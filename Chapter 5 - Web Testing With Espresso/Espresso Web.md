# Espresso Web

- Espresso web library gives us the ability to interact with WebView

- Use Espresso-Web to test your hybrid apps.

- We can use the Espresso-Web to fully interact with web elements inside WebView objects.

- Allows to perform ViewActions using Web Drive Atoms.

- The WebDriver framework uses Atoms to find and manipulate web elements programmatically.

- Atoms are used by WebDriver to allow browser manipulation such as findElement() and getElement().

## Test Code

```java
package com.example.android.testing.espresso.web.BasicSample;


import android.content.Intent;

import org.junit.Rule;
import org.junit.Test;
import org.junit.runner.RunWith;

import androidx.test.espresso.web.webdriver.DriverAtoms;
import androidx.test.espresso.web.webdriver.Locator;
import androidx.test.ext.junit.runners.AndroidJUnit4;
import androidx.test.rule.ActivityTestRule;

import static androidx.test.espresso.web.assertion.WebViewAssertions.webMatches;
import static androidx.test.espresso.web.sugar.Web.onWebView;
import static androidx.test.espresso.web.webdriver.DriverAtoms.clearElement;
import static androidx.test.espresso.web.webdriver.DriverAtoms.findElement;
import static androidx.test.espresso.web.webdriver.DriverAtoms.getText;
import static androidx.test.espresso.web.webdriver.DriverAtoms.webClick;
import static org.hamcrest.CoreMatchers.containsString;

@RunWith(AndroidJUnit4.class)
public class WebViewActivityTest {

    @Rule
    public ActivityTestRule<WebViewActivity> mActivity =
    new ActivityTestRule<WebViewActivity>
        (WebViewActivity.class,false,false)
    {
        @Override
        protected void afterActivityLaunched() {
            onWebView().forceJavascriptEnabled();
        }
    };

    @Test
    public void typeText_SubmitForm()
    {
        Intent webFormIntent = new Intent();
        mActivity.launchActivity(webFormIntent);

        //text_input
        //submitBtn
        //response

        onWebView()
            .withElement(findElement(Locator.ID,"text_input"))
            .perform(clearElement())
            .perform(DriverAtoms.webKeys("TAU"));

        onWebView()
            .withElement(findElement(Locator.ID,"submitBtn"))
            .perform(webClick());

        onWebView()
            .withElement(findElement(Locator.ID,"response"))
            .check(webMatches(getText(),containsString("TAU")));
        }
}
```