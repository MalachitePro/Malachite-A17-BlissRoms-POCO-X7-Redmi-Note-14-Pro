# BlissRoms 20.1 (Android 17) for POCO X7 and Redmi Note 14 Pro 5G (malachite)

BlissRoms v20.1 (Android 17) for the POCO X7 and the Redmi Note 14 Pro 5G (codename malachite, MediaTek MT6878 / Dimensity 7300).
First BlissRoms build for these phones. Made by HUNTER[RKJAAT].
Support group: https://t.me/Malachite_Pro

Only for malachite. Check Settings > About phone before flashing. Other Redmi Note 14 or POCO phones are different devices, do not flash this on them.

## Status

Tested: everything we tried works. No known bugs right now. If you find one, tell us in the support group.

There are no Google apps in this ROM (no Play Store). See "Google apps" below if you want them.

## Download

- ROM zip: https://t.me/Malachite_Pro/16
- boot.img, vendor_boot.img, init_boot.img and checksums.txt: in the Releases of this repo.

SHA-256 of the zip: d4aefe723ce3c02bcd252d9d77dac38a3dda315422faa11e736e5f6f00864eda

## How to install

Bootloader must be unlocked. This wipes your data, take a backup first.

1. Flash the stock Global fastboot ROM first and let it boot once.
   OS2.0.208.0.VOOMIXM version (2.0.208, Android 15). This ROM does not carry any firmware, so the firmware on the phone must be this one.
2. Go to fastboot and flash boot and vendor_boot from the Releases of this repo:

        fastboot flash boot_a boot.img
        fastboot flash vendor_boot vendor_boot.img

3. Go to recovery with the buttons only (power off, then hold Vol Up + Power). Do not use `adb reboot recovery` or `fastboot reboot recovery`, it can break things on this phone.
4. In recovery: **Format data** (not only wipe), then Apply update > Apply from ADB and run:

        adb sideload Bliss-v20.1-20261101-UNOFFICIAL-HUNTER-RKJAAT-malachite.zip

5. Reboot system.

**Format data is required.** If you come from another ROM or another build and skip it, the system can crash in a loop right after the boot logo. This build is signed with its own keys, so data from a build signed with different keys does not work.

Check your downloads against `checksums.txt` before flashing.

You do all this at your own risk. We are not responsible for a bricked phone.

## Google apps

Not included. If you want them, use MindTheGapps 17.0.0 arm64: https://github.com/MindTheGapps/17.0.0-arm64/releases
We have not tested it ourselves yet. Do not use GApps from random sites.

Flash it right after the ROM and before the first boot: when the ROM zip is done, power off, go to recovery with the buttons again, Apply update > Apply from ADB, sideload the MindTheGapps zip, then reboot.

## Source

- BlissRoms: https://github.com/BlissRoms (branch xylobium, tag v20.1-stable-xylobium)
- Device tree: https://github.com/MalachitePro/android_device_xiaomi_malachite
- Vendor blobs: https://github.com/MalachitePro/proprietary_vendor_xiaomi_malachite
- Hardware: https://github.com/MalachitePro/android_hardware_xiaomi

## Credits

- BlissRoms team for the ROM.
- LineageOS team for the base BlissRoms is built on.
- The Android 16 (LineageOS 23.2) device tree for malachite is from malachite-project (noamtu123), puhboo, mt6878-devs and cmdr-chara. Thanks to them.
- Android 17 port, fixes, face unlock port and this build: HUNTER[RKJAAT].

## Kernel

Prebuilt Linux 6.1 kernel from malachite-project (GPLv2). Source: https://github.com/malachite-project/kernel_manifest-6.1
