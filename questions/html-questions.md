# HTML Questions:

### What does a `doctype` do?
`doctype` lets the browser know what markup standard the page is using.  This allows the browser to determine how to render the page according to the source code.

###### References
* https://stackoverflow.com/questions/7695044/what-does-doctype-html-do

### How do you serve a page with content in multiple languages?
Use `lang` in tags. Also use metadata and `Content-Language` HTTP header.  

###### References
* https://www.w3.org/International/getting-started/language

	
### What kind of things must you be wary of when design or developing for multilingual sites?
* `lang` attribute in your HTML.
* Directing users to their native language - Allow a user to change his country/language easily without hassle.
* Language reading direction - `dir` attr indicating language direction, such as `rtl`
* Restrictive words/sentence length
* Be mindful of how colors are perceived - Colors are perceived differently * across languages and cultures. The design should use color appropriately.
* Formating dates and currencies

###### References
* https://www.quora.com/What-kind-of-things-one-should-be-wary-of-when-designing-or-developing-for-multilingual-sites

### What are `data-` attributes good for?
Before JavaScript frameworks became popular, front end developers used data- attributes to store extra data within the DOM itself, without other hacks such as non-standard attributes, extra properties on the DOM. It is intended to store custom data private to the page or application, for which there are no more appropriate attributes or elements.

These days, using data- attributes is not encouraged. One reason is that users can modify the data attribute easily by using inspect element in the browser. The data model is better stored within JavaScript itself and stay updated with the DOM via data binding possibly through a library or a framework.

###### References
* http://html5doctor.com/html5-custom-data-attributes/


### Consider HTML5 as an open web platform. What are the building blocks of HTML5?
* Semantics - Allowing you to describe more precisely what your content is.
* Connectivity - Allowing you to communicate with the server in new and innovative ways.
* Offline and storage - Allowing webpages to store data on the client-side locally and operate offline more efficiently.
* Multimedia - Making video and audio first-class citizens in the Open Web.
* 2D/3D graphics and effects - Allowing a much more diverse range of presentation options.
* Performance and integration - Providing greater speed optimization and better usage of computer hardware.
* Device access - Allowing for the usage of various input and output devices.
* Styling - Letting authors write more sophisticated themes.

###### References

* https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5
	
### Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
* All the above-mentioned technologies are key-value storage mechanisms on the client side. They are only able to store values as strings.

###### References

* https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies
 
 
### Describe the difference between `<script>`, `<script async>` and `<script defer>`.
 * `<script>` stops the rendering process, to download and run the script
 * `<script async>` does not stop the rendering process while asynchronously downloading a script. When finished downloading, it stops rendering and the script runs.
 * `<script defer>` does not stop the rendering process while asynchronously downloading a script. When finished rendering, the script runs.

###### References
* https://stackoverflow.com/questions/10808109/script-tag-async-defer

### Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
 *  The `<link>` tag placed between the `<head></head>` to allow the page to render progressively which improves the user experience. If stylesheets are placed near the bottom of the document, it will prohibit progressive rendering in browsers. Some browsers block rendering to avoid having to repaint elements of the page if styles change. The user will be stuck viewing a blank white page.
 *  The `<script>` is placed before the `</body>` because `<script>`s block HTML parsing while they are being downlaoded and executed.  This will allow the HTML to be parsed and displayed to the user.
 *  The exception for positioning the `<script>`s at the bottom is when the `<script>` contains a `document.write()`.

###### References
* https://developer.yahoo.com/performance/rules.html#css_top

  
### What is progressive rendering?
 * Progressive rendering is the name given to techniques used to render content for display as quickly as possible. With HTML progressive rendering is chunking the HTML into separate bits and loading each block as it's finished. 
 * e.g. `Lazy Loading` and `Prioritizing visible content`. 

###### References

* https://stackoverflow.com/questions/33651166/what-is-progressive-rendering

### Why you would use a `srcset` attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.
You would use the `srcset` attribute when you want to serve different images to users depending on their device display width - serve higher quality images to devices with retina display enhances the user experience while serving lower resolution images to low-end devices increase performance and decrease data wastage (because serving a larger image will not have any visible difference). 

For example: `<img srcset="small.jpg 500w, medium.jpg 1000w, large.jpg 2000w" src="..." alt="">` tells the browser to display the small, medium or large `.jpg` graphic depending on the client's resolution. The first value is the image name and the second is the width of the image in pixels. For a device width of 320px, the following calculations are made:

* 500 / 320 = 1.5625
* 1000 / 320 = 3.125
* 2000 / 320 = 6.25

If the client's resolution is 1x, 1.5625 is the closest, and `500w` corresponding to `small.jpg` will be selected by the browser.

If the resolution is retina (2x), the browser will use the closest resolution above the minimum. Meaning it will not choose the 500w (1.5625) because it is greater than 1 and the image might look bad. The browser would then choose the image with a resulting ratio closer to 2 which is 1000w (3.125).

`srcset`s solve the problem whereby you want to serve smaller image files to narrow screen devices, as they don't need huge images like desktop displays do — and also optionally that you want to serve different resolution images to high density/low-density screens.


###### References
*  https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images

### Have you used different HTML templating languages before?
* I have used Pug/Jade before. 
