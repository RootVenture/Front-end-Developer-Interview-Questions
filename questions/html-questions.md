# HTML Questions:

* What does a `doctype` do?
	* `doctype` lets the browser know what markup standard the page is using.  This allows the browser to determine how to render the page according to the source code. 
		
* How do you serve a page with content in multiple languages?
	* Use `lang` in tags. Also use metadata and `Content-Language` HTTP header.  
	
* What kind of things must you be wary of when design or developing for multilingual sites?
	* `lang` attribute in your HTML.
	* Language reading direction - `dir` attr indicating language direction, such as `rtl`
	* Restrictive words/sentence length
	* Be mindful of how colors are perceived - Colors are perceived differently across languages and cultures. The design should use color appropriately.
	* Formating dates and currencies
	
* What are `data-` attributes good for?
	* 	Allow us to store extra information on standard, semantic HTML elements.
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
	*  Semantics
	*  Connectivity 
	*  Offline and storage
	*  Multimedia
	*  2D/3D graphics and effects
	*  Performance and integration
	*  Device access
	*  Styling
	
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
* 
 
 
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
 * `<script>` stops the rendering process, to download and run the script
 * `<script async>` does not stop the rendering process while asynchronously downloading a script. When finished downloading, it stops rendering and the script runs.
 * `<script defer>` does not stop the rendering process while asynchronously downloading a script. When finished rendering, the script runs.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
 *  The `<link>` tag placed between the `<head></head>` to allow the page to render progressively which improves the user experience. If stylesheets are placed near the bottom of the document, it will prohibit progressive rendering in browsers. Some browsers block rendering to avoid having to repaint elements of the page if styles change. The user will be stuck viewing a blank white page.
 *  The `<script>` is placed before the `</body>` because `<script>`s block HTML parsing while they are being downlaoded and executed.  This will allow the HTML to be parsed and displayed to the user.
 *  The exception for positioning the `<script>`s at the bottom is when the `<script>` contains a `document.write()`.
 *  Reference:
 		* https://developer.yahoo.com/performance/rules.html#css_top
  
* What is progressive rendering?
 * Progressive rendering is the name given to techniques used to render content for display as quickly as possible. With HTML progressive rendering is chunking the HTML into separate bits and loading each block as it's finished. 
 * e.g. `Lazy Loading` and `Prioritizing visible content`. 
* Why you would use a `srcset` attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.
 *  `srcset` defines the set of images we will allow the browser to choose between, and what size each image is.
 *  https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images
 *  With these attributes in place, the browser will:
	 * Look at its device width
 	 * Work out which media condition in the sizes list is the first one to be true
 	 * Look at the slot size given to that media query
 	 * Load the image referenced in the `srcset` list that most closely matches the chosen slot size.  
* Have you used different HTML templating languages before?
	* I have used Pug/Jade before. 
