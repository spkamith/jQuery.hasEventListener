"hasEventListener" plugin for [jQuery](http://jquery.com/) (version 1.2.3+ tested)
================================

Description
------------
A jQuery plugin which tests if a dom element actually has a particular event listener bound to it.
[More infos ?](https://twitter.com/#!/search/_sebastienp%20hasEventListener)

Demo
-----
A quick demo is available here : [http://jsfiddle.net/sebastienp/eHGqB](http://jsfiddle.net/sebastienp/eHGqB/)

Setup
------
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="utf-8"/>
            <title>Page title</title>
        </head>
        <body>
            <!-- Some HTML tags -->
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.5.0/jquery.min.js"></script>
            <script scr="jquery.hasEventListener-2.0.0.min.js"></script>
            <!-- Some other jQuery plugins and/or scripts, order matters ! -->
        </body>
    </html>

1.0.5 Usage
------------
* `$.hasEventListener(dom_element);` --> Boolean
* `$.hasEventListener(dom_element, "event");` --> Boolean
* `$.hasEventListener(dom_element, "event.namespace");` --> Boolean
* `$("selector:hasEventListener");` --> jQuery object
* `$("selector:hasEventListener(event)");` --> jQuery object
* `$("selector:hasEventListener(event.namespace)");` --> jQuery object
* `$("selector").hasEventListener();` --> jQuery object
* `$("selector").hasEventListener("event");` --> jQuery object
* `$("selector").hasEventListener("event.namespace");` --> jQuery object

2.0.0 API roadmap
------------------
    tested_element: (DOM Element or plain Object) where to check for event presence.
    mode: (String) "!live" or "!delegate", for live/delegated event presence test.
    type: (String) type of the event to test presence for. e.g. "click".
    namespace: (String) namespace of the event to test presence for. e.g. ".namespaced".
    handler: (Function) event handler to test presence for.

* `jQuery.hasEventListener(tested_element, [mode][type][namespace], [handler])` --> Boolean
* `:hasEventListener[([mode][type][namespace])] Selector` --> jQuery object
* `.hasEventListener([mode][type][namespace], [handler])` --> jQuery object

**Important notes :**
* `handler` used with `mode` currently only works with jQuery 1.4.2+.

2.0.0 API examples
-------------------
* `$.hasEventListener($("#tabs li")[0], "!delegate click.tab_widget");` returns `true` or `false`.
* `$("#tabs li:hasEventListener(!delegate click.tab_widget)");` returns a jQuery object.
* `$("#tabs li").hasEventListener("!delegate click.tab_widget");` returns a jQuery object.
* `$.hasEventListener($({}).bind("custom_event", function () {})[0], "custom_event");` returns `true`.
* `$({}).bind("custom", function () {}).hasEventListener("custom");` returns a jQuery object.

They talked about "hasEventListener"
-------------------------------------
* [http://sullerton.com/2011/01/jquery-haseventlistener-and-developer-collaboration](http://sullerton.com/2011/01/jquery-haseventlistener-and-developer-collaboration)
* [http://snipplr.com/view/48107/jquery-fancy-select-dropdown-menu](http://snipplr.com/view/48107/jquery-fancy-select-dropdown-menu)

Special thanks
---------------
* Julian Jelfs - [Blog](http://julianjelfs.wordpress.com/) - [Twitter](http://twitter.com/julianjelfs)

Licence
--------
Copyright (c) 2011 Sebastien P.

[http://twitter.com/_sebastienp](http://twitter.com/_sebastienp)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.