- Disabled dm-verity (if applicable)
- Disabled forceencrypt (if applicable)
- SuperSU inject script
- Patched Sepolicy:

Root a reference device (4.4+ with SELinux enabled) with v2.50+
Extract the sepolicy file from the target boot image's ramdisk
With the reference device connected to ADB:
```
adb push sepolicy /data/local/tmp/sepolicy

adb shell su -c "supolicy --file /data/local/tmp/sepolicy /data/local/tmp/sepolicy_out"

adb shell su -c "chmod 0644 /data/local/tmp/sepolicy_out"

adb pull /data/local/tmp/sepolicy_out sepolicy_out
```
