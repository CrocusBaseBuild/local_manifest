LineageOS 18.0 for Exynos3475 devices (WIP)
------------------------------------

Create directories

	$ mkdir lineage-18.0
	$ cd lineage-18.0

Init the base manifest

**For some reason, we need to use older manifest for now**

	$ repo init -u https://github.com/LineageOS/android.git -b lineage-18.0 --depth=1
  
Add the local manifest

  Take the xml file for your device and copy it to .repo/local_manifests/

Then sync up with this command:

	$ repo sync --force-sync -q

-------------
 
_Building from source_
---------------

	$ . build/envsetup.sh
	$ lunch lineage_j1xlte-userdebug
	$ mka bacon
