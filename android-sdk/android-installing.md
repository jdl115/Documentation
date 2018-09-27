---
uid: android-installing
---

## Installing Android SDK
To use Trivver SDK on Android need add following code into your app's build.gradle:

```groovy
repositories{
    maven{url 'https://repository.trivver.com/repository/maven-releases/'}
}

dependencies {
        compile ('com.trivver:trivver-smarttab:1.0.23:prodRelease@aar'){
            transitive = true;
        }
}
```

Triver SDK requered minimum API Level not less 14 for the application. Check the version of your project you can in file build.gradle `minSdkVersion`.