% zdk-modal
% zedesk.net
% May 2014

zdk-modal
==========

This polymer component aims to display a modal content, over the page content. A background panel will hide all the page to prevent events on the page.

The content of the component is your own, however the modal panel is sized and clipped by two attributes : width and height. so the content must be sized with width and height to 100% to fill all the available space. By default if no attributes is given the width and height are fixed to 300px.

## how to use it

it's very simple, first get the component thanks to the bower command :

    bower install zdk-modal -S

Then in the header of your html page, adds :

    <script src="/bower_components/platform/platform.js"></script>
    <link rel="import" href="/bower_components/zdk-modal/zdk-modal.html">

And finally in the body of your page :

    <zdk-modal width="<width>" height="<height>">
        <! your content here -->
    </zdk-modal>

## Attributes

   - __closebutton__ ( boolean ) show the close button, by default the button is shown to hide it : `closebutton="false"`
   - __width__ defines the width of the panel
   - __height__ defines the height of the panel
   - __type__ position attribute :
     - __top__ the panel is displayed at the top of the screen
     - __bottom__ the panel is displayed at the bottom of the screen
     - __middle__ the panel is displayed at the middle of the screen ( default )
	 
## Methods

__show()__ display the component

__hide()__ hide the component

These actions could also be done by changing the class of the object. if the classList contain "show" then component is automatically displayed.

__timeout(time)__ shows the modal box for time in seconds, if time is set to zero the box never automatically close.

## Demo

[demo](demo.htm)
  
## examples

    <html>
    <head>
        <meta charset="utf-8">
        <title>modal box component</title>
        <script src="/bower_components/platform/platform.js"></script>
        <link rel="import" href="/bower_components/zdk-marked/zdk-modal.html">
        <link rel="import" href="/bower_components/zdk-marked/zdk-marked.htm">
    </head>
    <body>
        <style>
        body { font-family: Verdana; font-size: 15px; }
        zdk-modal {
            border:1px solid black;
            box-shadow: 2px 2px 10px #ccc;
        }
        zdk-modal div.content {
            padding:10px;
            box-sizing: border-box;
            width:100%; height: 100%;
            background: Tomato;
            border:1px solid red;
            overflow: auto;
            border-radius:20px;
        }
        </style>
        <zdk-modal id="modal1" width="400" height="300" class="show" type="bottom" >
            <div class="content">
            <zdk-marked src="/bower_components/zdk-marked/README.md"></zdk-marked>
            </div>
        </zdk-modal>
        <zdk-marked src="/bower_components/zdk-marked/README.md"></zdk-marked>
        <p><button onclick="show()">show</button></p>
        <script>
        var modal = document.querySelector("zdk-modal");
        function show() { 
            modal.show();
            modal.timeout(5000);
        };
        setTimeout( function() { modal.width = 500; show(); }, 2000);
        </script>
    </body>
    </html>

## Compatibility

| Browser          | status   |
|:-----------------|:--------:|
| Chrome           | ok       |
| Firefox          | ok       |
| Safari           | ok       |
| android (chrome) | ok       |
| IOS (safari)     | ok       |
