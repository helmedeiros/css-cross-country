css-cross-country
=================

Code School - Learn the fundamentals &amp; foundational elements of CSS with CSS Cross-Country. Review all the web-styling necessities for front-end efficiency. 

### Level 1

#### External Stylesheets
Refactor the `<head>` tag so that all CSS is instead found on an external stylesheet;

#### ID Selector
Select the slogan only by its ID attribute, then center the text and make it italic;

#### Compound Selector
Add a declaration that selects the `<section>` via both class attributes, removing the border when both are present;

#### Style Specificity
Remove the non-external styles found on the HTML page so that !important is no longer needed to set the `<header>` background in style.css.

#### Floats
Float the `<aside>` to the right and add 10px of margin to its left and bottom sides.

#### Columns
Now let's make the `<article>` a column width the same width as the `<aside>` column and float it left.


### Level 2 - Clear Carving

#### Clearfix
Sometimes clearing is necessary. Floated items can be taller than non-floated content or even All children are floating. For all this cases we can apply 3 ways of clearing. They are:
1.Clear with a subsequent element: Requires sequence to stay intact - breaks if things move; Background / border do not extend. 

```html
    <div>
     <img src="ski.jpg" alt="Skiing!" />
     <p>To successfully ski, simply do not fall.</p>
    </div> 
    <div class="intro">
      <p>Whee!</p>
    </div>
```
```css
    img {
      float: left;
    }
    .intro {
      clear: both;
    }
```

2.Manual clearing: Requires an empty element; Might not be necessary later. 

```html
    <div>
     <img src="ski.jpg" alt="Skiing!" />
     <p>To successfully ski, simply do not fall.</p>
     <div class="clear"></div>
    </div>
```

```css
    .clear {
     clear: both;
    }
```

3.The clearfix. 

```html    
    <div class="group">
     <img src="ski.jpg" alt="Skiing!" />
     <p>To successfully ski, simply do not fall.</p>
    </div>
```
```css
    .group:before, .group:after { content: "";
      display: table; }
    .group :after {
      clear: both; }
    .group {
      zoom: 1; /* IE6&7 */ }
```

##### Challenge
Rather than using `<div class="clear"></div>` to clear floats, refactor this page to use the clearfix method via .group.

#### Nested Selectors
By default nested elements automatically inherit parent styles, but sometimes we expect a different behavior from nested elements. On those cases is very important to know the **specificity rule**(the priority of selectors). Think os specificity as four digits number, where the lowest values are in the amount of elements selectors (a, p, img, div, etc); and the highest values are in the inline selectors. ex.:

######0,0,0,1
```css
    p { color: #fff; }
```

######0,0,1,0
```css
    .intro { color: #98c7d4; }
```

######0,1,0,0
```css
    #header { color: #444245; }
```

######1,0,0,0
```html
    <h1 style="color: #000;">Mogul</h1>
```

##### Challenge
Use a nested selector to make paragraphs only within asides `italic`.

#### Inherited Styles
##### Challenge
For `anchor` tags within `aside paragraphs`, override the inherited `italics` with a `normal` font-style.

#### Specificity
##### Challenge
Refactor the CSS declarations for `.active a` and `.copyright` so that the `!important` rule can be removed.

#### Removing Id Selectors
##### Challenge
Refactor `#home` scoped anchor tags to be scoped to the `.home` class instead, so that the `.button` declaration no longer needs reference to the home class or ID.

### Level 3 - Box Bindings

#### Box Model
When adapting a layout is important to have in mind the box model. Each DOM element has a imaginary diagram with 4 areas (content area, padding area, border area and margin area). 

Total calculated box width = content width + padding width + border width;

ex.: 100px content width + 15px padding width + 10px border width = 125px box width
```css
    .downhill {
        border: 5px solid #fff;
        padding-left: 10px;
        padding-right: 5px;
        width: 100px;
    }
```
##### Challenge
The `<figure>` in our page footer should have a total box `width` of `120px`. Add an appropriate content `width` given its base `padding` and `border`.

#### Box Model Overflow
When adapting a design to its content is important to have in mind that a content could request to be overflow. The css has the `overflow` property that could be set as `visible` / `auto` / `hidden` / `scroll`. the overflow is by default applied for both axis, but is possible to restrict it to each axi using `overflow-x` or `overflow-y`.

##### Challenge
Add an appropriate content height to give the `<figure>` a height of `120px`, hide any `overflow` on the `x-axis`, and add a `scroll bar` on the `y-axis` if necessary. Hint: Use `overflow-x` and `overflow-y` to target the different axes.

#### Positioning
To setup layout positioning, the css, brings the `position` property. It could be set as one of the follow values: `static`, `relative`, `absolute` and `fixed`. Using a value other than `static` causes an object to become a **positioned** element. After became a **positioned element**, the element could use the `top`, `left`, `bottom`, and `right` properties for placement.

#### Relative Positioning
After set as relative, the renders occours in the normal flow, then shifted via positioning properties.

##### Challenge
Anchors with a `.button` class are floated to the right of our `<h3>`, but we'd like them to be centered vertically. Use `relative positioning` to move the button down `3px`.

#### Scoping Position
##### Challenge
We've attempted to position the newsletter paragraph to stick to the bottom of the footer, but it's sticking to the window instead. Add the necessary `positioning` to `<footer>` to scope it.

#### Absolute Positioning
##### Challenge
Use `absolute positioning` to place the `<figure>` in the upper right corner of the footer. Set a `z-index` on `.newsletter` to keep it above `<figure>` after it's positioned.

### Level 4 - Grooming Your Code
#### DRY
In IT world DRY is an acronym for Don't Repeat Yourself. when we're talking about css, there are some places to keep it in mind. 
1. Suppose you want to include a font property in a number of text-related elements, in a not DRY way, you could finished with something like a font-family for each element h1, p also .sale. 

```html
<body>
    <div class="container">
    <h1>Sven's Snowshoe Superstore</h1>
    <p>Our snowshoes are so stylish!</p>
    <a class="sale" href="/sale">View our sales</a>
  </div>
</body>
```
##### NOT-DRY WAY
```css
    h1 {
      font-family: Arial, sans-serif; 
    }
    p {
      font-family: Arial, sans-serif;
    }
    .sale {
      font-family: Arial, sans-serif;
    }
```
##### DRY
###### Selector combination:
```css
    h1, p, .sale {
      font-family: Arial, sans-serif; 
    }
```
###### Target parent element:
```css
    .container {
      font-family: Arial, sans-serif; 
    }
```

##### Challenge
Refactor any repeated declarations and apply them to a single parent container

#### Selector Combination
##### Challenge
Combine selectors that share the same properties into a comma-delimited list.

#### Selector Combination II
##### Challenge
Combine selectors that share the same properties into a comma-delimited list, then override the comma-delimited definition with individual definitions.

#### Shorthand
##### Challenge
Refactor the paragraph properties to use shorthand syntax.

#### Inline
##### Challenge
Use `display: inline` to make the `nav` list items display horizontal with `right` and `left` margins of `5px`. Be sure to use the shorthand syntax for `margin`.

#### Horizontal Centering
##### Challenge
Give the unordered list in `<nav>` a `width` of `250px` and `center` it `horizontally` within its parent container. Use shorthand syntax where appropriate.