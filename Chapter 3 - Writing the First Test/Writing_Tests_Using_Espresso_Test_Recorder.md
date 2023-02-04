# Espresso Test Recorder

- The Espresso Test Recorder tool allows you to create UI tests for your app without writing any test code.

- By recording a test scenario, you can record your interactions with a device and add assertions to verify UI elements in screenshots of the application. 

- Espresso Test Recorder then takes the saved recording and automatically generates a corresponding UI that can be run to test your application.


## Recording your first test

1. Go to Menu Run > Record Espresso Test
<img src="https://github.com/nihalalfred/Android-Test-Automation-with-Espresso/blob/main/Screenshots/RecordEspressoTest.png" height="600" width="1000" >

2. Once you tap on it you will see the app under test build along with the TestRecorderapp which will record your actions you will make on the app. (Default will show as "No actions recorded yet")
<img src="https://github.com/nihalalfred/Android-Test-Automation-with-Espresso/blob/main/Screenshots/TestRecorderApp.png" height="600" width="1000" >

3. Now type something in the text field on the app and tap on the button Change Text
<img src="https://github.com/nihalalfred/Android-Test-Automation-with-Espresso/blob/main/Screenshots/RecordingYourActions1.png" height="600" width="1000" >

4. Now you will notice the TestRecorderApp capturing all your actions.

5. Tap on the Add Assertion button on the TestRecorderApp which will capture a screenshot of your app state.
<img src="https://github.com/nihalalfred/Android-Test-Automation-with-Espresso/blob/main/Screenshots/InsertingAssertions.png" height="600" width="1000" >

6. You can now hover over any of the elements (which will be highlighted in red) in the captured screenshot and select it which will automatically populate the assertion detail for you which you can save by tapping on the Save Assertion button
<img src="https://github.com/nihalalfred/Android-Test-Automation-with-Espresso/blob/main/Screenshots/RecordingYourActions2.png" height="600" width="1000" >

7. Saving it will prompt you to choose a Test Class name and the Test Class language (defaulted to Java)
<img src="https://github.com/nihalalfred/Android-Test-Automation-with-Espresso/blob/main/Screenshots/SavingYourRecordedTests.png" height="600" width="1000" >

8. Once you save it you will find the file created which you can locate and tap on the Double Green Arrow to run and execute the test and view the Test Results. 
<img src="https://github.com/nihalalfred/Android-Test-Automation-with-Espresso/blob/main/Screenshots/RunningRecordedTests.png" height="600" width="1000" >

## Limitations of Espresso Test Recorder

1. Currently you can only record a single test method per class.
2. UI assertions seem limited to your own UI Code.
3. Handling background tasks need to be done manually.

