# PreLoadMe, a lightweight jQuery website preloader
PreLoadMe is a lightweight preloader for any webcontent. Powered by jQuery and CSS it is fully responsive and will run on all modern desktop- and mobile browsers with no additionals plugins. PreLoadMe displays a loading animation until the browser fetched the whole webcontent and will fade out the moment the page has been completely chached. Because the simplicity of PreLoadMe, it can be easily customized and adapted to your needs.

PreLoadMe displays a loading animation until the browser fetched the whole web content and will fade out the moment the page has been completely cached. Because the simplicity of PreLoadMe, it can be easily customized and adapted to your needs.

You can read more about it here: <a href='https://www.niklausgerber.com/projects/preloadme-a-lightweight-jquery-website-preloader/' title='PreLoadMe by Niklaus Gerber' target='_blank'>PreLoadMe by Niklaus Gerber</a><br />
You can see a live preview here: <a href='http://codepen.io/niklausgerber/pen/MKrVdQ' title='PreLoadMe Live Preview' target='_blank'>PreLoadMe Live Preview</a>

## Implementation
PreLoadMe is jQuery driven. You will need to implement an up to date jQuery version and the corresponding JavaScript for executing the preloader. Add the following code right before the `</body>` tag.

    <!-- jQuery Plugin -->
    <script type="text/javascript" src="https://code.jquery.com/jquery-1.12.3.min.js"></script>

    <!-- Preloader -->
    <script type="text/javascript">
        //<![CDATA[
            $(window).on('load', function() { // makes sure the whole site is loaded 
                $('#status').fadeOut(); // will first fade out the loading animation 
                $('#preloader').delay(350).fadeOut('slow'); // will fade out the white DIV that covers the website. 
                $('body').delay(350).css({'overflow':'visible'});
              })
        //]]>
    </script>

The CSS-Markup will help you style the preloader. Make sure to include it on your website.

	body {
		overflow: hidden;
	}

	/* Preloader */
	#preloader {
		position: fixed;
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

Finally place the following HTML Code directly after the `<body>` tag.

	<!-- Preloader -->
	<div id="preloader">
		<div id="status">&nbsp;</div>
	</div>

The outer DIV `preloader` will be called from the CSS file and will cover the entire website with a white DIV. The inner DIV `status` will show the loading animation. Also you should not forget to give your document a proper doctype. Otherwise the preloader might not work.

### Using with AJAX requests
If you want to show preloader during AJAX request you can use the following CSS code.

	#preloader {
		position:fixed;
		left: 0px;
		top: 0px;
		width: 100%;
		height: 100%;		
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

Your Javascript code will look like:

	$("#status").fadeIn();
	$("#preloader").fadeIn();
	$.get(url, data, function(){
		$("#status").fadeOut();
		$("#preloader").fadeOut();
	});

The source package contains all relevant files and a working demonstration.

### Download, Fork, Commit.
If you think you can make this better, please Download, Fork, & Commit. I'd love to see your ideas.

## Donation
I love to create and I won't ask for repayment. If you appreciate my work and would like to support me I am sure you will earn some extra Karma points. <a href="https://www.paypal.me/NiklausGerber" target="_blank" title="Please donate">Please donate</a>.