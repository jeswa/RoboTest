# RoboTest


Robo test is a test tool that is integrated with Firebase Test Lab for Android. Robo test analyzes the structure of your app's UI and then explores it methodically, automatically simulating user activities. Unlike the UI/Application Exerciser Monkey test, Robo test always simulates the same user activities in the same order when you use it to test an app on a specific device configuration with the same maximum depth and timeout settings. This lets you use Robo test to validate bug fixes and test for regressions in a way that isn't possible when testing with the UI/Application Exerciser Monkey test.

Robo test captures log files, saves a series of annotated screenshots, and then creates a video from those screenshots to show you the simulated user operations that it performed. These logs, screenshots, and videos can help you to determine the root cause if your app crashes, and can also help you to find issues with your app's UI

## Configuring Robo test

You can configure Robo test in multiple ways, as follows:

Maximum depth. You can configure how deeply Robo test explores your app by setting the maximum depth of the test. The maximum depth setting tells the test how thoroughly it should explore a particular branch of your app's UI before returning to the root of the UI (the main screen) to explore another branch. The default value for maximum depth is 50, and any value less than 2 prevents the test from exploring the app beyond the main screen.
Timeout. Depending on the complexity of your app's UI, Robo test might take five minutes or more to complete a thorough set of UI interactions. We recommend setting the test timeout to at least 120 seconds (2 minutes) for most apps, and 300 seconds (5 minutes) for moderately complex apps. The default value for timeout is 300 seconds (5 minutes) for tests run from Android Studio and the Google Developer Console, and 1500 seconds (25 minutes) for tests run from the gcloud command line.
If your app has both a UI with significant depth and multiple UI branches that Robo test should explore, then you should do one of the following to ensure that Robo test explores your app thoroughly:

Set a high value for timeout so that Robo test is able to explore multiple UI branches.
Set a low value for maximum depth so that Robo test completes some exploration of each UI branch.

## Integration with Google Play

You can use Robo test in the Google Play Console when you upload and publish your app's APK file using either the alpha or beta channel. Robo test runs on a set of popular physical devices from different geographic locations, providing test coverage across various form factors and hardware configurations.

## Test account sign-in and predefined text input

Robo test supports test account sign-in, and also allows you to enter predefined text into fields in your app. For custom sign-in and other predefined text input, Robo test can enter text into EditText fields in your app. For each string, you need to identify the EditText field using an Android resource name.

### Sign-in

Robo test has two mutually-exclusive methods to support sign-in:

Automatic sign-in: If your app has a sign-in screen that uses a Google account for authentication, Robo test generates a Google test account, unless you provide test account credentials for custom sign-in.
Custom sign-in: If you provide test account credentials, you need to tell Robo test where to enter them, and also provide those credentials.
To provide test account credentials for custom sign-in, do the following:

On the Select dimensions page, choose Show advanced options.
Under Test account credentials (Optional), enter the username and password resource names and the username and password for the test account.

### Predefined text input

You can provide custom input text for other text fields used by your app. To provide text input for additional fields, do the following:

On the Select dimensions page, choose Show advanced options.

## Known issues

Robo test currently has the following known limitations:

UI framework support. Robo test is only compatible with apps that use UI elements from the Android UI framework (including View and ViewGroup objects, but excluding WebView objects). If you use Robo test to exercise apps that use other UI frameworks, including apps that use the Unity game engine, the test may exit without exploring beyond the first screen.
Sign-in Captchas. Robo test cannot bypass sign-in screens that require additional user action beyond entering credentials to sign in (such as completing a Captcha).
Scripting. Robo test can't use a script to explore your app by using a predefined sequence of simulated user actions.
Licensing. Robo test does not currently support the App Licensing service offered by Google Play.
Under Additional fields (Optional), enter one or more resource names, and the strings to enter in the corresponding text fields.
