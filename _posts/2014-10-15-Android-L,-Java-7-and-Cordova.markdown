---
layout: post
title:  "Android L, Java 7 and Cordova"
---
Google has just announced a new developer preview for Android L (Lollipop), which will be released this Friday, October 17. With that said, it is noted in the [ADT dependencies](http://developer.android.com/tools/sdk/eclipse-adt.html) that JDK 7 is required if you are targeting Android L. What does this mean if you are using Java 6 or have a jar file in your project that was created using Java 6? I did some research and testing with Android L, Java 7 and Cordova. Although it is stated that Java 7 is required, it doesn't seem that there is actually anything preventing you from building a project targeting Android L with Java 6 (as long as there are no Java 7 specific features being used). I tested this three ways:

1. I used the Cordova build scripts to build a project targeting Android L with my JAVA_HOME variable set to JDK 6. The project built and deployed to a device without any issues.

2. I imported a Cordova project to Eclipse, set the target to Android L and JDK to 6. Built and deployed the project without any issues. I also created a new Android project within Eclipse, followed the same steps and got the same results.

3. I imported a Cordova project to Android Studio, set the target to Android L and JDK to 6. I did get an error here with the build.gradle file about needed JDK 7 to target Android L. However, just for kicks I decided to try to build the project anyway. The project built (with warnings) and deployed to a device successfully. Initially, I did change the JDK to 7 to get rid of the error and the project still built and deployed successfully with the Cordova jar that was created using Java 6.

So based on my personal findings, it seems that unless you have Java 7 specific features or Android L specific features that require Java 7, you should still be able to target Android L with Java 6. And if, in the future, it does become absolutely required to use Java 7, then included jars created using Java 6 should work fine with the project as noted above in number 3.

If you have any different findings that conflict with my own, please let me know in the comments.