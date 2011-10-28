# PreLoadMe, a lightweight  jQuery website preloader
PreLoadMe is a lightweight  preloader for any webcontent. Powered by jQuery and CSS it is fully responsive and will run on all modern desktop- and mobile browsers with no additionals plugins. PreLoadMe displays a loading animation until the browser fetched the whole webcontent and will fade out the moment the page has been completely chached. Because the simplicity of PreLoadMe, it can be easily customized and adapted to your needs.

## How it works?
PreLoadMe needs following components to work:

### jQuery
You need jQuery to run PreLoadMe. Add this code before the `</body>` tag.
	
	<!-- jQuery Plugin -->
	<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.6/jquery.min.js"></script>

### jQuery Snippet
Place the following JavaScript code right before the `</body>` tag.

	<!-- Preloader -->
	<script type="text/javascript">
		//<![CDATA[
			$(window).load(function() { // makes sure the whole site is loaded
				$("#status").fadeOut(); // will first fade out the loading animation
				$("#preloader").delay(350).fadeOut("slow"); // will fade out the white DIV that covers the website.
			})
		//]]>
	</script>

### CSS
Make sure you include the following CSS code on your website.

	/* Preloader */
	#preloader {
		position:absolute;
		top:0;
		left:0;
		right:0;
		bottom:0;
		background-color:#fff; /* change if the mask should have another color then white */
		z-index:99; /* makes sure it stays on top */
	}

	#status {
		width:200px;
		height:200px;
		position:absolute;
		left:50%; /* centers the loading animation horizontally one the screen */
		top:50%; /* centers the loading animation vertically one the screen */
		background-image:url(../img/status.gif); /* path to your loading animation */
		background-repeat:no-repeat;
		background-position:center;
		margin:-100px 0 0 -100px; /* is width and height divided by two */
	}

### HTML
Place following HTML Code directly after the `<body>` tag.

	<!-- Preloader -->
	<div id="preloader">
		<div id="status">&nbsp;</div>
	</div>

The outer DIV `preloader` will be called from the CSS file and will cover the entire website with a white DIV.
The inner DIV `status` will show the loading animation.

### Image
The image `status.gif` is will be displayed in the DIV `status` and is located at `/img/status.gif`.

The source package contains all relevant files and a working demonstration.

## Disclaimers

### Credits
Please support humans.txt (http://humanstxt.org/). It's an initiative for knowing the people behind a website. It's a TXT file that contains information about the different people who have contributed to building the website.

	PreLoadMe: https://github.com/niklausgerber/PreLoadMe
	Niklaus Gerber
	Twitter: @niklausgerber
	URL: www.gerbers.ch
	Location: Bern, Switzerland
	
### Licences
PreLoadMe by Niklaus Gerber is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.
Based on a work at github.com.

### Download, Fork, Commit.
If you think you can make this better, please Download, Fork, & Commit. I'd love to see your ideas.