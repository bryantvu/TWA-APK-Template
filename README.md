# TWA APK Template
## Table of Contents
- [Introduction](#introduction)
- [FAQ](#faq)
- [Setup](#setup)
- [GMS vs HMS Behavior](#gms-vs-hms-behavior)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Introduction
This Android project is an example template based off of the files generated from [PWA Builder](https://pwabuilder.com/) and is meant for those that wish to have greater control in building their own TWA apps.

While PWA Builder can automatically generate an APK without the Android Studio IDE, it is very simple for a developer with Android experience to modify the template project directly.

This option might be better if:
- There are issues using PWA Builder to generate an APK.
- A developer wishes to customize the PWA solution to meet their needs.

## FAQ

1. What is a PWA?  <br />
   PWA  = Progress Web Application. These are web apps that are built with modern APIs to deliver enhanced capabilities, reliability, and an overall better end user experience that is closer to that of a native mobile app. https://web.dev/what-are-pwas/
2. What is PWA Builder?  <br />
   [PWABuilder.com](https://www.pwabuilder.com/) is a Microsoft open-source tool that can automatically package PWAs for mobile app stores. No developer experience is required.

3. What is a TWA (Trusted Web Activity)?  <br />
   "A Trusted Web Activity (TWA) displays a full screen Chrome browser inside of an Android app with no browser UI. Although Android apps routinely include web content using a Chrome Custom Tab (CCT) or WebView, a TWA offers unique advantages when you need Chrome’s performance and features in your app in full screen mode." - [Chromium Blog](https://blog.chromium.org/2019/02/introducing-trusted-web-activity-for.html)

4. Why use this template over PWA Builder? <br />
   Some websites might not meet the necessary PWA score on PWAB and cannot be packaged. This template option is for those that wish to see how their website looks and feels as a TWA without taking the effort to meet the PWA standard first.

5. Why do I see the navigation bar at the top of the screen? <br />
   "A Trusted Web Activity runs a Chrome browser full screen in an Android app, meaning there is no browser UI visible in the app, including the URL bar. This is a powerful capability so we need to verify that the app and the site belong to the same developer - hence ‘Trusted’. To verify that the app and the site opened in the TWA belong to the same developer, a TWA uses [Digital Asset Links](https://developers.google.com/digital-asset-links/v1/getting-started) to certify ownership." - Chromium Blog

6. Why does a "digital asset links verification failed" message appear? <br />
   This is a similar issue to how the navigation bar appears, occuring when the [Digital Asset Links](https://developers.google.com/digital-asset-links/v1/getting-started) have not been setup properly (which only the website owner can do). In my testing, it has only occurred on Google Chrome.

## Setup
Items to change:
- **Package Name**
  [Guide](https://stackoverflow.com/questions/16804093/rename-package-in-android-studio)
- **Host URL** - build.gradle(app), L26
- **App Name** - build.gradle(app), L28-29
- **UI Color** - build.gradle(app), L30-34
- **Splash Page Color** - build.gradle(app), L35
- **App Icon**
  [Guide](https://stackoverflow.com/questions/26615889/how-do-you-change-the-launcher-logo-of-an-app-in-android-studio)
- **Splash Image**
  All splash images must be replaced with the PNG files of following square dimensions and name.
  **Note: splash images might not appear on Huawei devices.*
    - res/drawable-hdpi/splash.png (300px square)
    - res/drawable-mdpi/splash.png (450px square)
    - res/drawable-xhdpi/splash.png (600px square)
    - res/drawable-xxhdpi/splash.png (900px square)
    - res/drawable-xxxhdpi/splash.png (1200px square)

## GMS vs HMS Behavior

Please note that the LauncherActivity has been modified to check for GMS availability. If GMS is detected, the TWA launcher will proceed as normal and select the best TWA provider on the device. In the case that GMS is not available, it is assumed that the app is running on a Huawei device and the TWA is force launched using the Huawei Browser.

## License
This Android sample code is licensed under the  [Apache License, version 2.0](http://www.apache.org/licenses/LICENSE-2.0)

## Acknowledgements
The code in this project was created from the Android template found in [Bubblewrap](https://github.com/GoogleChromeLabs/bubblewrap) and additions from [Android Browser Helper](https://github.com/GoogleChrome/android-browser-helper)