# appodeal-sdk-wrapper
Get Appodeal SDK adding just a Gradle dependency line :)



x.y.z.version  -> x.y.z match official Appodeal release, "version" should be 0 or n if I have to make any release to add fixes

The aim of this repository is to simplify updating Appodeal SDK or switching among available versions, it includes all jar dependencies, manifest entries and proguard configuration.

**Please read carefully:**

1- Unity-ads dependency **is NOT** included (I haven't been capable of packaging successfully the unity ads .aar whithin an Android Library, let me know if you know how to do it) so you should manually download it from Appodeal website and import the unity-ads-version.aar to your project.
```groovy
compile project(':unity-ads-1.5.6')
```
2- Google Play Services **are NOT** included nor support libraries, you must add them in your app dependencies section and don't forget to add the manifest entries for ads:
```groovy
compile 'com.android.support:recyclerview-v7:a.b.c'
```
```xml
<meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />

<activity android:name="com.google.android.gms.ads.AdActivity"
      android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|uiMode|screenSize|smallestScreenSize"
      android:theme="@android:style/Theme.Translucent" />	
```
3- AndroidManifest permissions **are NOT** included to allow you to choose what fits bests for your pourposes

```
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<!-- Optional -->
<uses-permission android:name="android.permission.GET_ACCOUNTS" />
```

##How to add to your project:

This project has been built using Jitpack.io
[![](https://jitpack.io/v/pamartineza/appodeal-sdk-wrapper.svg)](https://jitpack.io/#pamartineza/appodeal-sdk-wrapper)

Releases available using this repo:

* 1.14.15 (June 17, 2016) -> com.github.pamartineza:appodeal-sdk-wrapper:1.14.15.0


Add to your root build.gradle

```groovy
allprojects {
	repositories {
		...
		maven { url "https://jitpack.io" }
	}
}
```	
	
	
Add to your app build.gradle, check Jitpack badge to get current release numbers [![](https://jitpack.io/v/pamartineza/appodeal-sdk-wrapper.svg)](https://jitpack.io/#pamartineza/appodeal-sdk-wrapper)
```groovy
dependencies {
        compile 'com.github.pamartineza:appodeal-sdk-wrapper:x.y.z.version'
}
```	

