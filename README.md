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
