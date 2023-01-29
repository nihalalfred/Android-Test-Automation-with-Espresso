# Espresso Test Recorder

- The Espresso Test Recorder tool allows you to create UI tests for your app without writing any test code.

- By recording a test scenario, you can record your interactions with a device and add assertions to verify UI elements in screenshots of the application. 

- Espresso Test Recorder then takes the saved recording and automatically generates a corresponding UI that can be run to test your application.


## Recording your first test

1. Go to Menu Run > Record Espresso Test
2. Once you tap on it you will see the app under test build along with the TestRecorderapp which will record your actions you will make on the app. (Default will show as "No actions recorded yet")
3. Now type something in the text field on the app and tap on the button Change Text
4. Now you will notice the TestRecorderApp capturing all your actions.
5. Tap on the Add Assertion button on the TestRecorderApp which will capture a screenshot of your app state.
6. You can now hover over any of the elements (which will be highlighted in red) in the captured screenshot and select it which will automatically populate the assertion detail for you which you can save by tapping on the Save Assertion button
7. Saving it will prompt you to choose a Test Class name and the Test Class language (defaulted to Java)
8. Once you save it you will find the file created which you can locate and tap on the Double Green Arrow to run and exectute the test.