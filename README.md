# jQuery Canvas Overlay

jQuery plugin to allow canvas overlays with cutout at the current cursor position. Actions of elements behind the overlay, are still working.

![GitHub Logo](http://www.cw-internetdienste.de/overlay/coheader.jpg)

[See live Demo](http:www.cw-internetdienste.de/overlay/)

## Getting Started
Download the [production version][min] or the [development version][max].

[min]: https://raw.github.com/Bahlor/jQuery-Canvas-Overlay/master/dist/canvasoverlay.min.js
[max]: https://raw.github.com/Bahlor/jQuery-Canvas-Overlay/master/dist/canvasoverlay.js

In your web page:

```html
<canvas id="overlay-canvas"></div>
<script src="jquery.js"></script>
<script src="dist/canvasoverlay.min.js"></script>
<script>
jQuery(function($) {
  $('#overlay-canvas').CanvasOverlay();
});
</script>
```

## Documentation
The Plugin has 4 configuration parameters:

**Argument:**   	shadow	  
**Default:** 		10	  
**Data-Attribute:** 	-	  
**Description:** 	This defines the size of the shadow around the cutout.

**Argument:**   	radius	  
**Default:** 		150	  
**Data-Attribute:** 	-	  
**Description:** 	This defines the size / radius of the cutout itself.

**Argument:**  	ready  
**Default:**		null  
**Data-Attribute:**	-  
**Description:**	This is the callback for the onready event of the object. The callback has 1 callback variable <i>function(element)</i>. *Element* is a jquery object of the parsed html element. 

**Argument:**   	background	  
**Default:** 		'rgba(0,0,0,1)'	  
**Data-Attribute:** 	-	  
**Description:** 	This allows to change the rendering color / pattern / gradient of the overlapping background.


## Examples

**Background pattern instead of solid color**

```js
var ca = document.createElement('canvas');
  var cx	=	ca.getContext('2d');
	
	var img = new Image();
	img.src	=	'http://www.cw-internetdienste.de/overlay/assets/img/escheresque_ste.png';
	img.onload	=	function() {
		var pattern = cx.createPattern(img,'repeat')
		var overlayCanvas	=	$('#overlay').CanvasOverlay({shadow:50,radius:500,background:pattern});
	}
```

## Release History
 * 2013-06-25   v0.1.0   First initial release. Still experimental.
