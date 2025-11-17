LineageOS 19.1 for Exynos3475 devices WIP
------------------------------------

Create directories

	$ mkdir lineage-19.1
	$ cd lineage-19.1

Init the base manifest

	$ repo init -u https://github.com/kOtusin/android.git -b lineage-19.1 --git-lfs
  
Add the local manifest

  Take the xml file for your device and copy it to .repo/local_manifests/

Then sync up with this command:

	$ repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags --optimized-fetch --prune

-------------
 
_Building from source_
---------------

	$ . build/envsetup.sh
	$ lunch lineage_DEVICE-userdebug
	$ mka bacon

-------------

**If the build ends with the error "webview_intermediates/package.apk: error: failed opening zip: Invalid file."**
---------------
	$ cd external/chromium-webview/prebuilt/arm
 	$ git rev-parse --git-dir
  	$ git config --global --add safe.directory external/chromium-webview/prebuilt/arm/
   	$ git lfs pull
	$ cd ../../../..
	
