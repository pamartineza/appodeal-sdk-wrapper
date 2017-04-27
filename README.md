# appodeal-sdk-wrapper
Get Appodeal SDK adding just a Gradle dependency line :)



x.y.z.version  -> x.y.z match official Appodeal release, "version" should be 0 or n if I have to make any release to add fixes

The aim of this repository is to simplify updating Appodeal SDK or switching among available versions, it includes all jar dependencies, manifest entries and proguard configuration.

####Please read carefully:

1- Aar's dependencies **are NOT** included (I haven't been capable of packaging successfully the .aar's' whithin an Android Library, let me know if you know how to do it) so you should manually download it from Appodeal website and import the .aar's' to your project. (Note: aars are also available in this repo in the folder aars)
```groovy
compile project(':adcolony-sdk-3.1.1')
compile project(':facebook-audience-network-4.19.0')
compile project(':cheetah-mobile-3.5')
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

<!-- Optional -->
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```

##How to add to your project:

This project has been built using Jitpack.io
[![](https://jitpack.io/v/pamartineza/appodeal-sdk-wrapper.svg)](https://jitpack.io/#pamartineza/appodeal-sdk-wrapper)

Releases available using this repo:
* 2.0.0-beta (April 12, 2017)
-> com.github.pamartineza:appodeal-sdk-wrapper:2.0.0-beta.0 (aars: cheetah-mobile-3.5.aar, facebook-audience-network-4.19.0, adcolony-sdk-3.1.1')
* 1.15.9 (February 16, 2017)
-> com.github.pamartineza:appodeal-sdk-wrapper:1.15.9.0 (aars: cheetah-mobile-3.4.7.aar)
* 1.15.8 (December 15, 2016)
-> com.github.pamartineza:appodeal-sdk-wrapper:1.15.8.0 (aars: cheetah-mobile-3.4.7.aar)
* 1.15.7 (October 10, 2016)
-> com.github.pamartineza:appodeal-sdk-wrapper:1.15.7.0 (aars: cheetah-mobile-3.4.7.aar)
* 1.15.5 (September 26, 2016)
-> com.github.pamartineza:appodeal-sdk-wrapper:1.15.5.0 (aars: cheetah-mobile-3.4.7.aar)
* 1.15.3 (September 6, 2016)
-> com.github.pamartineza:appodeal-sdk-wrapper:1.15.3.0 (aars: unity-ads-1.5.8.aar and cheetah-mobile-3.4.7.aar)
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

####Please star :star: this project if you find it useful :)
####Follow me on Twitter to get updates :+1: [@pamartineza](https://twitter.com/pamartineza)