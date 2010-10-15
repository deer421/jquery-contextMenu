# jQuery context menu

jQuery plugin that shows a custom context menu when right clicking something. Super simple implementation.

The best way to try it out is to try the demo in test.html. 

## Basic calling syntax: 

    // it basically takes to parameters, a name that becomes the context menu´s id and an object with the context menu items. 

    $("selector").contextMenu('context-menu-1', {   // selector is for the elements that should launch our context menu.
        'Context Menu Item 1': {
            click: function(element){  // element is the jquery obj clicked on when context menu launched
                alert('Menu item 1 clicked');
                element.css({backgroundColor: 'pink'}); // just as example the clicked items backgorund is changed
            },
            class: "custom-class1" // a custom css class for this menu item (usable for styling)
        },
        'Second menu item': {
            click: function(element){ alert('second clicked'); },
            class: "custom-class2"
        }
    });

## Markup, and css

All context menus gets the class 'context-menu', so it´s quite easy to keep a consistent look over multiple menus. The look is all up to you and the structure of a menu looks like this:

    <ul id="contextMenu" class="context-menu">
      <li class="custom-class1"><a href="#">Context Menu Item 1</a></li>
      <li class="custom-class2"><a href="#">Second menu item</a></li>
    </ul>
    
Style it however you want with CSS, it does not come with any predefined styles so thats completely up to you.

## Callback

In the example above, when a user clicks on the first context menu item, the original element that launched the context menu is passed in as the only argument for the click callback. Thus, we can make the clicked element green by doing this: 

    clickFirstItem = function(element){  
        element.css({color: "green"});
    }

    $(".targets").contextMenu({
        'Context Menu Item 1': {
            click: clickFirstItem,
            class: "menu-item-1" 
        }
    });

Simple, yet powerful. 


## License

Copyright (c) 2010 [Jonas Arnklint](http://fkw.se), released under the MIT license.

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.