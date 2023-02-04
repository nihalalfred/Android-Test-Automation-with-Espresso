# Where can we find the Element IDs?

Typically all android app element IDs are located in the "res > layout" folder under the main app package folder. 

_(see attached screenshot)_

# Two ways you can inspect elements

1. UIAutomatorViewer
2. Layout Inspector


## Element Inspection with UIAutomatorViewer

- **UIAutomatorViewer** is a useful GUI tool that can scan and analyze the UI Components of an Android application.

- With **UIAutomatorViewer** you can inspect the UI of an Android application to understand its hierarchy and view different properties like ID, text values and locations of elements.

- **UIAutomatorViewer** is a part of the Android SDK and is accessible after installation under `Android/sdk/tools/bin/uiautomatorviewer.`

> Note: Currently UIAutomatorViewer supports Java 8 but is not working correctly with Java 11.

_see attached Screenshot on how the UIAutomatorViwer looks like_

## Element Inspection with Layout Inspector

- You can find this under Tool menu

- **Layout Inspector** in Android Studio allows you to compare your app layout with design mockups and examine details of its layout at runtime.

- This is useful when your layout is built at runtime rather than entirely in XML.

- When we open the Layout Inspector we see 3 views (see attached screenshots):

        1. Layout Inspector Toolbar.

        2. Screenshot of the app layout as it appears on your device with layout boundaries visible.

        3. Attributes - Properties table where you can find element properties such as the elementID

        4. Component Tree where you can see the Linear Layout of all the elements

