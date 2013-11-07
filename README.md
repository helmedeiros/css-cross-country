css-cross-country
=================

Code School - Learn the fundamentals &amp; foundational elements of CSS with CSS Cross-Country. Review all the web-styling necessities for front-end efficiency. 

### Level 1

#### External Stylesheets
Refactor the <head> tag so that all CSS is instead found on an external stylesheet;

#### ID Selector
Select the slogan only by its ID attribute, then center the text and make it italic;

#### Compound Selector
Add a declaration that selects the <section> via both class attributes, removing the border when both are present;

#### Style Specificity
Remove the non-external styles found on the HTML page so that !important is no longer needed to set the <header> background in style.css.

#### Floats
Float the <aside> to the right and add 10px of margin to its left and bottom sides.

#### Columns
Now let's make the <article> a column width the same width as the <aside> column and float it left.


### Level 2 - Clear Carving

Sometimes clearing is necessary. Floated items can be taller than non-floated content or even All children are floating. For all this cases we can apply 3 ways of clearing. They are:
1.Clear with a subsequent element: Requires sequence to stay intact - breaks if things move; Background / border do not extend. 
ex.: 
    <div>
     <img src="ski.jpg" alt="Skiing!" />
     <p>To successfully ski, simply do not fall.</p>
    </div> 
    <div class="intro">
      <p>Whee!</p>
    </div>

    img {
      float: left;
    }
    .intro {
      clear: both;
    }

2.Manual clearing: Requires an empty element; Might not be necessary later. 
ex.: 
    <div>
     <img src="ski.jpg" alt="Skiing!" />
     <p>To successfully ski, simply do not fall.</p>
     <div class="clear"></div>
    </div>

    .clear {
     clear: both;
    }

3.The clearfix. 
ex.:
    <div class="group">
     <img src="ski.jpg" alt="Skiing!" />
     <p>To successfully ski, simply do not fall.</p>
    </div>

    .group:before, .group:after { content: "";
      display: table; }
    .group :after {
      clear: both; }
    .group {
      zoom: 1; /* IE6&7 */ }

#### Clearfix
Rather than using <div class="clear"></div> to clear floats, refactor this page to use the clearfix method via .group.

#### Nested Selectors
#### Inherited Styles
#### Specificity
#### Removing Id Selectors