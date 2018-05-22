
# Web Developer Guide

## Prerequisits

- NPM
- http-server
- Visual Studio Code

## HTML 5 Structure
The skeleton of all HTML5 pages should look like the following:
```html
<!DOCTYPE html>
<html lang="en"> <!-- ALWAYS specify the language, this helps browsers and search engines in displaying your page -->
    <head>
        <meta charset="utf-8"/> <!-- This should always be the first element in the header, see https://www.w3.org/International/questions/qa-html-encoding-declarations -->
        <meta name="viewport" content="width=device-width, initial-scale=1.0" /> <!-- Mobile compatible website/app-->
        <!--
        <meta name="description" content="Page synopsis, this must be less than 155 characters">
        <meta name="author" content="Just to Brag">
        -->
        <title>Name of the page here</title>
        <!--
        <link rel="stylesheet" type="text/css" href="assets/css/default.css" />
        <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
        <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
        -->
    </head>

    <body>
        <header>
            <nav>
                <li>Menu item</li>
                <li>Menu item</li>
                <li>Menu item</li>
            </nav>
        </header>

        <section>
            <article>
                <header>
                    <h2>Article Title</h2>
                    <p>Article content goes here</p>
                </header>
            </article>
        </section>

        <aside>
            <h2>Section Title</h2>
            <p>Content of the Section</p>
        </aside>

        <footer>
            <p>Copyright @year @name</p>
        </footer>
    </body>
</html>
```

## Colours

Colours in CSS are defined using the Red, Green, Blue (RGB) model (#RRGGBB)
example of a color is `#ff0000` (Red), `#00ff00` (Green), `#0000ff` (Blue), another notation is:
`rbg(12, 334, 43, 0.75)` (this also includes transparancy)

### Choosing colors
- Choose ONLY one base colour (excluding black, white or shades of gray)
- See [0to255](http://www.0to255.com/) to help with picking colors
- Use the main colour draw the most user to important parts of the website
- NEVER use pure black (`#00000`) as part of any design, its unnatural

### Links
```css
	/* Ensure links looks the same even if previously visited */
	.someclass:link, .someclass:visited {
		text-decorated: none;
	}
```

### Colours Invoke Certain Emotions
Picking a color for a website means more then picking your favorite color and turning it into a design. It means picking the right color in order to get the desired response from your audience. Color really makes a difference. This happens because there are psychological effects behind each color.

- *Red* is a great color to use when power, passion, strength and excitement want to be transmitted. Brighter tones are more energetic and darker shades are more powerful and elegant.
- *Orange* draws attention without being as overpowering as red. It means cheerfulness and creativity. Orange can be associated with friendliness, confidence, and courage.
- *Yellow* is energetic and gives the feeling of happiness and liveliness. Also, it associates with curiosity, intelligence, brightness, etc.
- *Green* is the color of harmony, nature, life and health. Also, it is often associated with money. In design, green can have a balancing and harmonizing effect.
- *Blue* means patience, peace, trustworthiness, and stability. It is one of the most beloved colors, especially by men. It is associated with professionalism, trust and honor. That's actually why the biggest social networks use blue.
- *Purple* is traditionally associated with power, nobility and wealth. In your design, purple can give a sense of wisdom, royalty, nobility, luxury, and mystery.
- *Pink* expresses romance, passivity, care, peace, affection, etc.
- *Brown* is the color of relaxation and confidence. Brown means earthiness, nature, durability, comfort, and reliability.

## CSS *Block Model*

CSS elements can either be inline or block elements, block elements adhear to whats called the *Block Model* in which they can have margins and padding.
All browsers add default margins and padding on *Block Elements* its important to remove these and add you own as needed:

```css
* {
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
}
``` 
### Center Website Page
```css
.container {
    width: 1140px;
    margin: 0 auto 0 auto;
}

/* or */

.container {
    width: 1140px;
    margin-left: auto;
    margin-right: auto;
}
```
### *CSS* Animation 
```css
	a:link, a:visited {
		transition: border-bottom 0.2s; /* what to animate and for how long (in seconds) */
	}
	a:hover, a:active {
		border-bottom: 2px solid #ff0000;
	}	
```

### `:before` and `:after` *CSS* Pseudo Classes
There is a way to use *CSS* to insert content either `before` or `after` every element:
```css
/* Customize every h2 heading to have short orange underline as a style */
h2:after {
	content: " ";
	height: 3px;
	width: 150px;
	display: block;
	background-color: #e67e22;
	margin: 30px  auto  0  auto;
}
```
### `:first-child` and  `:last-child` *CSS* Pseudo Classes
As the name suggests selecting the first child or first child of the *CSS* elements

### `:last-of-type` *CSS* Pseudo Classes


### Lining up block elements
```html
<style>
    .ice-block {
        float: left;
        width: 30%;
    }

    .clearfix:after {
        clear: both;
        content: "";
        display: table;
    }
</style>

<div class="ice-block">

</div>
<div class="ice-block">

</div>
<div class="clearfix"></div>
```

### Element Positioning
```html

<style>

.container {
    position: relative;
}

.show-right {
    position: absolute;
    top:0;
    right:20px;
}
</style>

<div class="container"> <!-- Relative -->
    <div class="show-right">Nice Position</div> <!-- Absolute -->
</div>
```
## Typography Guidelines
- Use font sizes between `15px` and `25px` for general text
- Use font sizes between `32px` and `60px` for headings
- Use line spacing of between `120%` and `150%`
- Get more fonts from [Google Web Fonts](https://fonts.google.com/)

### Choosing a font
1. Choose a font which reflects the look and feel you want for your website
2. Decide: `sans-serif` or `serif` typeface?
3. Then choose the good font `sans-serif`/`serif`
4. Only use one typeface

### Headings 
Each page should typically only have one `<h1>` element but can have many `<h2>`, `<h3>` and so on. 

## Using Images as part of design
Images can be used in the background of text, however for the text to be readable apply the following strategies:
- Use images that are in contrast with the text colour
- Use *Text Overlays* (must be transparent) on the image to bring out the text
- Use *Image Blur* to focus the text in the blurred background
- Use *Bottom/Top Fade* to bring out the text in an image based website while also preserving the image visibility (the fade effect is only applied to the top/bottom part of the image where there is text after which it fades out)

```css
/* Using one element that has an Image that is dimmed to enabled visible overlayed text */
header {
	background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('image/hero.jpg');
	height: 100vh; /* 100% ViewPort*/
	background-position: center;
	background-size: cover;
}
```

## Icons on a Website
Icons have the power in determining the look and feel of an entire website, but at the same time they can also cause user confusion when poorly used. Icons give the user a glimpse of what the website is about, use the following guidelines:
- Use icons to show features/products that you are selling.
- Use icons to show steps the a user needs to follow to achieve a particular task
- Use icons for actions and links
	- Icons should be very familiar
	- Always label icons where possible
- Icons should NEVER play the center stage in your design but instead play a supporting role
- Use *Icon Fonts* where possible because *Icon Images* loose their quality when they are resized

You can download the icons on [Ionic Icons](http://ionicons.com/) or use *NPM*

## Spacing and Layout
### Use *Whitespace*
Every piece of good design uses white spaces well, often when you want to have a great design you need a lot of *Whitespaces* in the correct places. *Whitespace* enable us to create a clean simple website, with *whitespace* we also describe the invisible relationships between the elements of your website.
Simple guidelines are:
- Put *Whitespace* between your elements
- Put *whitespace* between groups of elements
- Put *whitespace* between your website's sections
- But don't exaggerate, too much *whitespace* can lead elements to loose their relationship

### Define Hierarchy
*Whitespace* is closes related to something called *Visual Hierarchy* (content structure), which gives order to your website (guides audience from one element to the next), use the following guidelines:
- Define where you want the audience to look first
- Establish a  flow that corresponds to your content's message
- Use *Whitespace* to build that flow

## User Experience
Overall experience the the user has on using the product, this includes the *User Interface* but also has to understand to whole picture of the product

## Getting Inspiration
Use other leading website as a source of your inspiration, this will help you understand what other leading designers are *doing right*. You'll also need to be able to *steal like at artist*, when starting try using designs of existing websites, dont worry about looking different.

- Collect designs  that you like are good
- Try to understand everything about them
	- Why do they look do good?
	- What do they have in common?
	- How were they build in HTML and CSS?

## Real World Steps in Building an Online Platform
1. Define Your Project
	- Define the goal of your project (Showing your portfolio to the world, selling stuff or providing specialised services)
	- Define your audience
2. Plan Out Everything
	- Plan your content carefully: images, videos, icons etc.
	- Start thinking about visual hierarchy and use the content first approach (let content define your site rather than building a site and filling it with content)
		- Define navigation
		- Define the site structure  (define a site map for larger projects)
3. Sketch Your Ideas Before You Design
	- Get inspired and think about your design
	- Sketch any ideas down to paper before you start designing
	- Make as many sketches as you want, don't worry about making it perfect
	- Never start designing without having an idea of what you want to build
4. Design and Develop Your Website
	- Start the design process using HTML and CSS (done on the browser)
	- Create folder structure that will cater for all the static content of your site
	- Use sketches, content and planning decisions you've made in steps 1, 2 and 3.
5. Site Optimisation
	- Speed (fast)
	- Search engine optimisation (searchable from popular search engines) and example of this is to use a `lang` attribute in the `html` tag to define the language of the page i.e. `<html lang="en">`
	- Use [normalize.css](https://necolas.github.io/normalize.css) to ensure that CSS renders the same in all browsers
6. Launch The Website
	- Deploying this on a Web Server (Apache HTTP, NginX etc.)
7.  Site Maintenance
	- Monitor user behaviour and make changes accordingly

### Design and Develop Your Website
The first to do is to create the folder structure of your site, ensure separation between your assets and 3rd party assets as seen below, also note that in some cases the *CSS* folder could have images that are used for *CSS* ONLY.
```
	projectname/assets/image
	projectname/assets/css
	projectname/assets/css/image (for image background)
	projectname/assets/css/font
	projectname/assets/js
	projectname/assets/3party1/css
	projectname/assets/3party1/js
	projectname/assets/3party1/font
```
Next we need to download the following assets:
- [normalize.css](https://necolas.github.io/normalize.css) (or use package manager such as *NPM*)
- Fonts that you want for your site (or you can use a *CSS* declaration from [Google Fonts](https://fonts.google.com/))

Next we create the font *CSS* file (optional if you going to use internet link), file should be located in the path `assets/css/font.css`,  and should look like the following:
```css
@font-face {
	font-family: 'Open Sans';
	src: url(font/opensans-regular.ttf);
}
@font-face {
	font-family: 'Open Sans Light';
	src: url(font/opensans-light.ttf);
}
```
Next we create the global *CSS* file that will be used throughout the website, `asset/css/default.css`:
```css
@import url('font.css');

* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

html {
	background-color: #fff;
	color: #535353;
	font-family: 'Open Sans Light', 'Arial', sans-serif;
	/* This is the base font size, every child element should use percentage % */
	font-size: 20px; /* use desiredSize / 20 = % */
	text-rendering: optimizeLegibility;
}
```
Next we create a landing/main page for the whole website:
```html
<!doctype html>
<html lang="en"> <!-- This helps search engines -->
	<head>
		<meta charset="utf-8"/>
		<title>My Kickass Site</title>
		<link rel="stylesheet" type="text/css" href="assets/normalize/css/normalize.css" />
		
		<link rel="stylesheet" type="text/css" href="assets/css/default.css" />
	</head>
	<body>
		<h1>Hello World</h1>
	</body>
</html>
```

## Responsive Design
This is a design that allows a website to adapt to any size/shape modern screen. According to [HostingFacts.com](https://hostingfacts.com/internet-facts-stats-2016/) mobile devices are responsible for over 50% of the internet traffic. There are 3 main ingredients to Responsive Web Design:
- *Fluid Grid* a grid structure in which the width of every cell is defined using relative units such as percentages as opposed to absolute units such as pixels/points (see [Responsive Grid System](http://www.responsivegridsystem.com/) for grid system).
- *Flexible Images* images are also resized using relative units
- *Media Queries* allows for for different *CSS* to be used based on the browser widths

### *Viewport* (Mobile Zooming)
Mobile devices should never zoom out of the web page because the content tents to get too small to read, instead should use the device width:

```html
<html lang="en">
	<head>
		<meta charset="utf-8"/>
		<!-- Don't Zoomout this is specifically for smaller screens -->
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
	</head>
</html>
```

```css
/* A responsive centered element in the middle of the page */
.hero-text-box {
	position: absolute;
	width: 1140px;
	left: 50%;
	top: 50%;
	transform: translate(-50%, -50%)
}

```
### *Media Queries* and *Breakpoints*
This enables *CSS* to call different style declarations based on browser width or mobile device, these *Media Queries* will trigger at different *Breakpoints* (screen widths which we want the web page to change the way it looks). You can also use a browser's *Developer Tools* to take advantage of the predefined device sizes, on *Google Chrome* simply press `F12` then `Ctrl`+`Shift`+`M` .
*Media Queries* should be defined in their own separate file, which would then be declared after the styles you want to trigger on:

#### Defining `assets/css/mq.css`
```css
/* Smartphones (portrait and landscape) ----------- */
@media only screen and (min-device-width : 320px) and (max-device-width : 480px) {
	.somestyle {
		position: absolute;
		width: 100%;
		left: 50%;
	}
}

/* Smartphones (landscape) ----------- */
@media only screen and (min-width : 321px) {
/* Styles */
}

/* Smartphones (portrait) ----------- */
@media only screen and (max-width : 320px) {
/* Styles */
}

/* iPads (portrait and landscape) ----------- */
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) {
/* Styles */
}

/* iPads (landscape) ----------- */
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : landscape) {
/* Styles */
}

/* iPads (portrait) ----------- */
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : portrait) {
/* Styles */
}
/**********
iPad 3
**********/
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : landscape) and (-webkit-min-device-pixel-ratio : 2) {
/* Styles */
}

@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : portrait) and (-webkit-min-device-pixel-ratio : 2) {
/* Styles */
}
/* Desktops and laptops ----------- */
@media only screen  and (min-width : 1224px) {
/* Styles */
}

/* Large screens ----------- */
@media only screen  and (min-width : 1824px) {
/* Styles */
}

/* iPhone 4 ----------- */
@media only screen and (min-device-width : 320px) and (max-device-width : 480px) and (orientation : landscape) and (-webkit-min-device-pixel-ratio : 2) {
/* Styles */
}

@media only screen and (min-device-width : 320px) and (max-device-width : 480px) and (orientation : portrait) and (-webkit-min-device-pixel-ratio : 2) {
/* Styles */
}

/* iPhone 5 ----------- */
@media only screen and (min-device-width: 320px) and (max-device-height: 568px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

@media only screen and (min-device-width: 320px) and (max-device-height: 568px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

/* iPhone 6 ----------- */
@media only screen and (min-device-width: 375px) and (max-device-height: 667px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

@media only screen and (min-device-width: 375px) and (max-device-height: 667px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

/* iPhone 6+ ----------- */
@media only screen and (min-device-width: 414px) and (max-device-height: 736px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

@media only screen and (min-device-width: 414px) and (max-device-height: 736px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

/* Samsung Galaxy S3 ----------- */
@media only screen and (min-device-width: 320px) and (max-device-height: 640px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

@media only screen and (min-device-width: 320px) and (max-device-height: 640px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 2){
/* Styles */
}

/* Samsung Galaxy S4 ----------- */
@media only screen and (min-device-width: 320px) and (max-device-height: 640px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 3){
/* Styles */
}

@media only screen and (min-device-width: 320px) and (max-device-height: 640px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 3){
/* Styles */
}

/* Samsung Galaxy S5 ----------- */
@media only screen and (min-device-width: 360px) and (max-device-height: 640px) and (orientation : landscape) and (-webkit-device-pixel-ratio: 3){
/* Styles */
}

@media only screen and (min-device-width: 360px) and (max-device-height: 640px) and (orientation : portrait) and (-webkit-device-pixel-ratio: 3){
/* Styles */
}
```
#### Declaring *Media Query* in the main page
```html
	...
	<head>
		<meta charset="utf-8"/>
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<title>My Kickass Site</title>
		<link rel="stylesheet" type="text/css" href="assets/normalize/css/normalize.css">		
		<link rel="stylesheet" type="text/css" href="assets/css/default.css">
		<!-- Declaring Media Query CSS -->
		<link rel="stylesheet" type="text/css" href="assets/css/mq.css">
	</head>
	...
```

## Search Engine Optimisation (SEO)
Web pages can declare extra metadata which help the search engines in presenting a quick synopsis about the page, this is achieved by using the `<meta>` tags as follows:

```html
<!doctype html>
<html lang="en"> <!-- This helps search engines -->
	<head>
		<meta charset="utf-8"/>
		<meta name="description" content="Page synopsis, this must be less than 155 characters">
		<!-- The Keywords metadata is no longer used nowadays only a few search engines still use this and it can be ignored -->
		<meta name="keywords" content="fruits, vegetables, watches" >
		<title>Kickass Site</title>
		...
	</head>
	...
</html>
```
## Creating a *favicon*
*favicons* are small icons on the browser's tab to easily identify a website's identity. The icon should adhere to a standard size of either 16x16 or 32x32, there are many tools that can help you generate icons some can be found at [favicon-generator.org](https://www.favicon-generator.org/), and are declared in the following manner:

```html
<!doctype html>
<html lang="en">
	<head>
        <meta charset="utf-8"/>
		<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
		<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
		<title>Kickass Site</title>
		...
	</head>
	...
</html>
```

## Website Performance Optimisation
The easiest way to optimise a website's loading time is to use compressed files, when using 3rd party libraries ensure that you select the *minified* version to be declared on your pages, this is a compressed version which will load faster.
Another way is to make sure that the images used in the website are compressed, you can try online tools such as [optimizilla.com](http://optimizilla.com) to significantly reduce your image sizes
