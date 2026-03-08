# debloater
Debloat your device using your terminal (requires su permissions)
Adapted to work with KernelSU, Magisk and APatch using OverlayFS. You can use something like Termux to run it 

 Just enter the command in Terminal Emulator:

	debloat
	
or

	debloat -h
	
 And you will be presented with a list of apps inside /system 
 Just reboot and you will have it removed, systemless-ly
 
## Error?
 Running into issues? Just type `logs` in the module menu to automatically upload your log files and generate a shareable link. You can drop that link right here! Alternatively, you can manually grab the `/data/local/tmp/ terminal_debloater-verbose.log` file and attach it to this thread

## Note:
Inspired by the good ol' days of Magisk v23.0, this is built on the foundation of veez21's original debloat script. It's been completely revamped and modernized to bring that classic, reliable debloating functionality to current Android releases

## Changelog

### v1
* Fixed critical array indexing bug that caused first app in sorted list to be hidden
* Fixed selection offset bug where selecting app #1 would debloat app #2 instead
* Fixed special character handling for apps with %, (), and other symbols in names
* Added support for 5 additional system partitions:
  - /system/vendor/priv-app
  - /system/system_ext/app
  - /system/system_ext/priv-app
  - /system/vendor/overlay
  - /system/product/overlay
* Improved KernelSU compatibility with enhanced debloat method
* Cleaned up auto-generated RRO overlay names for better readability
* Added [overlay] prefix to distinguish overlay packages from actual apps
* Improved error handling when aapt fails to read APK files
* Changed array population from word-splitting to line-by-line reading for better stability
* Added .debloated marker file with metadata (app name, package, date)
* Enhanced debloat_app() to work on both Magisk and KernelSU
