---- setup ----

Starting from the root of your source tree and check out the project:

cd vendor/htc
git clone git://github.com/koush/platform_vendor_htc_mytouch-open.git mytouch-open

---- setup using a localmanifest.xml ----

You can also add the reference to this project in a localmanifest.xml.
The file would need to contain atleast the following:

<?xml version="1.0" encoding="UTF-8"?>
<manifest>
    <remote name="github" fetch="git://github.com/" />
    <project path="vendor/htc/magic-open" name="koush/platform_vendor_htc_magic-open" revision="refs/heads/master" remote="github" />
</manifest>


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

