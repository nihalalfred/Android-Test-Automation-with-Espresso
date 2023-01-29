# Espresso Dependencies
To add or use Espresso in our project, two steps are required.

1. Open the "app/build.gradle" file and add the following lines inside of "dependencies": one for the Espresso core, one for the test runner, and one for the rules:

> androidTestImplementation ‘androidx.test.espresso:espresso-core:3.1.0’

>androidTestImplementation ‘androidx.test:runner:1.1.0’

>androidTestImplementation ‘androidx.test:rules:1.1.0’

Note: 
- Once you add any new dependencies you would need to click `Sync Now` which usually shows up in the upper corner to begin downloading dependencies for Gradle.
- You might also see see some of the dependencies highlighted idenfiying new versions are available. Select the suggested new versions and don't forget to click on `Sync Now` once again.

2. The next step is to add our test runner `"AndroidJUnitRunner"` as the Android default in 

    `"build.gradle (Module: app)"`

    Add the following line to "android.defaultConfig":

    >testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"

