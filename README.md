# HiltAndroid
Hilt android implementation

# Add Hilt Dependencies in Android project 

## Adding Hilt Gradle plugin in Application gradle file(build.gradle)

```groovy
buildscript {

    ext.hilt_version = '2.31.2-alpha'

    dependencies {
         .....
        classpath "com.google.dagger:hilt-android-gradle-plugin:$hilt_version"
    }
 }

```

## Apply the Gradle plugin and add these dependencies in your app/build.gradle file
```groovy
plugins {
    ....
    id 'dagger.hilt.android.plugin'
    id 'kotlin-kapt'
}

dependencies {
    ....
    implementation "com.google.dagger:hilt-android:$hilt_version"
    kapt "com.google.dagger:hilt-android-compiler:$hilt_version"
}
```

## Hilt use Java 8 features so we add following code in app/build.gradle file.

```groovy
android {
    ....     
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}
```

## We use Hilt so we must declare Application class that is annotated with @HiltAndroidApp.

#### This @HiltAndroidApp annotation is generate Hilt components and it attach with Application object lifecycle and provide dependency to it.

```kotlin
@HiltAndroidApp
class MyApplication : Application(){
}
```

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.hiltdemo">

    <application
        android:name=".MyApplication"
        ....
    >
        
</application>
```
