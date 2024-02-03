# Test Examples : Data Adapter


## Using what we have learned in this chapter we are going to write the following tests:

1. Check if the last item is does not exist/displayed on View
2. Scroll to the last item and check if it is completely displayed
3. Scroll to an item text, click on it and check if the clicked text is displayed on the top
4. Scroll to an item text, click on it's toggle and check if the toggle is turned from OFF to ON


To write our tests a bit easier we are going to declare 3 String variables with values and use them. 

For example: 

```java
    private static final String itemText = "item: 30";
    private static final String lastItemID = "item: 99";
    private static final String selectedItemID = "30";
```
    
### Test 1:

```java
@Test
    public void lastItemNotDisplayedTest()
    {
        onView(withText(lastItemID)).check(doesNotExist());
    }
```

1. **onView**: 

This is an Espresso method that indicates you are selecting a view (UI element) for testing.

2. **withText(lastItemID):** 

This is a matcher that specifies the text you are looking for within the selected view. The text is provided by the variable **`lastItemID`**.

3. **.check(doesNotExist()):**

**check:** 
This is another Espresso method that allows you to perform assertions or checks on the selected view.

**doesNotExist():** 
This is an assertion that checks if the view with the specified text (given by **`lastItemID`**) does not exist on the current screen.

Putting it all together, this line of code is checking if there is no view with the text specified by the variable **`lastItemID`** on the current screen. 

The variable **`lastItemID`** likely contains some dynamic content that represents the identifier or text of the last item in a list or some UI element.

In the context of mobile app testing, this code is commonly used to verify that a particular UI element (with the specified text) has been removed or is not present on the screen. It's often used in scenarios where you want to ensure that an item has been successfully deleted or that a particular UI state has been changed.

### Test 2:

```java
@Test
    public  void scrollToLastItemTest()
    {
        onData(hasEntry(equalTo(LongListActivity.ROW_TEXT), is(lastItemID)))
                .check(matches(isCompletelyDisplayed()));
    }
```

1. **onData:**

This Espresso method is used when dealing with `AdapterViews` (like `ListViews` or `GridViews`). It helps in selecting data from these views.

2. **hasEntry(equalTo(LongListActivity.ROW_TEXT), is(lastItemID)):**

`hasEntry` is a Hamcrest matcher that checks if the data associated with a specific key in an Adapter item matches the given value.

`equalTo(LongListActivity.ROW_TEXT)`: This is specifying the key you are looking for, which is likely associated with the text of an item in the Adapter.

`is(lastItemID):` This part is specifying that the value associated with the key (specified above) should be equal to the value held in the variable lastItemID.

3. **.check(matches(isCompletelyDisplayed())):**

`check` is an Espresso method used to perform assertions on the selected data.

`matches(isCompletelyDisplayed()):` This part is asserting that the selected data (likely a view within the `AdapterView`) is completely displayed on the screen. It checks if the view is not partially hidden or obscured.

In summary, this code is checking for a specific data entry in an AdapterView (like a ListView) where the key is associated with the text of an item, and the value is equal to the content of the variable lastItemID. It then verifies that the corresponding view is completely displayed on the screen.

### Test 3:

```java
@Test
    public void clickOnRowTextTest()
    {
        onData(hasEntry(equalTo(LongListActivity.ROW_TEXT), is(itemText)))
                .onChildView(withId(R.id.rowContentTextView))
                .perform(click());
        onView((withId(R.id.selection_row_value)))
                .check(matches(withText("30")));
    }
```

1. **onView((withId(R.id.selection_row_value))):**

This switches the context to the overall view hierarchy and specifies that subsequent actions should be performed on the view with the resource ID `R.id.selection_row_value.` This is outside the context of the `AdapterView` used earlier.

2. **.check(matches(withText("30"))):**

This checks if the view with the resource ID `R.id.selection_row_value` has the text content "30". It's asserting that the text of this view matches the expected value "30".

In summary, the test clicks on a specific item in an `AdapterView`, interacts with a child view within that item, and then checks if another view outside the AdapterView has the expected text "30". This type of test might be checking if clicking on a certain row in a list updates another part of the UI with the expected value.

### Test 4:

```java
@Test
    public void clickToggleButtonTest()
    {
        onData(hasEntry(equalTo(LongListActivity.ROW_TEXT), is(itemText)))
                .onChildView(withId(R.id.rowToggleButton))
                .perform(click())
                .check(matches(isChecked()));
    }
```
1. **.check(matches(isChecked())):**

This part checks if the view's state matches the specified condition. In this case, it checks if the toggle button's state is in the checked state.

**2. matches(isChecked())** 

is asserting that the toggle button is checked after the click action.

In summary, after clicking the toggle button, the test ensures that the button is in the checked state. This is a common pattern for testing the behavior of toggle buttons or checkboxes in a UI.