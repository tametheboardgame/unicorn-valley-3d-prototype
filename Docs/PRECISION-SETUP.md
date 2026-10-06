# Precision 7780 Development Workstation

## Confirmed Hardware

Primary 3D development workstation:

- Dell Precision 7780.
- Intel Core i9-13950HX.
- 64 GB RAM.
- NVIDIA RTX 1000 Ada Generation Laptop GPU, 6 GB GDDR6.
- 1 TB internal SSD.
- UEFI / TPM / Secure Boot-capable enterprise workstation.

This machine is sufficient for the Unicorn Valley 3D prototype. The GPU is below Epic's general 8 GB VRAM recommendation, but the final product is tablet-targeted and the workstation is still substantially more capable than the target device.

## Planned Operating-System Layout

The workstation is currently a corporate-managed Windows device.

Planned approach:

1. Preserve the existing corporate Windows installation.
2. Create a second Windows installation for game development.
3. Keep the development OS independent from the corporate Microsoft Entra / Intune environment.
4. Boot either environment natively so Unreal and Blender have full access to the CPU, RAM and GPU.

A virtual machine is not the preferred design.

## Security and Firmware Rules

Both operating systems should keep:

- UEFI boot.
- TPM enabled.
- Secure Boot enabled.

Do not disable Secure Boot or clear the TPM as part of the dual-boot setup.

The development OS should not be Microsoft Entra joined or Intune enrolled unless this is deliberately required later.

## Autopilot / Intune Considerations

Windows Autopilot registration, Microsoft Entra device identity and Intune MDM enrolment are separate states.

Before changing Autopilot registration, confirm the intended lifecycle for the existing corporate Windows installation. Microsoft documents full Autopilot deregistration as a managed decommissioning workflow and warns that deleting records in the wrong order can create orphaned or unrecoverable states.

The aim is:

- corporate Windows remains a normal compliant managed workstation;
- development Windows remains outside the corporate tenant;
- neither installation accidentally changes the other's management state.

Do not sign the development Windows installation into a work account in a way that triggers Entra join or automatic MDM enrolment.

## Intune Policy Check Before Repartitioning

Before changing the disk, inspect the policies currently assigned to the Precision.

Record whether the device is subject to:

- Require BitLocker/device encryption.
- FixedDrivesRequireEncryption.
- Deny write access to fixed drives not protected by BitLocker.
- Secure Boot compliance requirements.
- TPM compliance requirements.
- Windows Defender / Firewall compliance.
- Device Health Attestation.
- custom compliance scripts that inspect partitions, boot configuration or local storage.

The fixed-data-drive policy is particularly important. A second Windows partition may appear to the corporate OS as another fixed data drive. If policy requires all fixed drives to be BitLocker-protected, that partition can be affected even though it is intended for the development OS.

If fixed-drive encryption is enforced, design the BitLocker layout before installing the second OS rather than discovering the conflict afterwards.

## BitLocker Preparation

Changing the NTFS partition table or Windows boot manager can trigger BitLocker recovery.

Before repartitioning:

- verify the corporate OS recovery key is successfully escrowed and retrievable;
- export/store an authorised recovery copy according to company policy;
- record current BitLocker protector state;
- record the current partition layout;
- confirm Windows Recovery Environment status;
- suspend BitLocker protection before resizing partitions or altering the boot configuration;
- do not decrypt the corporate OS merely to repartition it.

After the new boot layout is established:

- boot corporate Windows;
- complete any expected BitLocker recovery;
- resume BitLocker protection;
- verify the protector is sealed correctly;
- verify recovery information remains escrowed;
- run an Intune sync;
- confirm the device reports compliant;
- confirm Secure Boot, TPM, Defender and Firewall state.

## Development Partition

Provisional size:

- 400 to 450 GB, subject to current corporate-drive utilisation.

The development Windows installation should contain:

- Epic Games Launcher.
- Unreal Engine 5.8.
- Visual Studio 2022 C++ game-development workload.
- Git.
- Git LFS.
- Blender.
- Android/Unreal mobile toolchain.
- NVIDIA workstation/game-development driver selected for stability.
- Unicorn Valley 3D prototype checkout.

Keep Unreal Derived Data Cache, temporary builds and downloaded asset libraries under explicit size control.

## Storage Contingency

The Precision 7780 supports multiple internal M.2 NVMe SSDs.

If same-disk dual boot causes policy, BitLocker or storage-management problems, a dedicated second NVMe SSD is the preferred fallback because it isolates development storage from the corporate OS disk while preserving native GPU/CPU access.

## Validation Gate

The workstation setup is accepted only after all of the following are true:

- corporate Windows boots normally;
- corporate BitLocker is healthy;
- corporate Intune status is compliant;
- Secure Boot and TPM remain enabled;
- development Windows boots independently;
- development Windows has full RTX GPU acceleration;
- development Windows is not enrolled in the corporate tenant;
- Git, Unreal, Visual Studio and Blender operate correctly;
- an Unreal Android test build can be packaged and deployed to the Galaxy Tab S8.
