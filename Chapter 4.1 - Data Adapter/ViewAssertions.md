# ViewAssertions

`ViewAssertions` are used to assert that the actual view found using `ViewMatchers` and the expected views are the same.

Examples:

```
matches(Matcher)
doesNotExist()
selectedDescendantsMatch(...)
```

#### LAYOUT ASSERTIONS
```
noEllipseizedText(Matcher)
noMultilineButtons()
noOverlaps([Matcher])
```

#### POSITION ASSERTIONS
```
isLeftOf(Matcher)
isRightOf(Matcher)
isLeftAignedWith(Matcher)
isRightAlinedWith(Matcher)
isAbove(Matcher)
isBelow(Matcher)
isBottomAlignedWith(Matcher)
isTopAlignedWith(Matcher)
```


### Creating a Custom View Matcher

A custom matcher is a very powerful concept used to extend the framework as well as to customize the framework to our taste.

Espresso provides two classes to write new matchers:

1. `TypeSafeMatchers` 

2. `BoundedMatcher`




