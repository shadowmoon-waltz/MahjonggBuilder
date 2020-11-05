MahjonggBuilder
===============

MahjonggBuilder was an old googlecode project for Android, which was retrieved from an [archive] (https://archive.softwareheritage.org/browse/origin/http://mahjonggbuilder.googlecode.com/svn//directory/).

Build changes
-------------
- Upgraded build system to gradle (wrapper is 6.6.1, uses android build tools 4.0.1).
- Target api version is android-30, with min api version retained as android-1.
- Had to disable lint on release to build, because that was causing the gradle build to crash (still need to determine why).
- Increased version string to 1.5
- Added release signing based on "gradle.properties" in your gradle config directory (which usually defaults to "~/.gradle").
  Add the following lines to that file `
keystoreFile=C:\\somewhere\\key.jks
keystorePassword=<keystore password>
keystoreAlias=<key alias>
keystoreAliasPassword=<key password>
`

Code changes
------------
- Change sidewall size calculation in BaseActivity.java's updateZBuffer.
- Add preference for sidewall size (marked border size is based on this value) and add preference getter in Utils.java.

Build instructions
------------------
- Run `gradlew clean` in repository root to clean up previously compiled code, if necessary.
- Follow signing notes above if you want APK output to be signed during build.
- To build, run "gradlew assembleRelease" in repository root; APK is written to app/build/outputs/apk/release/app-release.apk in repository root.
