# ViewMatchers

- The purpose of a matcher is to match a view using different attributes of a view such as ID, text, or availability of a child view.

- Each matcher matches a particular attribute of the view and applies to a particular type of view.

- The Espresso framework makes extensive use of the _**Hamcrest**_ library and extends it whenever necessary to provide simple and extendable matchers.


Examples:

#### USER PROPERTIES

```
withId(...)
withText(...)
withTagKey(...)
withTagValue(...)
hasContentDescription(...)
withContentDescription(...)
withHint(...)
withSpinnerText(...)
hasLinks()
hasEllipsizedText()
hasMultilineText()
```

#### UI PROPERTIES

```
isDisplayed()
isCompletelyDisplayed()
isEnabled()
hasFocus()
isClickable()
isChecked()
isNotChecked()
withEffectiveVisibility(...)
isSelected()
```

#### OBJECT MATCHER

```
allOf(Matchers)
anyOf(Matchers)
is(...)
not(...)
endsWith(String)
startsWith(String)
instanceOf(Class)
```

#### HIERARCHY

```
withParent(Matcher)
withChild(Matcher)
hasDescendant(Matcher)
isDescendantOfA(Matcher)
hasSibling(Matcher)
isRoot()
```

#### INPUT

```
supportsInputMethods(...)
hasIMEAction(...)
```

#### CLASS

```
isAssignableFrom(...)
withClassName(...)
```

#### ROOT MATCHERS

```
isFocusable()
isTouchable()
isDialog()
withDecorView()
isPlatformPopup()
```

#### SEE ALSO

- Preference matchers
- Cursor matchers
- Layout matchers