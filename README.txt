---- easy setup method ----

The preferred setup is by using a local_manifest.xml in your .repo
directory. But if for some reason you don't want to do that, you can do the
following.
Starting from the root of your source tree, check out the project:

cd vendor/htc
git clone git://github.com/koush/mytouch-open.git mytouch-open
# You may want to checkout the appropriate branch:
# git checkout -b cupcake origin/cupcake
# or 
# git checkout -b eclair origin/eclair

---- preferred setup using a .repo/local_manifest.xml ----

You can also add the reference to this project in a local_manifest.xml.
The file would need to contain atleast the following:

<?xml version="1.0" encoding="UTF-8"?>
<manifest>
    <remote name="github" fetch="git://github.com/" />
    <project path="vendor/htc/mytouch-open" name="koush/mytouch-open" revision="refs/heads/master" remote="github" />
</manifest>

As above, you may want to change the "revision" attribute to the appropriate branch.

After that file is modified/created, simply run:

repo sync

---- build configuration ----

You can configure to build for HTC MyTouch (aka T-Mobile MyTouch) by setting
your environment at the root of the source tree:

. build/envsetup.sh
lunch htc_mytouch-eng

---- proprietary files ----

The HTC MyTouch device includes a small number of proprietary binary 
files that are necessary for Android to work correctly on it.

They can be obtained from your Dream device by running the
extract-files.sh script in this directory.  It will create the 
proprietary subdirectory, and use adb (which will need to be in 
your path) to copy the files from your device.  You will need to
enable USB Debugging (under Settings/Applications/Development)
for this to work.

---- creating an update.zip after building ----

Run the following from the root of your Android directory.

TARGET_NO_RADIOIMAGE=true make otapackage

The resultant update.zip can then be found at:
out/target/product/$TARGET_PRODUCT/htc_mytouch-ota-eng.koush.zip