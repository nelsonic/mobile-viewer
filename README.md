mobile-viewer
=============

Simulate your mobile web app/site on desktop the easy way.

Instead of *installing* an app to simulate the iPad viewport why not simply 
use an iFrame in your project's testing page to constrain the viewport on desktop?

## Demo

Visit: **http://goo.gl/vi6XLj**


The code is pretty simple:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
    <title>iPad View</title>
  </head>
  <body>
    <iframe id="ipad" src="http://nelsonic.s3.amazonaws.com/range-touch/index.html" frameborder="0" width="1024" height="768"></iframe>

    <!-- add a bezel-like border to the iframe to simulate an ipad -->
    <style>
      iframe {
        z-index: 10;
        border: 40px solid black;
        border-radius: 40px;
        margin-left: 30px;
      }
    </style>
  </body>
</html>
```

And an example: http://nelsonic.s3.amazonaws.com/mobile-viewer/example/demo.html

## [Future] Features

1. Switch Viewport Size and Orientation on the fly with a button e.g:
- iPad 2 Portrait / Landscape
- iPhone 4 Portrait / Landscape
- iPad 4 Portrait / Landscape
- iPhone 5 Portrait / Landscape
- Samsung Galaxy S2 Portrait / Landscape
2. Allow anyone to define a new "Device" 
- Device Name
- Operating System + Version
- Width
- Height
3. Save Viewport options to cookie/local storage so user can return
4. Add (iFrame) url and viewport options to containing page url to make it shareable
5. Use HTML5 Canvas (when available) or PhantomJS to take screenshots (without forcing anyone to install a plugin)
6. Save history of pages viewed inside the frame for easy/quick re-access


## Same Origin Annoyance

> Refused to display 'example.com' in a frame because it set 'X-Frame-Options' to 'SAMEORIGIN'

I will get around this by creating a Node.js proxy for any page you are visiting.
Thus creating a web app. 

- http://stackoverflow.com/questions/6666423/overcoming-display-forbidden-by-x-frame-options