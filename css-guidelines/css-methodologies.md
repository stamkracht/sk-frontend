## Table of contents
- [ITCSS methodology](#itcss-methodology)
  + [Ordering CSS groups](#ordering-css-groups)
  + [Example: ordering CSS groups](#example-ordering-css-groups)
  + [File naming](#file-naming)
  + [Example: file naming](#example-file-naming)
- [BEM methodology](#bem-methodology)
  + [Example: BEM methodology](#example-bem-methodology)
- [Outside-in methodology](#outside-in-methodology)
  + [Ordering CSS properties](#ordering-css-properties)
  + [Example: ordering CSS properties](#example-ordering-css-properties)
- [Resources](#resources)



## ITCSS methodology
<sup>1</sup>Fully written as Inverted Triangle CSS. It involves visualising your entire CSS project as a layered, upside-down triangle. It's not a framework or library, there is nothing to download or install. It's a fully managed CSS architecture. A collection of principles and metrics by which developers should group and order their CSS in order to keep it scalable, terse, logical, and manageable. <sup>3</sup>The philosophy of ITCSS is to write it in a way that browsers and the design of the language can best utilise, which gives us far better scalability and maintainability than we'd get if we were to write CSS around how a person thinks.

### Ordering CSS groups
1. Settings
    - Global variables.
    - Config switches.
2. Tools
    - Default mixins.
    - Functions.
3. Generic
    - Ground-zero styles.
4. Base
    - Unclassed HTML elements.
5. Objects
    - Cosmetic-free design patterns.
6. Components
    - Complete chunks of UI.
7. Trumps
    - Utilities and overrides.

### Example: ordering CSS groups
```
/css
  ├── 1-settings/
  ├── 2-tools/
  │   ├── functions/
  │   └── mixins/
  ├── 3-generic/
  ├── 4-base/
  ├── 5-objects/
  ├── 6-components/
  ├── 7-trumps/
  │   ├── utilities/
  │   └── overrides/
  └── index.scss
```

### File naming
1. Prefix the file names with their belonging group. This way, it will always be clear where they belong inside the inverted triangle. For example if it's not possible/prefered to follow the directory structure and the file ends up somewere without any context.
2. Whenever a CSS module has multiple words, use the dash to connect them. Only use the dot for seperating the group name from the module name.

### Example: file naming
```
settings.[name-example].scss
functions.[name-example].scss
mixins.[name-example].scss
generic.[name].scss
base.[name].scss
objects.[name-example].scss
components.[name-example].scss
utilities.[name].scss
overrides.[name].scss
```



## BEM methodology
<sup>4</sup>Meaning block, element, modifier. It is a front-end naming methodology. A smart way of naming your CSS classes to give them more transparency and meaning to other developers. They are far more strict and informative, which makes the BEM naming convention ideal for teams of developers on larger projects that might last a while.

### Example: BEM methodology
```
.block {}
.block__element {}
.block--modifier {}
```



## Outside-in methodology
<sup>2</sup>Order CSS properties by how much impact they have on the selected elements or other elements around them. The gist of the technique is to start with big-picture properties which impact stuff outside the element and work in towards the finer details. This is why it's called it the 'Outside-in' method.

### Ordering CSS properties
1. Layout
  1. z-index, 
  2. overflow 
  3. position
  4. float
  5. clear
2. Box model
  1. content
  2. box-shadow
  3. display
  4. width
  5. height
  6. margin
  7. border
  8. border-radius
  9. padding
3. Color
  1. color
  2. background
4. Typography
  1. font-family
  2. font-size
  3. text-align
  4. text-transform
5. Miscellaneous 
  1. cursor
6. Animation 
  1. transition
  2. animation
  3. keyframes

### Example: ordering CSS properties
```css
.selector {
  /* Layout */
  z-index: 10;
  overflow: hidden;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;

  /* Box model */
  box-shadow: 0px 0px 1px #222222;
  display: block;
  width: 100px;
  height: 100px;
  margin: 10px;
  border: 10px solid #222222;
  border-radius: 2px;
  padding: 10px;

  /* Color */
  color: #FFFFFF;
  background: #222222;
  
  /* Typography */
  font-family: sans-serif;
  font-size: 16px;
  line-height: 1.4;
  text-align: right;

  /* Miscellaneous */
  cursor: pointer;

  /* Animation */
  transition: left 0.3s ease-out;
  animation: animate 2s linear;
}

@keyframes animate {
  0% {background: #222222;}
  100% {background: #00FF00;}
}
```



## Resources
1. [Managing CSS Projects with ITCSS](https://www.youtube.com/watch?v=1OKZOV-iLj4 "youtube.com/")
2. [Outside In” — Ordering CSS Properties by Importance](http://webdesign.tutsplus.com/articles/outside-in-ordering-css-properties-by-importance--cms-21685 "webdesign.tutsplus.com/articles/")
3. [Manage large-scale web projects with new CSS architecture ITCSS](http://www.creativebloq.com/web-design/manage-large-scale-web-projects-new-css-architecture-itcss-41514731 "creativebloq.com/web-design/")
4. [Getting your head 'round BEM syntax](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/ "csswizardry.com/2013/01/")
