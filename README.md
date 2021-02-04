# HiltAndroid
Hilt android implementation

## Adding Hilt Gradle plugin in Application gradle file(build.gradle)

```
buildscript {

    ext.hilt_version = '2.31.2-alpha'

    dependencies {
         .....
        classpath "com.google.dagger:hilt-android-gradle-plugin:$hilt_version"
    }
 }

```
