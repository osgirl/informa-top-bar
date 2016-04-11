#Informa 'top-bar'

##Summary

The Informa 'top-bar' is universal branding and must be applied to every Informa website. It's implementation is
discussed in the ['Informa Web Estate Guidelines' PDF document](https://informaplc.sharepoint.com/teams/rooms4/webbestpract/Shared%20Documents/Forms/AllItems.aspx) available via the 'Informa Web Best Practice' Indigo room.

Guidance of the design, layout and colours is available in the ['Brand Guideline' PDF document](http://indigo.informa.com/informa/Brand-Centre/Documents/).

**Note**: the 'top-bar' files in the current repository are the latest files.


##Features

The Informa 'top-bar' provides a consistent branding incorporating ownership details and general Informa links. It is essentially a 
HTML fragment styled with its own Cascading Stylesheet and scripting functionality. The panel opens and closes via mouse or keyboard
events. When navigating using the keyboard the user 'tabs' into the 'top-bar' and the first element that gains focus is the 'Informa'
button - this must be activated using the 'spacebar' or 'return' keys. If a keyboard user 'tabs' out of the array of links the 'top-bar'
will automatically close and dependent on tabbing direction focus will then be gained on the next/previous element in the document.

The 'top-bar' is designed to be implemented on diverse sites and this is a particular reason for it being designed to be accessible in
the absence of scripting availability. In the latter circumstance the 'top-bar' will present itself in an open state with no script-added
control button.


##Requirements

The Informa 'top-bar' has a reliance on the jQuery library (no particular version).


##Implementation

1. Add references to the CSS file in the ```<head>``` section of your web page. For example:
   ```<link href="css/top-bar.css" rel="stylesheet" media="screen" />```

2. Add the image files into a directory of your choice and ascertain that the references to the files are valid in the CSS file.
   Edit the paths if not. There are two images in the repository, both the same but one is designed for 'Retina' displays.

3. Add references to jQuery in the ```<head>``` section of your web page. For example:
   ```<script src="https://code.jquery.com/jquery-1.11.3.min.js"></script>```

4. Add references to the 'top-bar' Javascript file in the ```<head>``` section or at the base of the ```<body>``` section of the page. 
   For example: ```<script src="/main.js"></script>```
   Alternatively you may want to integrate the script contents into an existing Javascript file to reduce HTTP-requests.

5. Add the folowing HTML fragment into the markup as the first child of the ```<body>``` section. 

```
	<div id="iribbon-container">
		<div id="iribbon-detail">
			<div id="iribbon-left">
				<p>Datamonitor is part of the Business Intelligence Division of Informa PLC</p>
				<ul>
				  <li><a href="http://informa.com/">Informa PLC</a></li>
				  <li><a href="http://informa.com/About-Us/">About us</a></li>
				  <li><a href="http://informa.com/Investors/">Investor relations</a></li>
				  <li><a href="http://informa.com/Talent/">Talent</a></li>
				</ul>
			</div>
			<div id="iribbon-right">
				<p>This site is operated by a business or businesses owned by Informa PLC and all copyright resides with them. 
                Informa PLC's registered office is 5 Howick Place, London SW1P 1WG. Registered in England and Wales. Number 8860726.</p>
			</div>
		</div>
	</div>
```
   **Note**: The initial paragraph should be edited to reflect the title of the site to which it is being applied.


##Troubleshooting

As the 'top-bar' is operated via scripting it is important to ensure that the content is always accessible and available in an
unpredictable user-agent environment which may preclude scripting. The 'top-bar' has therefore been designed from a 'progressive
enhancement' perspective - its content is plain HTML and will always be delivered and legible. However, this means that on some 
sites where there may be a small delay between the HTML being rendered and the script initiating the close/open mechanism. This will
potantially result in a perceivable flash of the 'top-bar' in an open state before being closed. This is most likely to occur on 
sites where numerous other scripts are potentially causing delays by implementation or design. 


