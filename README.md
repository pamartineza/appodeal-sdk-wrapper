[![](https://jitpack.io/v/pamartineza/appodeal-sdk-wrapper.svg)](https://jitpack.io/#pamartineza/appodeal-sdk-wrapper)

# appodeal-sdk-wrapper
Get Appodeal SDK adding just a Gradle dependency line :)

x.y.z.version  -> x.y.z match official Appodeal release, "version" should be 0 or n if I have to make any release to add fixes

The aim of this repository is to simplify updating Appodeal SDK or switching among available versions, it includes all jar dependencies, manifest entries and proguard configuration.

**Note:** Unity-ads dependency **is NOT** included (I haven't been capable of packaging successfully the unity ads .aar whithin an Android Library, let me know if you know how to do it) so you should manually download it from Appodeal website and import the unity-ads-version.aar to your project.

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

