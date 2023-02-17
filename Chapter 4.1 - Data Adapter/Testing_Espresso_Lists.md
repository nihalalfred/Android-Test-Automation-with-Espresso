# Testing Espresso Lists

Espresso offers two types of list mechanisms to scroll or interact with a particular item

1. AdapterView

2. RecyclerView


## AdapterView

AdapterView is a ViewGroup that displays items loaded into an adapter.

The most common type of adapter comes from an array-based data source.

The method `onData()` provides a matcher against the data backing the view you would like to match.


```
onData(ObjectMatcher)
    .DataOptions
    .perform(ViewAction)
    .check(ViewAssertion);
```

#### DataOptions
```
inAdapterView(Matcher)
atPosition(Integer)
onChildView(Matcher)
```

Espresso will do all the work of finding the row in the Adapter object and making the item visible in the viewport.


## How does AdapterView Work?

- AdapterView renders the user interface dynamically depending on the amount of data available in the underlying data source. 

- AdapterView renders only the minimum data necessary to draw the visible area of the screen. 

- This is done to conserve memory and to maintain UI responsiveness even if the underlying amount of data is large.





