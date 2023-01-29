# Introduction to Mobile UI Testing

Testing your mobile app is a vital part of the app development process.

Consistent execution of tests against your mobile app verifies:

- app correctness,
- functional behavior, and
- usability prior to public release.


## Native Vs. Cross- Platform Mobile Testing Tools

### Cross-platform testing tool:

Within the mobile space, the term "cross-platform" implies support for all major mobile platforms
including iOS, Android and Windows phones.

Appium is one example which also supports many programming languages.

### Native testing tool:

In contrast, a native tool is developed, released, and supported on a single mobile platform.

Examples include Espresso for Android and XCUITest for iOS.

Espresso supports Java and Kotlin programming languages while XCUITest supports Swift
and Objective-C.

## Android Jetpack

Jetpack is a suite of libraries, tools, and guidance to help developers write high-quality app
easier.

These templates or components help you follow best practices and simplify complex tasks, so you can
focus on the code you care about.

## Different components of Android Jetpack

- Architecture
- UI
- Behaviour
- Foundation -> AndroidX Espresso - > Test (see attached image)

<img src="https://github.com/nihalalfred/Android-Test-Automation-with-Espresso/blob/main/Chapter%201%20-%20Introduction%20to%20Espresso/Android%20Jetpack.png" height="600" width="1000" >

## AndroidX


AndroidX is an improved version of the android support libraries that the android team uses to
develop, test, package, version and release libraries within the Jetpack.


AndroidX includes the following features:

- All packages in AndroidX are in consistent namespace starting with the string AndroidX.
- Unlike the previous support libraries, AndroidX packages are separately maintained and updated.

## Espresso

- Espresso is a testing framework, provided by AndroidX, provides APIs for writing UI tests to
simulate user interactions within a single target app.

- Espresso tests can run on devices running Android 2.3.3 (API level 10) and higher.

- The Espresso testing framework is an instrumentation API and works with the AndroidJUnitRunner
test runner. (This means it would require full android environment [android device and OS] to deploy
and run tests.

- No cross-platform support

- Can be used for integration and performance testing.

- Used with Java and Kotlin.

## How does it work?

- You will have two APKs:
    - The app apk (application under test)
    - The Espresso (instrumentation) test apk.

- After installing the two APKs on the target device:
    - The AndroidJUnitRunner will run the test suite against the application under test in a same
    process such as App Process. (see image attached)
<img src="https://github.com/nihalalfred/Android-Test-Automation-with-Espresso/blob/main/Chapter%201%20-%20Introduction%20to%20Espresso/How%20does%20it%20work.png" height="600" width="1000" >

## Implementing Instrumented UI Tests

- Separate from instrumented Unit tests in different folder (AndroidTest).

- Depends on test runner by passing @RunWith with the class.

- Requires Android environment (emulator or physical device).

## Espresso Features

- A key benefit of using Espresso is that it provides automatic synchronization of test actions with
the UI of the app you are testing.

- Espresso detects when the main thread is idle, so it is able to run your test commands at the
appropriate time, improving the reliability of your tests.

- This capacity also helps you from adding any timing workarounds, such as Thread.sleep() in your
test code.

## Advantages of Espresso

- It is simple to use

- Fast and reliable feedback to developers

- Less flakiness

- Android devs can write UI test scrips easily.
