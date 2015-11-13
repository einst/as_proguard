# AndroiStudio Proguard

##Why I wrote this script  

there are some differences between AndroidStudio and eclipse, such as: third-party library is no longer required to declare with -libraryjars,Otherwise，Android studio will throw a exception:java.io.IOException: The same input jar [xxx.jar] is specified twice.
this script is based on google official [proguard-android.txt](https://android.googlesource.com/platform/tools/base/+/HEAD/files/proguard-android.txt),I just added some necessary content

##How to use:

###gradle 2.5 or later(>=gradle2.5)：

```
android.buildTypes {
    release {
        minifyEnabled = true
        proguardFiles  += file('proguard-rules.txt')
    }
}
```

###other old gradle version(<gradle2.5):
```
android {
    buildTypes {
        release {
            runProguard true
            proguardFile 'proguard-android.txt'
        }
    }
}
```

#中文：

##Android Studio 混淆脚本

由于AndroidStudio的混淆脚本和eclipse有些不——比如：android studio已经不需要-libraryjars 来声明第三方库了，否则会报库被引用两次的错误信息。
此脚本仅仅是在google官方脚本[proguard-android.txt](https://android.googlesource.com/platform/tools/base/+/HEAD/files/proguard-android.txt)上增加了部分内容

##使用方法：

###gradle 2.5及以上版本：
```
android.buildTypes {
    release {
        minifyEnabled = true
        proguardFiles  += file('proguard-rules.txt')
    }
}
```
###gradle 2.5以下版本：
```
android {

    buildTypes {
        release {
            runProguard true
            proguardFile 'proguard-android.txt'
        }
    }
}
```
