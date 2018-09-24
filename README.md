# SmartBeijing

### splash interface(SplashActivity.java)
- ImageView + ShareUtil
  - The spash interface reads the shared file to determine whether it is the first visit.

### Navigation page(GuideActivity.java)
- Used viewPager to navigate the interface toggle.
- The display button will display if it is the last image, otherwise the display button will be hidden.
  - addOnPageChangeListener
    - onPageSelected used to select current page

### Sideslip menu
- Imported third party Library
  - error solusion
    - find menu_library file in build.gradle file
    - edit dependencies and buildToolsVersion
    - Change the consistency with the app directory.
 - Imported the menu_library library into the current project
   - Used project structure to find APP
   - dependencies (module dependencies)
 - Initialized sideslip menu
   - inherited SlidingFragmentActivity
   - Set the basic properties of menu display
   - Used Fragment to fill menu and main page

### Main page
  - homeFragment interface
    - customized viewpager at the top
    - customized radioGroup at the bottom
   - Defined a BasePager
     - Put all child pager in a List collection.
   - Added adapter to viewPager
      - PagerAdapter
      - returned all pager
  - Set up monitor for button
    - setOnCheckedChangeListener
    - Jumped to the corresponding viewpager based on the currently selected button.
      - viewpager.setCurrentItem(0);

### Perfect interface display
  - Initialized title
    - Defined a method to initialize the title for basepager.
    - Extracted the title separately.

### Optimized viewPager
  - Shielded slip events
    - onInterceptTouchEvent (false)
    - onTouchEvent (false)
  - Removed preload
    - DEFAULT_OFFSCREEN_PAGES =0

### Access to news center data
  - Imported xutil Library
    - If there was a minimum version error, modify minSdkVersion 7 in build.gradle
  - Method of setting up data in basepager
  - Xutil found no HttpMethod
    - imported org.apache.http.legacy.jar

### parsed data(json)
  - Imported Gson Toolkit
  - Tool class converted JSON file to JavaBean
  - Parsed JavaBean in the news center page to get data

### Displayed the menu title that was parsed.
  - switchMenuFragment
  - Different menus pointing to different menuFragment

### Clicked the different menu to display the specified page.
  - Sideslip menu to display title

### News content interface
  - Pointer displayed
    - Remember to add themes to androidManifest.
  - Added the top picture.
  - Added listview news items
  - Added a timing scroll to the top news.
    - When using handler, remember to empty messages when switch pages.
      - protected void onDetachedFromWindow()
      - handler.removeCallbacksAndMessages(null);
