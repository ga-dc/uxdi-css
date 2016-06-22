# HTML & CSS II 

### Learning Objectives 

- Explain the advantage to separating CSS from HTML
- Explain what selectors are, and how they target HTML elements
- Practice positioning and styling elements
- Use the developer tools to adjust styles
- Know how to use and style a webfont
- Explain the difference between different types of assets
- Exposure to more advanced concepts

### Historcial JANK (5)

In the beginning the web originated out of a need to share text content - there was no CSS. The World Wide Web Consortium (W3C - not to be confused with W3 schools) is the international committee that decides that decides the standards of web languages.

HTML 1.0 only had support text and headings
HTML 2.0 - Released Nov 1995 - added support for images
HTML 3.0 added tables so could share data
People realized that they could use tables to give pages structure and crude layouts
HTML 3.2 added support for colors, fonts, and backgrounds

Browsers read HTML and figure out how to display it. Browsers in order to compete with one another started implementing non-standard elements that enabled web designers to make cooler sites[.](http://toastytech.com/evil/)

#### Exercise (3 / 8)

Go to [dolekemp96](http://www.dolekemp96.org/main.htm) and [spacejam](http://www2.warnerbros.com/spacejam/movie/jam.htm)

- Use the 'inspector' to examine the page.
- What elements are used?
- How are things styled?

### CSS & The Separation of Concerns

CSS was introduced in December of 1996 to separate styles from markup. By separating information about presentation from the content it made it easier to adjust how things looked.

- external, head, inline
90s webpages


### Layout is hard

In print media what you see is what you get. As a print designer you know the size of the page, the amount of content you have, and the fonts.

In web everything is variable
- screen & window size
- aspect ratio
- screen resolution
- the content
- available fonts

![css versions](https://upload.wikimedia.org/wikipedia/commons/f/fd/CSS3_taxonomy_and_status-v2.png)

The details of CSS2.1 was first proposed in 2004 but didn't become the official W3C recommendation until 2011. Many of the features of CSS3 are available in modern browsers today but it may be years until they the official specification for CSS.

# Selecting (10)

```html
<section class="card" id="bike-rights">
  <article>
    <h3>Bicycle rights</h3>
    <p> Blue bottle lo-fi deep v, disrupt mumblecore trust fund raw denim health goth ramps fanny pack squid typewriter forage.</p>
  </article>
  <figure>
    <img src="http://hipsum.co/wp-content/uploads/2015/01/il_fullxfull.701978082_qnbo-compressor.jpg" alt="plaid">
    
  </figure>
</section>
```

There are three main ways to select elements for applying styles
  - **tag**
```css
section article {
  text-align: center;
}
```
  - **class** can be resused, selected with `.`
```css
.card h3,
.card p {
  font-family: Helvetica-neue, Arial Black, sans-serif,
}
```
  - **id** every id must be unique, selected with `#`
```css
#bike-rights {
  background-image: linear-gradient(10deg, #881cbb 0%, #0072bc 100%);
}
```

Selecting rules can be nested and combined target elements more specifically. Keep in mind that you may inadvertently override a rule you created somewhere else or apply styles to elements you didn't intend to.

> Selectception rule - don't go more than 3 levels deep


There are also a bunch of other ways to select elements and some psuedo-selectors that let you do fancy things. [Check them out](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) when you get a chance!


### Exercise: Selecting stuff (10)

Try to get through all 26 levels of this [selecting exercise](http://flukeout.github.io/).

# Styling 

### Box model
![box model](https://camo.githubusercontent.com/3393b2c92e409167f6def57d6845d4982428585c/68747470733a2f2f646c2e64726f70626f7875736572636f6e74656e742e636f6d2f732f63617067333568626c6872366f37762f53637265656e73686f74253230323031352d31302d313325323031342e31312e33392e706e673f646c3d30)

Probably not that important
- hands of a clock for margin, padding

```csss
margin: top/bottom left/right;
padding: top right bottom left;
```

### Display styles

![display styles](http://i.stack.imgur.com/mGTYI.png)

### Floats & Clearfix

Floats allow content to wrap or `float` around eachother. A common problem form text layouts.

![floats](https://css-tricks.com/wp-content/csstricks-uploads/web-text-wrap.png)

The `clear` property stops floated elements from floating up

![not cleared](https://css-tricks.com/wp-content/csstricks-uploads/unclearedfooter.png)

![cleared](https://css-tricks.com/wp-content/csstricks-uploads/clearedfooter.png)

#### Clearfix 

Weird stuff can happen if all the children of an element are floated. The `parent` element can collapse. 

![collapse](https://css-tricks.com/wp-content/csstricks-uploads/collapse.png)

To fix this we clear the float **after** the floated elements. Pretty weird.

```css
whatevz-element:after {
  content: "";
  display: table;
  clear: both;
}
```

[css-tricks](https://css-tricks.com/all-about-floats/)

### Centering (5)
  - css tricks https://css-tricks.com/snippets/css/a-guide-to-flexbox/
  - scotch.io https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties
  - centering without flexbox https://css-tricks.com/centering-css-complete-guide/

#### Exercise: flexbox frogs (20)

Try to get through all 24 levels of this [flexbox exercise](http://flexboxfroggy.com/)

### Fonts

![comic papyrus](https://d3ui957tjb5bqd.cloudfront.net/uploads/2015/03/comic-papyrus-3.jpg)

#### You do: Add a font
  
1. Go to [google fonts](https://www.google.com/fonts) and find a font you like
- Then click the 'pop out' button (the two offset boxes) to view more details
- When you're satisfied click 'Add to Collection', then 'Use' in the bottom right
- Add the `<link href="` to your html file
  - `<link href="` is typically preferred way to add a font instead of using `@import url(`
- Add a rule to your css to use the font

```csss
font-family: bablkadf;
```


### Styling stuff
Common tags
  - border-radius
  - box-shadow
More CSS properties
  - https://developer.mozilla.org/en-US/docs/Web/CSS/Reference

#### We Do: Practice using the inspector

1. Right click on something on the page and select 'inspect'
  - or `cmd` + `shift` + `c`
- Uncheck a few properties and observe the changes
- Select a css property in the styles panel and change the value
- Add an additional property

# Assets

The two big concern for assets are
- file size / download speed
- screen resolution

Here's a good overview comparing different image file types and what their appropriate uses are:
- [stack overflow](http://stackoverflow.com/a/7752936/5472034)

### SVG

```html
<svg xmlns="http://www.w3.org/2000/svg" version="1.1">
  <rect x="25" y="25" width="200" height="200" fill="lime" stroke-width="4" stroke="pink" />
  <circle cx="125" cy="125" r="75" fill="orange" />
  <polyline points="50,150 50,200 200,200 200,100" stroke="red" stroke-width="4" fill="none" />
  <line x1="50" y1="50" x2="200" y2="200" stroke="blue" stroke-width="4" />
</svg>
```

Generates this image (without the grid):
![svg](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1a/SVG_example_markup_grid.svg/782px-SVG_example_markup_grid.svg.png)

Cons:
- not supported by older browsers
- can be messy depending on how they are exported

[wikipedia](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics)

### Icon fonts

Icon fonts are fonts that contain symbols instead of letters. 
Pros:
- can be styled with css
- vectors - so infinitely scalable
- load fast
- pretty good support

[sitepoint](https://www.sitepoint.com/introduction-icon-fonts-font-awesome-icomoon/)

### Sprites

Are a way of combining multiple images into a single file to help with download speed. They are often used for icons and simple animations.

[css tricks](https://css-tricks.com/css-sprites/)

# Bonus

### Responsive design

#### You do: Turn and Talk
Checkout [mediaqueri.es](http://mediaqueri.es/)
What changes as the screen size adjusts?
Is the same content available to all users regardless of device? Does it need to be?

----

There are three main things that contribute to making a site responsive
1. Flexible media & units
  - %, em, rem, vh, vw
- Grids
  - columns within rows
- Media specfic layouts
  - media queries

### Design frameworks
  - [bootstrap](http://getbootstrap.com/css/)
  - [other design frameworks](http://designsparkle.com/bootstrap-alternatives/)

### Additional Resources

Awesome tutorials:
- [codyhouse](https://codyhouse.co/library/)
- [codrops](http://tympanus.net/codrops/)

Code snippets:
- [littlesnippets](http://littlesnippets.net/categories/)
- [codepen](https://codepen.io/)