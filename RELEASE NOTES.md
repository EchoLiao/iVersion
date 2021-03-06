Version 1.11 beta

- No longer requires StoreKit by default (see README for details)
- Removed disableAlertViewResizing property (no longer needed)
- Added Turkish translation
- Improved handling on HTTP request errors
- Now complies with the -Wextra warning level
- Removed deprecated methods on Mac OS

Version 1.10.6

- Fixed crash when plist contains versions later than latest in app store

Version 1.10.5

- Fixed critical bug in NSJSONSerializer implementation

Version 1.10.4

- Added Portuguese and Russian translations
- Now uses NSJSONSerializer if available, which solves problem with app store descriptions containing double quotes (iOS 4.x will still use the old parser)

Version 1.10.3

- Fixed potential infinite loop if release notes JSON contains 0x00 characters
- On Mac OS, release notes are now displayed in a scrolling text field (thanks to Daij-Djan for the suggestion).

Version 1.10.2

- Fixed issues where alert would not appear, even with preview mode enabled, if app has already been released but has no release notes
- Addressed possible issue on iOS 5.0.x where app store link does not work (unconfirmed).
- StoreKit framework is no longer included on Mac OS
- Added podspec

Version 1.10.1

- Fixed bug where iVersion would potentially display release notes for unreleased versions in the remote version plist if the user's version is not up to date with the latest version in the App Store
- Fixed deprecation warning when targeting iOS 6 and above
- iVersion now displays the StoreKit product view controller correctly even if a modally presented view controller has been displayed
- Added iVersionDidPresentStoreKitModal and iVersionDidDismissStoreKitModal delegate methods
- Added useAppStoreDetailsIfNoPlistEntryFound option
- Added Danish translation

Version 1.10

- Added new localisation system (see README for details)
- On iOS 6, iVersion can now use the StoreKit APIs to display the product page directly within the app.
- iVersion now requires the StoreKit framework on iOS
- iVersion now requires ARC. To use iVersion in a non-ARC project, follow the instructions in the README file.
- Dropped support for 32-bit Macs running Snow Leopard
- Fixed deprecation warning in iOS 6

Version 1.9.8

- Added verboseLogging option to make it easier to diagnose why a new version isn't being correctly detected
- Renamed debug property to previewMode as this better describes its function
- Fixed a bug where certain types of download error were not correctly passed to the delegate

Version 1.9.7

- Fixed crash on iOS 4.x and Mac OS 10.6.x when compiled using Xcode 4.4

Version 1.9.6

- Added support for iOS6. Currently it does not appear to be possible to link users directly to the release notes page on iOS6, but iVersion will now at least open the app store on the app page without an error.
- iVersion now displays correctly localised release notes
- Removed appStoreLanguage property, as this is no longer used

Version 1.9.5

- Fixed cache policy so that version data is no longer cached between requests while app is running
- Fixed typo in German translation

Version 1.9.4

- Now links users directly to update page on app store on iOS
- Fixed a bug where advanced properties set in the delegate methods might be subsequently overridden by iVersion
- Added disableAlertViewResizing option (see README for details)
- Added Resizing Disabled example project
- Added explicit 60-second timeout for remote version checks
- iVersion will now no longer spawn multiple download threads if closed and re-opened whilst performing a check
- Added Simplified Chinese translation

Version 1.9.3

- It is now possible again to use iVersion with apps that are not on the iOS or Mac app store using just the remoteVersionsPlist
- It is now possible again to test release notes using debug mode

Version 1.9.2

- Added logic to prevent UIAlertView collapsing in landscape mode
- Shortened default updateAvailableTitle to better fit the alert
- Removed applicationName configuration property as it is no longer used
- Fixed bug in Italian localised updateAvailableTitle text
- groupNotesByVersion now defaults to NO

Version 1.9.1

- Fixed bug where release notes containing commas would not be displayed
- Release notes containing unicode literals are now handled correctly
- Now uses localeIdentifier for language parameter to match iTunes format

Version 1.9

- Included localisation for French, German, Italian, Spanish and Japanese
- iVersion delegate now defaults to App Delegate unless otherwise specified
- Now checks the correct country's iTunes store based on the user locale settings

Version 1.8

- iVersion is now *completely zero-config* in most cases!
- iVersion can automatically detect app updates using official iTunes App Store search APIs based on your application bundle ID
- It is no longer necessary to set the app store ID in most cases
- Changed default checkPeriod to 0.0 so version check happens every launch
- Removed PHP web service as it is no longer needed

Version 1.7.3

- Added missing iVersionDidNotDetectNewVersion delegate method
- Added logic to prevent multiple prompts from being displayed if user fails to close one prompt before the next is due to be opened
- Added workaround for change in UIApplicationWillEnterForegroundNotification implementation in iOS5

Version 1.7.2

- Added automatic support for ARC compile targets
- Now requires Apple LLVM 3.0 compiler target

Version 1.7.1

- Now uses CFBundleShortVersionString when available instead of CFBundleVersion for the application version
- Fixed bug in iversion.php web service where platform was not set correctly
- Added logic to web service to use curl when available instead of file_get_contents for reading in iTunes search service data

Version 1.7

- Added additional delegate methods to facilitate logging
- Renamed some delegate methods
- Removed localChecksDisabled property and renamed remoteChecksDisabled property to checkAtLaunch for clarity and consistency with the iRate and iNotify libraries
- Combined remoteDebug and localDebug to simplify usage
- Added checkIfNewVersion method to manually trigger display of local version details

Version 1.6.4

- Updated iVersion web service to use official iTunes App Store search APIs
- iVersion now uses CFBundleDisplayName for the application name (if available) 
- Increased Mac app store refresh delay for older Macs
- Simplified version comparison logic
- Reorganised examples

Version 1.6.3

- Fixed web service and updated project for Xcode 4.2

Version 1.6.2

- Fixed version details in new version alert on iOS

Version 1.6.1

- Fixed crash on iOS versions before 4.0 when downloading version details.

Version 1.6

- Added openAppPageInAppStore method for more reliably opening Mac App Store
- Fixed issue with local versions plist path on Mac OS
- Renamed a couple of configuration settings names to comply with Cocoa conventions and prevent static analyzer warnings
- Added explicit ivars to support i386 (32bit x86) targets

Version 1.5

- Added PHP web service example for automatically scraping version from iTunes
- Added delegate and additional accessor properties for custom behaviour
- Added advanced example project to demonstrate use of the delegate protocol

Version 1.4

- Now compatible with iOS 3.x
- Local versions plist path can now be nested within a subfolder of Resources

Version 1.3

- Added Mac demo project
- Changed Mac App Store opening mechanism to no longer launch browser first
- Corrected error in documentation

Version 1.2

- Configuration no longer involves modifying iVersion.h file
- Now detects application launch and app switching events automatically
- No longer requires release notes to be included in update notifications
- Simpler to localise

Version 1.1

- Added optional remind me button
- Added ability to specify update period
- Local versions file path can now be set to nil

Version 1.0

- Initial release