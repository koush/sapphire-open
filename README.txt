
---- build configuration ----

You can configure to build for HTC Dream (aka T-Mobile G1) by putting
the following in your buildspec.mk file at the root of the source tree:

TARGET_PRODUCT := htc_sapphire

If you wish to override the included prebuilt kernel image, add:

TARGET_PREBUILD_KERNEL := /path/to/kernel/arch/arm/boot/zImage

---- proprietary files ----

The HTC Dream device includes a small number of proprietary binary 
files that are necessary for Android to work correctly on it.

They can be obtained from your Dream device by running the
extract-files.sh script in this directory.  It will create the 
proprietary subdirectory, and use adb (which will need to be in 
your path) to copy the files from your device.  You will need to
enable USB Debugging (under Settings/Applications/Development)
for this to work.

