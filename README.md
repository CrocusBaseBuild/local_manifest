AICP r11.1 for Exynos3475 devices WIP
------------------------------------

Create directories

	$ mkdir aicp
	$ cd aicp

Init the base manifest

**For some reason, we need to use older manifest for now**

	$ repo init -u https://github.com/AICP/platform_manifest.git -b r11.1 --git-lfs --depth=1
  
Add the local manifest

  Take the xml file for your device and copy it to .repo/local_manifests/

Then sync up with this command:

	$ repo sync --no-tags --no-clone-bundle

-------------
 
_Building from source_
---------------

	$ . build/envsetup.sh
	$ lunch lineage_DEVICE-userdebug
	$ mka bacon
