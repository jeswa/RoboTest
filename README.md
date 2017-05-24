# RoboTest


Robo test is a test tool that is integrated with Firebase Test Lab for Android. Robo test analyzes the structure of your app's UI and then explores it methodically, automatically simulating user activities. Unlike the UI/Application Exerciser Monkey test, Robo test always simulates the same user activities in the same order when you use it to test an app on a specific device configuration with the same maximum depth and timeout settings. This lets you use Robo test to validate bug fixes and test for regressions in a way that isn't possible when testing with the UI/Application Exerciser Monkey test.

Robo test captures log files, saves a series of annotated screenshots, and then creates a video from those screenshots to show you the simulated user operations that it performed. These logs, screenshots, and videos can help you to determine the root cause if your app crashes, and can also help you to find issues with your app's UI.

## Configuring Robo test

You can configure Robo test in multiple ways, as follows:

Maximum depth. You can configure how deeply Robo test explores your app by setting the maximum depth of the test. The maximum depth setting tells the test how thoroughly it should explore a particular branch of your app's UI before returning to the root of the UI (the main screen) to explore another branch. The default value for maximum depth is 50, and any value less than 2 prevents the test from exploring the app beyond the main screen.
Timeout. Depending on the complexity of your app's UI, Robo test might take five minutes or more to complete a thorough set of UI interactions. We recommend setting the test timeout to at least 120 seconds (2 minutes) for most apps, and 300 seconds (5 minutes) for moderately complex apps. The default value for timeout is 300 seconds (5 minutes) for tests run from Android Studio and the Google Developer Console, and 1500 seconds (25 minutes) for tests run from the gcloud command line.
If your app has both a UI with significant depth and multiple UI branches that Robo test should explore, then you should do one of the following to ensure that Robo test explores your app thoroughly:

Set a high value for timeout so that Robo test is able to explore multiple UI branches.
Set a low value for maximum depth so that Robo test completes some exploration of each UI branch.
