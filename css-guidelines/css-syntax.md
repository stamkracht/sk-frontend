## Table of contents
- [General](#general)
- [Specificity](#specificity)
  + [Example: specificity](#example-specificity)
- [Selectors](#selectors)
  + [Example: selectors](#example-selectors)
- [Naming selectors](#naming-selectors)
  + [Example: naming selectors](#example-naming-selectors)
- [Declarations](#declarations)
  + [Example: declarations](#example-declarations)
- [One-liners](#one-liners)
  + [Example: one-liners](#example-one-liners)
- [SCSS](#scss)
  + [Example: SCSS](#example-scss)
- [Quick-start template](#quick-start-template)
- [Further Reading](#further-reading)



## General
- Meaningful use of whitespace.
- Use 2 or 4 space indentation (preferred: 2).



## Specificity
- Prevent using IDs for styling purposes.
- Keep selectors short and strive to limit the number of elements in each selector to 2 or 3 (preferred: 2).
- Only chain selectors for the use of states.
- Use '!important' in the overrides of the inverted triangle.

#### Example: specificity
```css
/* not using IDs and limited the number of elements to 2. */
.selector-1 .level-1 {
  position: relative;
  display: none; 
}

/* chaining the selectors because it's a state. */
.selector-1.state-active {
  display: block;
}
```



## Selectors
- Use classes over generic element tag for optimum rendering performance.
- Each selector on a new line.
- The opening brace on the same line as the last selector.
- A space before the opening brace.
- Closing brace on a new line.

#### Example: selectors
```css
.selector-1,
.selector-2,
.selector-3 .selector-3__element {
  /* properties here */
}
```



## Naming selectors
- Use the BEM methodology.
- Prefix selectors to add more context.
  + Prefix objects with 'o-'.
  + Prefix components with 'c-'.
  + Prefix utilities with 'u-'.
  + Prefix javascript hooks with 'js-'.

#### Example: naming selectors
```css
.o-object-name {}
.c-component-name {}
.u-utility-name {}
.js-name {}
```



## Declarations
- Each declaration on a new line.
- A space after the property–value delimiting colon.
- End each declaration with a trailing semi-colon.
- Don't write prefixes (let PostCSS Autoprefixer deal with that).

#### Example: declarations
```css
.selector-1 {
  position: relative;
  display: block;
  width: 50px;
  height: 50px;
}
```



## One-liners
Selectors with 1 declaration can be written on 1 line.

#### Example: one-liners
```css
.selector-1 { display: block; }
```



## SCSS
- Seperate modules in different files.
- Use the '&' symbol to attach states to the selector.
- Keep it simple stupid (don't overuse functions and mixins).
- Avoid nesting more than 2 level deep.
- One empty line between closely related selectors.

#### Example: SCSS
```
.selector-1 {
  display: none;
  width: 50px;
  height: 50px;

  &:hover { display: block; }

  &.state-active {
    position: relative; 
    display: block; 
  }
}
```



## Quick-start template
```css
/* $ Module name.
   ======================================== */
.block,
.block__element,
.block__element--modifier {
  display: block;
}

/* simple comment. */
.block {
  display: block;
}
```



## Further Reading
Obviously the guidelines could be even more strict. But they are here to help you, and guide you to creating and maintaining a scalable codebase. The guidelines are inspired by a couple of popular styleguides. Feel free to read further.

- [High-level advice and guidelines for writing sane, manageable, scalable CSS](http://cssguidelin.es/ "cssguidelin.es/")
- [Code Guide by @mdo](http://codeguide.co/#css "codeguide.co/#css")
- [Principles of writing consistent, idiomatic CSS](https://github.com/necolas/idiomatic-css "github.com/necolas/idiomatic-css")
