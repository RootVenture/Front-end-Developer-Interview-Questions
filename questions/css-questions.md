# CSS Questions:

### What is CSS selector specificity and how does it work?
Specificity **determines, which CSS rule is applied** by the browsers.
There are four distinct categories which define the specificity level of a given selector, and are four comma-separated values, `a, b, c, d`.

1. `a` are **Inline styles** (Presence of style in document). An inline style lives within your XHTML document. It is attached directly to the element to be styled. E.g. `<h1 style=“color: #fff;”>`
1. **IDs** (# of ID selectors) ID is an identifier for your page elements, such as `#div`.
1. **Classes, attributes and pseudo-classes** (# of class selectors). This group includes `.classes`, `[attributes]` and pseudo-classes such as `:hover`, `:focus` etc.
1. **Elements and pseudo-elements** (# of Element (type) selectors). Including for instance `:before` and `:after`.

The resulting specificity is not a score, but a matrix of values that can be compared column by column. When comparing selectors to determine which has the highest specificity, look from left to right, and compare the highest value in each column. So a value in column `b` will override values in columns `c` and `d`, no matter what they might be. As such, specificity of `0,1,0,0` would be greater than one of `0,0,10,10`.

When selectors have an equal specificity value, the latest rule is the one that counts.

###### References
* https://www.smashingmagazine.com/2007/07/css-specificity-things-you-should-know/

### What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
1. **Reset** - CSS resets aim to *remove* all built-in browser styling. Standard elements like H1-6, p, strong, em, et cetera end up looking exactly alike, having no decoration at all. You're then supposed to add *all decoration* yourself.
2. **Normalize** - Normalize CSS aims to make built-in browser styling *consistent* across browsers. Elements like H1-6 will appear bold, larger et cetera in a consistent way across browsers. You're then supposed to add only the *difference* in decoration your design needs.

If your design a) follows common conventions for typography et cetera, and b) Normalize.css works for your target audience, then using Normalize.CSS instead of a CSS reset will make your own CSS smaller and faster to write.

###### References
* https://stackoverflow.com/questions/6887336/what-is-the-difference-between-normalize-css-and-reset-css

### Describe Floats and how they work.
Float is a CSS positioning property. Floated elements remain a part of the flow of the page, and will affect the positioning of other elements (e.g. text will flow around floated elements), unlike position: absolute elements, which are removed from the flow of the page.

There are four valid values for the float property. **Left** and **Right** float elements those directions respectively. **None** (the default) ensures the element will not float and **Inherit** which will assume the float value from that elements parent element.

If a parent element contains nothing but floated elements, its height will be collapsed to nothing. It can be fixed by clearing the float after the floated elements in the container but before the close of the container.

**The Easy Clearing Method**.clearfix hack uses a clever CSS pseudo selector (`:after`) to clear floats. Rather than setting the overflow on the parent, you apply an additional class clearfix to it. Then apply this CSS:

```
.clearfix:after {
  content: ' ';
  visibility: hidden;
  display: block;
  height: 0;
  clear: both;
}
```
###### References
* https://css-tricks.com/all-about-floats/

### Describe z-index and how stacking context is formed.
The `z-index` property in CSS controls the vertical stacking order of elements that overlap. As in, which one appears as if it is physically closer to you. `z-index` only effects elements that have a position value other than `static` (the default).

Without any z-index value, elements stack in the order that they appear in the DOM (the lowest one down at the same hierarchy level appears on top). Elements with non-static positioning will always appear on top of elements with default static positioning.

A stacking context is an element that contains a set of layers. Within a local stacking context, the `z-index` values of its children are set relative to that element rather than to the document root. Layers outside of that context — i.e. sibling elements of a local stacking context — can't sit between layers within it. If an element B sits on top of element A, a child element of element A, element C, can never be higher than element B even if element C has a higher `z-index` than element B.

Each stacking context is self-contained - after the element's contents are stacked, the whole element is considered in the stacking order of the parent stacking context. A handful of CSS properties trigger a new stacking context, such as `opacity` less than 1, `filter` that is not `none`, and `transform` that is not `none`.

###### References
* https://css-tricks.com/almanac/properties/z/z-index/
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context

### Describe BFC(Block Formatting Context) and how it works.
A Block Formatting Context (BFC) is part of the visual CSS rendering of a web page in which block boxes are laid out. 

A BFC is an HTML box that satisfies at least one of the following conditions:

* The value of `float` is not `none`.
* The value of `position` is neither `static` nor `relative`.
* The value of display is `table-cell`, `table-caption`, `inline-block`, `flex`, or `inline-flex`.
* The value of `overflow` is not `visible`.

In a block formatting context, each box’s left outer edge touches the left edge of the containing block (for right-to-left formatting, right edges touch). Floats do not affect the layout of the content inside other block formatting contexts, and clear only clears past floats in the same block formatting context.

###### References
* https://www.sitepoint.com/understanding-block-formatting-contexts-in-css/
* https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context

### What are the various clearing techniques and which is appropriate for what context?
* How would you approach fixing browser-specific styling issues?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system, and if so, what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?
* Can you give an example of an `@media` property other than `screen`?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Describe pseudo-elements and discuss what they are used for.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* What is the CSS `display` property and can you give a few examples of its use?
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
