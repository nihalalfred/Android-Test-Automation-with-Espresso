# Recycler View

- The `RecyclerView` Widget is a more advanced and flexible version of `ListView`.

- `RecyclerView` objects works differently than `AdapterView` objects, so `onData()` cannot be used to interact with them. 

To interact with `RecyclerView` using Espresso, you can use the `espresso-contrib package`, which has a collection of `RecyclerViewActions` that can be used to scroll to positions or to perform action on items:

- `scrollTo()` - Scrolls to the matched view.
- `scrollToPosition()` - Scroll to a specific position.
- `actionOnItem()` - Performs a View Action on a matched View.
- `actionOnItemAtPosition()` - Performs a ViewAction on a view at a specific position.

## Test Code Example

```java
@Test
    public void scrollToItem_checkItsText(){
        onView(withId(R.id.recyclerView))
                .perform(RecyclerViewActions.
                        actionOnItemAtPosition(itemText, click()));

        onView(withText(displayedText))
                .check(matches(isDisplayed()));

    }

```

1. **`onView(withId(R.id.recyclerView))`:**

Selects a view with the specified resource ID `(R.id.recyclerView)`. 

This is typically a `RecyclerView`, a flexible view for providing a limited window into a large data set.

2. **`.perform(RecyclerViewActions.actionOnItemAtPosition(itemText, click())):`**

Performs an action on an item at a specific position in the `RecyclerView`.

`itemText`: This represents the position of the item in the RecyclerView. 

The actual value of itemText may depend on how your `RecyclerView`` is populated, but it seems to be used as a position identifier.

`click():` Performs a click action on the item at the specified position.

3. **`onView(withText(displayedText)):`**

Selects a view with the specified text content (displayedText).

4. **`.check(matches(isDisplayed())):`**

Checks if the selected view is displayed on the screen.

`matches(isDisplayed())` is asserting that the view with the specified text is currently visible on the screen.

In summary, this Espresso test scrolls to a specific item in a `RecyclerView`, clicks on it, and then checks if a view with the specified text (displayedText) is displayed on the screen. 

This type of test is common for verifying that scrolling and clicking on items in a RecyclerView produce the expected UI changes.