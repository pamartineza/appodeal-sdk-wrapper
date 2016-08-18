# appodeal-sdk-wrapper
Get Appodeal SDK adding just a Gradle dependency line :)



x.y.z.version  -> x.y.z match official Appodeal release, "version" should be 0 or n if I have to make any release to add fixes

The aim of this repository is to simplify updating Appodeal SDK or switching among available versions, it includes all jar dependencies, manifest entries and proguard configuration.

####Please read carefully:

1- Unity-ads and Cheetah-Mobile dependencies  **are NOT** included (I haven't been capable of packaging successfully the .aar's' whithin an Android Library, let me know if you know how to do it) so you should manually download it from Appodeal website and import the .aar's' to your project.
```groovy
compile project(':unity-ads-1.5.8')
compile project(':cheetah-mobile-3.4.7')
```
2- Google Play Services **are NOT** included nor support libraries, you must add them in your app dependencies section and don't forget to add the manifest entries for ads:
```groovy
compile 'com.android.support:recyclerview-v7:a.b.c'
compile 'com.google.android.gms:play-services-ads:r.s.t'
compile 'com.google.android.gms:play-services-location:r.s.t'
```
```xml
<meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />

<activity android:name="com.google.android.gms.ads.AdActivity"
      android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|uiMode|screenSize|smallestScreenSize"
      android:theme="@android:style/Theme.Translucent" />	
```
3- AndroidManifest permissions **are NOT** included to allow you to choose what fits best for your pourposes, check Appodeal docs for further references

```xml
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

* 1.15.2 (August 12, 2016)
-> com.github.pamartineza:appodeal-sdk-wrapper:1.15.2.0 (aars: unity-ads-1.5.8.aar and cheetah-mobile-3.4.7.aar)
* 1.15.1 (August 8, 2016)
-> com.github.pamartineza:appodeal-sdk-wrapper:1.15.1.0 (aars: unity-ads-1.5.8.aar and cheetah-mobile-3.4.7.aar)
* 1.14.15 (June 17, 2016)
-> com.github.pamartineza:appodeal-sdk-wrapper:1.14.15.0 (aar: unity-ads-1.5.6.aar)

_(Note: aars are available in this repo in the folder aars)_



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

