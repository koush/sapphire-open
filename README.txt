---- setup ----

Starting from the root of your source tree and check out the project:

cd vendor/htc
git clone git://github.com/koush/platform_vendor_htc_mytouch-open.git mytouch-open

---- build configuration ----

You can configure to build for HTC MyTouch (aka T-Mobile MyTouch) by setting
your environment at the root of the source tree:

. build/envsetup.sh
lunch htc_magic-eng

---- proprietary files ----

The HTC MyTouch device includes a small number of proprietary binary 
files that are necessary for Android to work correctly on it.

They can be obtained from your Dream device by running the
extract-files.sh script in this directory.  It will create the 
proprietary subdirectory, and use adb (which will need to be in 
your path) to copy the files from your device.  You will need to
enable USB Debugging (under Settings/Applications/Development)
for this to work.

