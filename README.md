# CSS Best Practices

This is a guideline of best practices that we can apply to our front-end project.
Some of these recommendations are applied for CSS pre-processors such as [Sass](https://sass-lang.com/), [Less](http://lesscss.org/) and [Stylus](https://stylus-lang.com/).
These tips are based on CSS documentation, books, articles and professional experience.

## Table of Contents

1. [Follow conventions](#follow-conventions)
2. [Follow a CSS methodology](#follow-a-CSS-methodology)
3. [Lint the CSS files](#lint-the-css-files)
4. [Alphabetize CSS properties](#alphabetize-css-properties)
5. [Cross-browser compatibility](#cross-browser-compatibility)
6. [Prefer CSS over JavaScript](#prefer-css-over-javascript)
7. [Comment the CSS](#Comment-the-css)
8. [Avoid undoing styles](#avoid-undoing-styles)
9. [Avoid magic numbers](#avoid-magic-numbers)
10. [Avoid qualified selectors](#avoid-qualified-selectors)
11. [Avoid hard-coded values](#avoid-hard-coded-values)
12. [Avoid brute forcing](#avoid-brute-forcing)
13. [Avoid dangerous selectors](#avoid-dangerous-selectors)
14. [Avoid extra selectors](#avoid-extra-selectors)
15. [Avoid reactive !important](#avoid-reactive-important)
16. [Avoid IDs](#avoid-ids)
17. [Avoid loose class names](#avoid-loose-class-names)
18. [Avoid string concatenation for classes](#avoid-string-concatenation-for-classes)
19. [Avoid duplicated key selectors](#avoid-duplicated-key-selectors)
20. [Avoid using inline styles](#avoid-using-inline-styles)
21. [Avoid classes in wrong components](#avoid-classes-in-wrong-components)
22. [Avoid @mixin everywhere](#avoid-mixin-everywhere)
23. [Avoid @extend everywhere](#avoid-extend-everywhere)
24. [Avoid shorthand syntax everywhere](#avoid-shorthand-syntax-everywhere)
25. [Avoid too many font files](#avoid-too-many-font-files)
26. [Use multiple classes](#use-multiple-classes)
27. [Use nested declarations](#use-nested-declarations)
28. [Use "Margin: 0 auto" to center layouts](#use-margin-auto-to-center-layouts)
29. [Use Hex Code instead of Name Color](#use-hex-code-instead-of-name-color)
30. [Use a CSS reset](#use-a-css-reset)
31. [Use a CSS pre-processor](#use-a-css-pre-processor)
32. [Use a CSS post-processor](#use-a-css-post-processor)
33. [Use a CSS framework](#use-a-css-framework)
34. [Use a design system](#use-a-design-system)
35. [Use relative units](#use-relative-units)
36. [Use CSS variables](#use-css-variables)
37. [Write descriptive media queries](#write-descriptive-media-queries)
38. [Understand Block vs Inline Elements](#understand-block-vs-inline-elements)
39. [Separate global vs local style](#separate-global-vs-local-style)
40. [Minimize expensive properties](#minimize-expensive-properties)
41. [Style to be responsive or at least adaptive](#style-to-be-responsive-or-at-least-adaptive)
42. [Let the content define the size](#let-the-content-define-the-size)
43. [Let the parent take care child position](#let-the-parent-take-care-child-position)
44. [Keep HTML semantics](#keep-html-semantics)
45. [Create the HTML first](#create-the-html-first)
46. [Combine elements with same styles](#combine-elements-with-same-styles)
47. [Modularize the styles](#modularize-the-styles)
48. [Lazy load stylesheets](#lazy-load-stylesheets)
49. [Remove unused CSS](#remove-unused-css)
50. [Minimize the CSS](#minimize-the-CSS)

## Follow conventions

Code conventions are base rules that allow the creation of a uniform code base across an organization.
Following them does not only increase the uniformity and therefore the quality of the code.
[Airbnb CSS/Sass Style Guide](https://github.com/airbnb/css) is very popular and recommended.
We can complete them with [CSS Guidelines](https://cssguidelin.es/) and [Sass Guidelines](https://sass-guidelin.es/).
To make it mandatory, we need a linter, formatter and strong code review.
The code conventions must be dynamic and adaptable for each team and project. It is up to each team to define its convention. Finally, take a few minutes to browse [Awesome Sass](https://github.com/Famolus/awesome-sass).
Awesome Sass is a list of awesome Sass and SCSS frameworks, libraries, style guides, articles, and resources.

## Follow a CSS methodology

CSS methodologies will ensure consistency and future proof our styles.
There are plenty of methodologies out there aiming to reduce the CSS footprint, organize cooperation among programmers and maintain large CSS codebases.
[BEM](http://getbem.com/) (Block, Element, Modifier) was introduced in 2010 as a methodology organized around the idea of dividing the user interface into independent blocks.
Other CSS methodologies are [ITCSS](https://itcss.io/), [OOCSS](http://oocss.org/), [SMACSS](http://smacss.com/), [SUITCSS](https://suitcss.github.io/) and [Atomic CSS](https://acss.io/).

## Lint the CSS files

Linting works by ensuring that we follow the rules that we define for our style and make sure our styles are consistent, well structured, and follow CSS best practices.
We can use [stylelint](https://stylelint.io/) in our CSS projects.
It is very well documented and can be integrated with our favorite IDE.
To ensure all files committed to git don't have any linting or formatting errors, we can use [lint-staged](https://www.npmjs.com/package/lint-staged).
It allows to run linting commands on files that are staged to be committed.

## Alphabetize CSS properties

Anyone has their organization rules. However, what makes sense to you is not for another developer.
Instead, define your rules, use a linter to enforce the same rules for everyone.
[Sass Lint](https://www.npmjs.com/package/sass-lint) and [stylelint](https://www.npmjs.com/package/stylelint) provide rules to organize our CSS.
The specifics of what the linter looks for are up to us, but it can be configured to check everything from syntax errors to making sure our CSS properties are in a strict order.

## Cross-browser compatibility

Cross-browser compatibility is important. CSS browser prefixes are a way for browser makers to add support for new CSS features before those features are fully supported in all browsers.
For example, if we use [PostCSS](https://postcss.org/) with the [Autoprefixer](https://github.com/postcss/autoprefixer) plugin, we can write completely normal CSS without any browser prefixes and let the postprocessor do the rest of the work.
Internally, Autoprefixer relies on a library called [Browserslist](https://github.com/browserslist/browserslist) to figure out which browsers to support with prefixing.

## Prefer CSS over JavaScript

If something we want to do with JavaScript can be done with CSS instead, we use CSS.
Before we try to add JavaScript and even when we add JavaScript, we should consider having CSS making the most of the style and using JavaScript for things like triggers and side effects.
JavaScript is not fault tolerant.
This can be disastrous.
We are much more in control when using JavaScript, but we are also much more responsible.
In general, our applications are faster using CSS instead of JavaScript.

## Comment the CSS

One of the best practices that we can implement for CSS code is by putting a comment for each group of CSS code.
Just like any other language, it's a great idea to comment our code.
Comments are used in CSS to explain a block of code or to make temporary changes during development.
The commented code doesn't execute.
Regarding comments, we have documentation on [how to comment the CSS](https://www.freecodecamp.org/news/comments-in-css/).

## Avoid undoing styles

CSS that unsets styles should start ringing alarm bells right away.
Rulesets should only ever inherit and add to previous ones, never undo.
For more details, see the example below:

```css
h2 {
  font-size: 2em;
  padding-bottom: 0.5em;
  border-bottom: 1px solid #ccc;
}

.no-border {
  padding-bottom: 0;
  border-bottom: none;
}
```

As we go down a stylesheet, we should only ever be adding styles, not taking away.
If we are having to undo styling as we go down in the document, is because we started adding too soon.
In the example, `padding-bottom` and `border-bottom` should be moved from `h2` to `no-border` class.

## Avoid magic numbers

A magic number is a value that is used because it just works.
Magic numbers have several problems associated with them.
They soon become out of date, they confuse other developers, they cannot be explained, they cannot be trusted.
Never, ever use numbers just because they work.

## Avoid qualified selectors

Qualified selectors are ones like:

```css
ul.nav {}

a.button {}

div.header {}
```

Basically, selectors who are needlessly prepended by an element.
These are bad news because they totally inhibit reusability on another element, increase specificity and increase browser workload (decreasing performance).
These are all bad traits.
Those selectors can, and should be:

```css
.nav {}

.button {}

.header {}
```

Which will help us to save actual amounts of code, increase performance, allow greater portability and reduce specificity.

## Avoid hard-coded values

Not unlike magic numbers, hard-coded values are also bad news.
A hard-coded value might be something like this:

```css
h2 {
  font-size: 24px;
  line-height: 32px;
}
```

`line-height: 32px;` here is not cool, it should be `line-height: 1.333;`.
Line heights should always be set relatively to make them more forgiving and flexible.
This may not seem like a massive difference, but on every text element over a large project, this has a big impact.
Hard-coded values are not very future proof, flexible or forgiving, and thus should be avoided.

## Avoid brute forcing

This one is in a similar vein to hard-coded numbers, but a little more specific.
Brute forcing CSS is when we use hard-coded magic numbers and a variety of other techniques to force a layout to work.

```css
.foo {
  margin-left: -3px;
}
```

This is terrible CSS.
This type of CSS is indicative of either a poorly coded layout that requires this kind of manipulation, a lack of understanding of box-model and layout, or both.
Well coded layouts should never need brute-forcing, and a solid understanding of box model, layout and looking at our computed styles more often should mean that we'd rarely end up in a situation like this.

## Avoid dangerous selectors

A dangerous selector is one with far too broad a reach.
An obvious and simple example of a dangerous selector might be:

```css
div {
  background-color: #ffc;
}
```

To give such specific styling to such a generic selector is dangerous.
Our styles will leak out into areas they shouldn't as soon as we start trying to use that element again.
We'll need to start undoing styles (adding more code to take styles away) in order to combat this.

## Avoid extra selectors

It's easy to unknowingly add extra selectors to our CSS that clutters the stylesheet.
One common example of adding extra selectors is with lists.

```css
body #container .someclass ul li {}
```

In this instance, just the `.someclass li` would have worked just fine.

```css
.someclass li {}
```

Adding extra selectors won't bring the end of the world, but they do keep our CSS from being as simple and clean as possible.

## Avoid reactive !important

`!important` is fine and it's a, well, important tool.
However, should only be used in certain circumstances.
`!important` should only ever be used proactively, not reactively.
For example, we will always want errors to be red, so this rule is totally fine.
Where is bad is when it is used reactively, that is, it's used to get someone out of a specificity problem and force things to work.
Using reactively is just a way of circumventing the problems caused by ill-formed CSS.
It doesn't fix any problems, it only fixes the symptoms.

## Avoid IDs

IDs can never be used more than once in a page.
IDs can often have their traits abstracted out into many reusable classes.
An ID is 255 times more specific than one class or infinitely more specific than a class.
They are of no use to anyone and should never be used in CSS.

## Avoid loose class names

A loose class name is one that is not specific enough to define what is its purpose.
For example, imagine a class named `.board`.
Such class name is bad because we can't necessarily glean its purpose based on the class name alone and it is so vague that it might be (accidentally) redefined/reassigned by another developer in a near future.
All this can be avoided by using much stricter class names.
Classes like `.board` and `.user` and suchlike are far too loose, making them hard to quickly understand, and easy to accidentally reuse/override.
[BEM](https://en.bem.info/) helps us in this task.

## Avoid string concatenation for classes

Sass allows us to concatenate strings in our class names with `&`.
The obvious benefit is that we must write our foo namespace only once is certainly very DRY.

```css
.foo {
  color: red;
  &-bar {
    font-weight: bold;
  }
}
```

One less obvious downside, however, is the fact that the string `foo-bar` now no longer exists in our source code.
Searching our codebase for `foo-bar` will return only results in HTML.
It suddenly became a lot more difficult to locate the source of `.foo-bar's` styles.

## Avoid duplicated key selectors

The key selector is the selector that gets targeted/styled.
It is often, though not always, the selector just before your opening curly brace.

```css
header.btn{}

modal.btn{}

sidebar.btn{}
```

Aside from the fact that a lot of that is just generally pretty poor CSS, the problem is that `btn` is defined many times.
So, there is no Single Source of Truth telling what `btn` look like and there has been a lot of mutation meaning that the class has many different potential outcomes.

## Avoid using inline styles

[Inline styles](https://www.w3schools.com/css/css_howto.asp) are the style attribute in the HTML tags.
We should avoid using it because it mixes up content and presentation, which can lead to more trouble.
Inline styles are considered as bad practice due to poor scalability and maintainability.
It leads to messy code where each HTML file will need to be updated in the event of a style change, instead of a global change in a single external stylesheet.
As a rule of thumb, define all styles in the CSS files.

## Avoid classes in wrong components

If we need to style something differently because of its context, where should we put that additional CSS?
In the file that styles the thing?
Or in the file that controls that context?
We should do our best to group our styles based on the subject (i.e. the key selector).
For example, it's much more convenient to have the context of all of our buttons in one place.
This makes it much easier to move all of the button styles onto a new project, but more importantly it eases cognitive overhead.
You're familiar with the feeling of having ten files open in your text editor whilst just trying to change one small piece of styling.
As a simple rule of thumb, ask yourself the question am I styling `x` or am I styling `y`?
If the answer is `_`, then your CSS should live in `_`; if the answer is `_`, it should live in `.xx.cssyy.css`.

## Avoid @mixin everywhere

When we don't have to use mixins, just don't do it.
When we use mixins, they have to be well-structured and maintained in a rigorous way.
Using mixins for no good reason is the best way to get lost when the project grows.
They can cause side effects and become hard to update when they are used in many places.
Mixins are here to avoid repeating yourself by keeping a Single Source of Truth.
Also, we don't have to use mixins to prefix CSS properties because we have plugins like [Autoprefixer](https://github.com/postcss/autoprefixer).

## Avoid @extend everywhere

It's not absolutely, always, definitely bad, but it usually is.
The problems with `@extend` are manifold, but to summarize:

- It's actually worse for performance than mixins are;
- It's greedy. Sass will `@extend` every instance of a class that it finds, giving us crazy-long selector chains;
- It moves things around your codebase. Source order is vital in CSS, so moving selectors around your project should always be avoided;
- It obscures the paper-trail. `@extend` hides a lot of complexity in our Sass.

## Avoid shorthand syntax everywhere

Typically, we would view [shorthand syntax](https://csswizardry.com/2016/12/css-shorthand-syntax-considered-an-anti-pattern/) as a benefit because we have fewer keystrokes, fewer lines of code, less data over the wire.
However, it comes with a rather troublesome side effect.
It often unsets other properties that we never intended to modify.
So, always consider the longhand.
It might be more keystrokes, it might be more repetitive, it might be less DRY, but it's more accurate.
Only write as much as we need and not a single bit more.

## Avoid too many font files

Maybe the designers handed us too many font files which is a red flag.
A website with too many fonts can be chaotic and confusing, so we should only include the necessary fonts for the page.
Fonts can take time to load and be applied and when we have too many fonts.
By default, font requests are delayed until the render tree is constructed, which can result in delayed text rendering.
It is recommended to [optimize WebFont loading and rendering](https://web.dev/optimize-webfont-loading).

## Use multiple classes

Sometimes it's beneficial to add multiple classes to an element.
Let's say that we have a `<div>` "box" that we want to display a warning and we've already a `.warning` class in our CSS.
We can simply add an extra class in the declaration, like so:

```html
<div class="box warning"></div>
```

We can add as many classes as we'd like (space separated) to any declaration.

## Use nested declarations

Using CSS preprocessor not only adds some useful functions to our toolset, but also helps with code organization.
The best example is styles' declaration nesting.
In Sass it's possible to nest selector in other selectors, so that we can see what's the relation between them.
It's powerful feature, so it can be overused pretty easily.
It´s suggested not to go more than 3 levels deep.
This rule applies both for selectors specificity and selectors nesting in CSS preprocessors.
Going beyond that limit not only increases selector's strength, but also can make reading our code more difficult.

## Use "Margin: 0 auto" to center layouts

Many beginners can't figure out why we can't simply use `float: center;` to achieve that centered effect on block-level elements.
Unfortunately, we'll need to use the `margin: 0 auto`; to center divs, paragraphs or other elements in our layout.
By declaring that both the left and the right margins of an element must be identical, they have no choice but to center the element within its containing element.

## Use Hex Code instead of Name Color

It has been pointed out by experts and professionals that when using "hex code", they found that it is faster for 4-5 runs.
Try a performance test run and check for yourself.
So rather than using the "name color", go for "#hex code" instead.
Besides that, it´s recommended to use naming conventions for our color variables.
Instead of scratching our head about this one every time, we can use [Veli's colorpedia](http://veli.ee/colorpedia/).
This way we'll get to give our colors names that a human can understand.

## Use a CSS reset

Applying a reset stylesheet should be the first step in any app design.
There are several widely-used reset stylesheets available, but the job of each one is the same.
It must standardize the differences between different browsers' default styles and to create a clean slate on which to build our app's design.
To use a CSS reset, all we need to do is include the reset stylesheet file into our web app before applying any other styles.

## Use a CSS pre-processor

Part of the reason that CSS can be difficult to work with is that it lacks many of the standard tools available in every programming language.
For example, there's no way in CSS to specify variables.
It´s recommended to replace CSS with a [CSS pre-processor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_preprocessor), such as Sass.
Pre-processors extend CSS with variables, operators, interpolations, functions, mixins and many more other usable assets.
These features make the CSS structure more readable and easier to maintain.

## Use a CSS post-processor

If feel that there is something wrong while the CSS codes get loaded over the browsers and it seems to be lagging in speed, then there is high time we tried to compress the size of the CSS files.
A lot of elements, including line breaks, white spaces, and even redundant CSS styles might be interfering with our CSS file and delaying our app from loading quicker.
Code minification and compression are often used interchangeably, maybe because they both address performance optimizations that lead to size reductions.
Some of the tools that we can use to get rid of these issues include [PostCSS](https://www.npmjs.com/package/postcss), [cssnano](https://www.npmjs.com/package/cssnano) and [clean-css](https://www.npmjs.com/package/clean-css).

## Use a CSS framework

A CSS framework, such as [Bootstrap](https://ng-bootstrap.github.io/), collects together frequently applied styles into a single stylesheet and implements all of the above best practices for us so that we can spend more time thinking about how to improve the website, rather than on making the CSS more manageable.
As with any tools, CSS frameworks aren't always right for every job, and they can have bad side effects when used incorrectly.
But, learning and using a framework saves time and leads to better results in most cases.

## Use a design system

A design system is a collection of reusable components, guided by clear standards, that can be assembled together to build any number of applications.
A design system allows us to build for the future because it allows us to define our general design rules and specifications, follow an organization, modularize, define best practices, etc.
The reason it is a future proof strategy is that it is much easier to introduce changes, fix and configure things on a global scale.

## Use relative units

We should really try to use relative units.
Things like `em`, `rem`, `%`, `vw`, `vh`, `fr`, etc. Setting fix values with `px` and `pt` should be things for static design although there are cases that call for these value units.
The browser is flexible, so should our website and units.

## Use CSS variables

Variables is one the reasons why people choose pre-processors but they required compiling before use, thus (sometimes), adding an extra layer of complexity.
[CSS variables](https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties) are way better because they stick around when loaded in the browser.
The support is good and it allows us to create a more flexible and reusable UI, without mentioning it helps us create a more powerful design system and features.

## Write descriptive media queries

Media queries are the most important part of responsive website development.
We can define styles for different resolutions and change layout according to user's device.
Due to the many rules' combination, media query can become complex pretty easily.
To make media queries more developer-friendly we can assign it's rules to a variable.
In Sass it's possible to use string as normal CSS code using the interpolation braces.

```scss
$medium: 768px;
$screen-medium-wide: 'only screen and (min-width: #{$medium}) and (max-device-aspect-ratio: 9 / 16)';

@media #{$screen-medium-wide} {
  body {
    font-size: 20px;
  }
}
```

## Understand Block vs Inline Elements

Block elements are elements that naturally clear each line after they're declared, spanning the whole width of the available space.
Inline elements take only as much space as they need, and don't force a new line after they're used.
Here are the lists of elements that are either inline or block:

```html
span, a, strong, em, img, br, input, abbr, acronym
```

And the block elements:

```html
div, h1…h6, p, ul, li, table, blockquote, pre, form
```

## Separate global vs local style

It is recommended to distinguish which styles are meant for any or a set of HTML selectors vs. those meant for something specific.
We should keep all global styles in a separate file (especially when using a preprocessor).
Modern front-end frameworks are the building blocks of our applications' UI.
As visual elements, styling them is a big part of how applications meet our users, and composes the way our brand and product looks and feels.
These frameworks suggest appending specific styles to each component using separate files.

## Minimize expensive properties

The browsers are super-fast, however, on complex websites, there are some painting issues related to setting `box-shadow`, `border-radius`, `position`, `filter`, and even `width` and `height`, especially for complex animations or repetitive changes.
These require the browser to do complex re-calculations and repaint the view again down to every nested child.
The "will-change" is used as a performance boost to tell the browser about how a property is expected to change.
However, its use is a last resort.

## Style to be responsive or at least adaptive

We are creating something to go in the browser which means that people will access it in a variety of device types and sizes.
We should consider improving the experience for these people by considering responsive design.
If the project does not include a responsiveness plan, we should at least try to remain adaptive.
Responsive web design is recommended and rewarded by Google.

## Let the content define the size

Instead of setting the `width` and `height` of a button for example, consider setting some padding for spacing and including a `max-width` instead and `max-height` instead unless the design calls for a strict size.
This approach will reduce layout bugs and create reusable elements.

## Let the parent take care child position

When styling a component meant to be used in the content flow, let the content and inner spacing define the size and do not include things like `position` and `margin`.
Let the container where this component will be used to decide the position and how far apart this component is from others.
This approach, among other benefits, allows us to create reusable elements.

## Keep HTML semantics

It is common to find developers who go around changing their HTML to apply a certain style.
In general, let the styling to CSS and let the HTML structured in a way that makes sense semantically.
There are exceptions to this rule but always ensure that the adopted structure does not go against any [HTML semantic](https://developer.mozilla.org/docs/Glossary/Semantics#semantics_in_html) rules.
Write the HTML first with content in mind, not styling.
Then add CSS and try the best before changing the HTML for styling reasons.

## Create the HTML first

Many designers create their CSS at the same time they create the HTML.
It seems logical to create both at the same time, but actually we'll save even more time if we create the entire HTML mockup first.
The reasoning behind this method is that we know all the elements of our site layout, but we don't know what CSS we'll need with our design.
Creating the HTML layout first allows us to visualize the entire page as a whole and allows us to think of our CSS in a more holistic, top-down manner.

## Combine elements with same styles

Elements in a stylesheet sometimes share properties.
Instead of re-writing previous code, why not just combine them?
For example, the `h1`, `h2`, and `h3` elements might all share the same font and color:

```css
h1,
h2,
h3 {
  font-family: 'Times New Roman', Times, serif;
}
```

We could add unique characteristics to each of these header styles if we wanted (ie. `h1 {size: 2.1em;}`) later in the stylesheet.

## Modularize the styles

We do not need to bundle all CSS in one file unless it will be used.
If a user lands on the home page, only include the styles for that page, nothing else.
We can go so far as to separate style sheets into essential and non-essential styles.
Essential styles are those that once the page loads the user sees them and non-essential styles are those for components that remain hidden like dialog and notifications.
Elements or components that require user action to be displayed.

## Lazy load stylesheets

[Lazy loading](https://web.dev/lazy-loading/) is a technique that defers loading of non-critical resources at page load time.
The portion of fonts, images and video in the typical payload of a website can be significant.
By default, CSS is treated as a render blocking resource, so the browser won't render any processed content until the CSSOM is constructed.
There are many ways to [lazy load the CSS](https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading#css) files and it is often easier when using bundlers like [webpack](https://webpack.js.org/) and playing around with dynamic import.
We can create our own JavaScript CSS loader or we can [defer non-critical CSS](https://web.dev/defer-non-critical-css/) by playing with the `<link>` tag when including stylesheets in our page.

## Remove unused CSS

CSS files can easily gain redundant KBs over time.
Unused CSS just adds dead weight to our applications and contributes to the growth of web page size, so we want to make sure that we have as little excess code as possible.
Aside from slowing down our website's overall performance, excess CSS can cause headaches for developers.
Clean and orderly stylesheets are easier to maintain than disorderly ones.
We can [remove unused CSS](https://www.keycdn.com/blog/remove-unused-css) manually or with tools.
The most popular tools are [PurifyCSS](https://www.npmjs.com/package/purify-css), [PurgeCSS](https://www.npmjs.com/package/purgecss) and [UnCSS](https://www.npmjs.com/package/uncss).

## Minimize the CSS

Before loading the CSS into the browser, minimize it.
We can use a post-processor or make it a simple build process step of our site deployment.
Smaller CSS file will load faster and start to be processed sooner.
We can use tools such as [cssnano](https://www.npmjs.com/package/cssnano) or [clean-css](https://www.npmjs.com/package/clean-css). It can also be integrated with a [webpack plugin](https://webpack.js.org/plugins/css-minimizer-webpack-plugin/).
It uses cssnano to optimize and minify our CSS.
