# Recycler View

- The `RecyclerView` Widget is a more advanced and flexible version of `ListView`.

- `RecyclerView` objects works differently than `AdapterView` objects, so `onData()` cannot be used to interact with them. 

To interact with `RecyclerView` using Espresso, you can use the `espresso-contrib package`, which has a collection of `RecyclerViewActions` that can be used to scroll to positions or to perform action on items:

- `scrollTo()` - Scrolls to the matched view.
- `scrollToPosition()` - Scroll to a specific position.
- `actionOnItem()` - Performs a View Action on a matched View.
- `actionOnItemAtPosition()` - Performs a ViewAction on a view at a specific position.

