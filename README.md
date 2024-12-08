# Basic Commands:
1. **--kernel KERNEL**  
   *Path to the kernel image file.*  
   Specifies the kernel to be included in the boot image.

2. **--ramdisk RAMDISK**  
   *Path to the ramdisk file.*  
   Defines the ramdisk image to include in the boot image, containing essential system files for booting.

3. **--second SECOND**  
   *Path to the second bootloader (optional).*  
   Some devices use a second bootloader; specify the path if required.

4. **--dtb DTB**  
   *Path to the device tree binary (DTB).*  
   Contains the hardware configuration necessary for the kernel.

5. **--cmdline CMDLINE**  
   *Kernel command line arguments.*  
   Arguments to pass to the kernel during boot (e.g., configuring hardware, enabling debugging).

6. **--vendor_cmdline VENDOR_CMDLINE**  
   *Vendor-specific kernel command line arguments.*  
   Allows setting vendor-specific arguments for the vendor boot image.

### Memory and Offset Configuration:
7. **--base BASE**  
   *Base address for loading components in memory.*  
   Defines the base address for the kernel, ramdisk, and other components.

8. **--kernel_offset KERNEL_OFFSET**  
   *Offset for the kernel in memory.*  
   Specifies where in memory the kernel should be loaded.

9. **--ramdisk_offset RAMDISK_OFFSET**  
   *Offset for the ramdisk in memory.*  
   Defines where the ramdisk will be loaded in memory.

10. **--second_offset SECOND_OFFSET**  
    *Offset for the second bootloader.*  
    Specifies where to load the second bootloader in memory.

11. **--dtb_offset DTB_OFFSET**  
    *Offset for the device tree.*  
    Defines the memory location for the device tree blob.

### Image Customization and Output:
12. **--os_version OS_VERSION**  
    *Operating system version.*  
    Defines the OS version for the boot image.

13. **--os_patch_level OS_PATCH_LEVEL**  
    *Operating system patch level.*  
    Sets the patch level for the operating system.

14. **--tags_offset TAGS_OFFSET**  
    *Tags offset.*  
    Defines the offset for kernel tags, usually for passing bootloader information.

15. **--board BOARD**  
    *Board name.*  
    Specifies the board name (e.g., "obiwan") to customize the boot image.

16. **--pagesize {2048,4096,8192,16384}**  
    *Page size for the boot image.*  
    Sets the page size, important for memory alignment during boot.

17. **--output OUTPUT**  
    *Output file name.*  
    Specifies the name of the boot image file to be generated.

### Vendor-Specific Options:
18. **--vendor_boot VENDOR_BOOT**  
    *Vendor boot image output file.*  
    Creates a vendor boot image containing proprietary or customized components.

19. **--vendor_ramdisk VENDOR_RAMDISK**  
    *Path to the vendor ramdisk file.*  
    Specifies a separate ramdisk for the vendor’s boot components.

20. **--vendor_bootconfig VENDOR_BOOTCONFIG**  
    *Path to the vendor boot configuration file.*  
    Allows specifying a custom configuration for the vendor’s boot image.

### Deprecated GKI 2.0 Signing Options:
21. **--gki_signing_algorithm GKI_SIGNING_ALGORITHM**  
    *Signing algorithm for GKI boot image.*  
    Defines which signing algorithm to use for GKI-based boot images (e.g., RSA).

22. **--gki_signing_key GKI_SIGNING_KEY**  
    *Path to RSA private key.*  
    Specifies the path to the private key used for signing the boot image.

23. **--gki_signing_avbtool_path GKI_SIGNING_AVBTOOL_PATH**  
    *Path to `avbtool` for signing.*  
    Path to the `avbtool` used to sign the boot image, ensuring integrity.

### Vendor Boot Version 4 Options:
24. **--ramdisk_type {none,platform,recovery,dlkm}**  
    *Type of vendor ramdisk.*  
    Defines the type of ramdisk, such as platform, recovery, or dynamic load kernel mode (DLKM).

25. **--ramdisk_name NAME**  
    *Name of the ramdisk.*  
    Assigns a name to the ramdisk for identification in vendor-specific boot images.

26. **--board_id {0..15} NUMBER**  
    *Board ID for the vendor image.*  
    Specifies a board ID for identifying different device variants.

27. **--vendor_ramdisk_fragment VENDOR_RAMDISK_FILE**  
    *Path to vendor ramdisk fragment.*  
    Allows you to add multiple fragments to the vendor ramdisk, creating a larger image if necessary.

### Miscellaneous:
28. **--id**  
    *Prints the image ID.*  
    Outputs the ID of the boot image for reference.

29. **--header_version HEADER_VERSION**  
    *Boot image header version.*  
    Sets the version of the boot image header.

### Example Command:
Here is an example of how to use the `mkbootimg.py` command with some common options:

```bash
python mkbootimg.py --kernel /path/to/kernel --ramdisk /path/to/ramdisk --dtb /path/to/dtb --cmdline "androidboot.mode=normal" --base 0x10000000 --output /path/to/output.img
```

This would create a boot image with a kernel, ramdisk, and device tree, set to load from a specified base address, and output to `output.img`.
