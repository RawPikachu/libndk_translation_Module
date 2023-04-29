# LibNDK Translation for arm64-v8a,armeabi-v7a,armeabi
### newbit @ xda-developers
Installs the libndk_translation functions into you AVD.

### Description
Installs the libndk_translation functions into you AVD, Android 11

### Notes (might not apply anymore)
* rc file is not needed anymore, mount binfmt_misc and register copies are now in service.sh
* system.prop is updated
* set_perm_recursive are updated
* /system/lib/liblog.so and /system/lib64/liblog.so are added
	* due to **cannot locate symbol "__android_log_set_logger"** Error, liblog.so is needed
	* [__android_log_set_logger](https://developer.android.com/ndk/reference/group/logging#group___logging_1ga0e29961fa7bd5904bfc142d795af1fd6) is available since API level 30.
	* ADB doesn't work anymore, after Module is enabled and AVD rebooted
	* to test the LibNDK, copy your armeabi-v7a APKs **before** the module is enabled, to the AVD with adb push
* arm64-v8a APKs are still crashing
