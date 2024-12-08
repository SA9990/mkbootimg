mkbootimg tool is used to create an Android boot image, typically combining the kernel, ramdisk, and other necessary components. 
usage: 
mkbootimg.py [-h] [--kernel KERNEL] [--ramdisk RAMDISK] [--second SECOND]
                    [--dtb DTB]
                    [--recovery_dtbo RECOVERY_DTBO | --recovery_acpio RECOVERY_ACPIO]
                    [--cmdline CMDLINE] [--vendor_cmdline VENDOR_CMDLINE]
                    [--base BASE] [--kernel_offset KERNEL_OFFSET]
                    [--ramdisk_offset RAMDISK_OFFSET] [--second_offset SECOND_OFFSET]
                    [--dtb_offset DTB_OFFSET] [--os_version OS_VERSION]
                    [--os_patch_level OS_PATCH_LEVEL] [--tags_offset TAGS_OFFSET]
                    [--board BOARD] [--pagesize {2048,4096,8192,16384}] [--id]
                    [--header_version HEADER_VERSION] [-o OUTPUT]
                    [--vendor_boot VENDOR_BOOT] [--vendor_ramdisk VENDOR_RAMDISK]
                    [--vendor_bootconfig VENDOR_BOOTCONFIG]
                    [--gki_signing_algorithm GKI_SIGNING_ALGORITHM]
                    [--gki_signing_key GKI_SIGNING_KEY]
                    [--gki_signing_signature_args GKI_SIGNING_SIGNATURE_ARGS]
                    [--gki_signing_avbtool_path GKI_SIGNING_AVBTOOL_PATH]

options:
  -h, --help            show this help message and exit
  --kernel KERNEL       path to the kernel
  --ramdisk RAMDISK     path to the ramdisk
  --second SECOND       path to the second bootloader
  --dtb DTB             path to the dtb
  --recovery_dtbo RECOVERY_DTBO
                        path to the recovery DTBO
  --recovery_acpio RECOVERY_ACPIO
                        path to the recovery ACPIO
  --cmdline CMDLINE     kernel command line arguments
  --vendor_cmdline VENDOR_CMDLINE
                        vendor boot kernel command line arguments
  --base BASE           base address
  --kernel_offset KERNEL_OFFSET
                        kernel offset
  --ramdisk_offset RAMDISK_OFFSET
                        ramdisk offset
  --second_offset SECOND_OFFSET
                        second bootloader offset
  --dtb_offset DTB_OFFSET
                        dtb offset
  --os_version OS_VERSION
                        operating system version
  --os_patch_level OS_PATCH_LEVEL
                        operating system patch level
  --tags_offset TAGS_OFFSET
                        tags offset
  --board BOARD         board name
  --pagesize {2048,4096,8192,16384}
                        page size
  --id                  print the image ID on standard output
  --header_version HEADER_VERSION
                        boot image header version
  -o OUTPUT, --output OUTPUT
                        output file name
  --vendor_boot VENDOR_BOOT
                        vendor boot output file name
  --vendor_ramdisk VENDOR_RAMDISK
                        path to the vendor ramdisk
  --vendor_bootconfig VENDOR_BOOTCONFIG
                        path to the vendor bootconfig file

[DEPRECATED] GKI 2.0 signing arguments:
  --gki_signing_algorithm GKI_SIGNING_ALGORITHM
                        GKI signing algorithm to use
  --gki_signing_key GKI_SIGNING_KEY
                        path to RSA private key file
  --gki_signing_signature_args GKI_SIGNING_SIGNATURE_ARGS
                        other hash arguments passed to avbtool
  --gki_signing_avbtool_path GKI_SIGNING_AVBTOOL_PATH
                        path to avbtool for boot signature generation

vendor boot version 4 arguments:
  --ramdisk_type {none,platform,recovery,dlkm}
                        specify the type of the ramdisk
  --ramdisk_name NAME
                        specify the name of the ramdisk
  --board_id{0..15} NUMBER
                        specify the value of the board_id vector, defaults to 0
  --vendor_ramdisk_fragment VENDOR_RAMDISK_FILE
                        path to the vendor ramdisk file

  These options can be specified multiple times, where each vendor ramdisk
  option group ends with a --vendor_ramdisk_fragment option.
  Each option group appends an additional ramdisk to the vendor boot image.
