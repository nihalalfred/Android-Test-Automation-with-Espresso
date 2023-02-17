# Espresso Components

## Espresso provides three components:

1. **ViewMatchers**
2. **ViewActions**
3. **ViewAssertions**

- `ViewMatchers` allows to _**find**_ view in the current view hierachy.

- `ViewActions` allows to _**perform**_ actions on the view (click, scroll, type text).

- `ViewAssertions` allows to _**assert**_ state of a view.

- Method `onView()` is passed a `ViewMatcher` object such as an element ID. 

- Method `perform()` is passed a `ViewAction` object.

- Finally, the assertion Method `check()` is passed a `ViewAssertion` object.


```
onView(ViewMatcher)
    .perform(ViewAction)
    .check(ViewAssertion);
```