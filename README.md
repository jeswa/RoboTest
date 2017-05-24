# RoboTest


Robo test is a test tool that is integrated with Firebase Test Lab for Android. Robo test analyzes the structure of your app's UI and then explores it methodically, automatically simulating user activities. Unlike the UI/Application Exerciser Monkey test, Robo test always simulates the same user activities in the same order when you use it to test an app on a specific device configuration with the same maximum depth and timeout settings. This lets you use Robo test to validate bug fixes and test for regressions in a way that isn't possible when testing with the UI/Application Exerciser Monkey test.

Robo test captures log files, saves a series of annotated screenshots, and then creates a video from those screenshots to show you the simulated user operations that it performed. These logs, screenshots, and videos can help you to determine the root cause if your app crashes, and can also help you to find issues with your app's UI.
