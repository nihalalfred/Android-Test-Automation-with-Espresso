# Basic Test Structure
To create the basic test structure of your first Espresso UI test class we would need to perform the following actions for the text box element:

- Open the sample application and enter text into the EditText view.

- Perform a click on the "CHANGE TEXT" button.

- Assert that the view updated correctly.


## Steps to create your first test class

1. To create our first test case we need to go to the `(androidTest)` package which contains the previous test case that we created with the `Android Espresso Test Recorder`.

2. Right-click on this package and select a new Java class.

3. The class name can be anything. For this example we are going to call it as `ChangeTextTest`

4. Once the test class is created the first step is add an annotation to run this test using the AndroidJUnitRunner. 

    The annotation `@RunWith` will take `AndroidJUnit4.class` as an argument as follows:


```java
package com.example.android.testing.espresso.BasicSample;

import androidx.test.ext.junit.runners.AndroidJUnit4;

import org.junit.runner.RunWith;

@RunWith(AndroidJUnit4.class)
public class ChangeTextTest {
}
```
Notice that after filling in the `@RunWith` annotation a green icon appears next to the test class that enables us to run our test.


5. The next step is to an activity `test rule`.

<span style="color:gold">**A test rule allows us to initialize, open, start, or close an activity or screen in the application.**</span>

Let’s do this now by adding the `@Rule` annotation to a new method within the test class called `ActivityScenarioRule`.

``` 
Note: "ActivityTestRule" is depreciate now and is replaced by 
"ActivityScenarioRule".
```

"MainActivity" designates the active screen to be initialized at the start of the test. 

"MainActivity.class" needs to be passed as an argument when instantiating a new instance of "ActivityScenarioRule".

```java
package com.example.android.testing.espresso.BasicSample;

import androidx.test.ext.junit.rules.ActivityScenarioRule;
import androidx.test.ext.junit.runners.AndroidJUnit4;

import org.junit.Rule;
import org.junit.runner.RunWith;

@RunWith(AndroidJUnit4.class)
public class ChangeTextTest {
    @Rule public ActivityScenarioRule <MainActivity> activityScenarioRule
            = new ActivityScenarioRule<>(MainActivity.class);
}
```

6. Next we would need to create our test method. We can do that by adding the annotation `@Test` from JUnit and give it a name `changeText_sameActivity`

```java
package com.example.android.testing.espresso.BasicSample;

import androidx.test.ext.junit.rules.ActivityScenarioRule;
import androidx.test.ext.junit.runners.AndroidJUnit4;

import org.junit.Rule;
import org.junit.Test;
import org.junit.runner.RunWith;

@RunWith(AndroidJUnit4.class)
public class ChangeTextTest {
    @Rule public ActivityScenarioRule <MainActivity> activityScenarioRule
            = new ActivityScenarioRule<>(MainActivity.class);

    @Test
    public void changeText_sameActivity () {
        
    }
}
```
7. Now we need the elementIds in order to write our Espresso test script. 

    We can find this out by running the `Layout Inspector` after you have build the app.

    Our first test would be a simple one where you will be first
    
    a. Finding the textField, click it and then input a string into it
    
    b. Next we will need to find the ChangeText Button and then click on it

    c. Observe and assert that the entered string is being displayed replacing the earlier text.

    Using the Layout Inspector we have found the elementIDs for the above steps in the Attributes:

    a. `@id/editTextUserInput`

    b. `@id/changeTextBt`

    c. `@id/textToBeChanged`

8. Having the elementIDs we can proceed in writing our Espresso test script.

The basic script structure will involve 3 steps:

a. `Locate` the elements.

b. `Perform` actions on the elements.

c. `Assert` or `verify` the element state.

- Locating elements requires the use of a method `onView()`

    - Usually IDs are stored in the resources file of the Android application.

    - So you can start locating these id with the help of autocomplete function and find these elements.

- To perform an action on an elementID you can use `.perform()`.

    -   Since we are going to first type a text in the text field we can do that by the following action. The text is an string entry so it has to be within " ".
    
         `.perform(typeText("Hello My Friend"));`

    -  We also want to ensure we are dismising the soft keyboard after this action. We can do that by:

        `closeSoftKeyboard();`

- Similary we would be using `onView()` to locate the change text button.

- The last step would be find and verify that the new label that is being displayed after tapping on the change text button matches the entered string.

    - We can do that by `.check(matches(withText"Hello My Friend"));`

Now your first complete Espresso test script will look something like this:

```java
    @Test
    public void changeText_sameActivity () {
        onView(withId(R.id.editTextUserInput))
                .perform(typeText("Hello My Friend"));

        closeSoftKeyboard();

        onView(withId(R.id.changeTextBt))
                .perform(click());

        onView(withId(R.id.textToBeChanged))
                .check(matches(withText("Hello My Friend")));

    }
```

9. Now you can run your tests by clicking on the green play button on the left of the test defination method.

    👏 👏

    <span style="color:gold">**Congratulations! You have just finished writing your first test script using Espresso and Java.**<span> 

     🔥 🔥


