# FontManager
Android Font Manager

### Demo
[Download](https://github.com/Aspsine/FontManager/blob/master/art/demo.apk?raw=true)

### ScreenShot
![demo](https://github.com/Aspsine/FontManager/blob/master/art/screenshot.gif?raw=true)

### How to use
Step 1. Add the JitPack repository to your build file. Add it in your root build.gradle at the end of repositories:
```groovy
allprojects {
  repositories {
  	...
  	maven { url "https://jitpack.io" }
  }
}
```

Step 2. Add the dependency
```groovy
dependencies {
  compile 'com.github.Aspsine:FontManager:-SNAPSHOT'
}
```

Step 3. Load font into memory
Note: If the font files are big, this may take some times (several seconds). You'd better do this asynchronously.
Once the fonts were loaded. It will be cached.
```java
// fonts paths in asserts
String[] FontPaths = {"fonts/Lanehum.ttf", "fonts/OrangeJuice.ttf", "fonts/OrmontLight.ttf", "fonts/WedgieRegular.ttf"};
// load assert fonts into memory
FontManager.getInstance().init(context, FontPaths);
```
Set Typeface
```java
AssetManager assetManager = context.getAssets();
// obtain the Typeface. The 'path' is the font file path in asserts folder
Typeface typeface = FontManager.getInstance().getTypeface(assetManager, path);
// set font
textView.setTypeface(typeface);
```

### What's in Demo

- A FontsUtils is provided for easier use. Please check demo code.
```java
// set font to TextView/EditText/Button or any child class instance of TextView
FontsUtils.setFonts(textView, fontType);
// change font of textView in the viewGroup
FontsUtils.setFonts(viewGroup, fontType)
```

- Customised TextView and EditText widget
```xml
<com.aspsine.fontmanager.demo.FontTextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Hello World!"
    app:textFont="Lanehum" />
```
```xml
<com.aspsine.fontmanager.demo.FontEditText
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Hello World!"
    app:textFont="Lanehum" />
```

- Demonstrate how to load fonts into memory during splash
 [SplashActivity](https://github.com/Aspsine/FontManager/blob/master/app/src/main/java/com/aspsine/fontmanager/demo/SplashActivity.java)

### License

    Copyright 2016 Aspsine. All rights reserved.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
