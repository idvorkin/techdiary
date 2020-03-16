# Hacking the web for fun and profit`

Now a days javascript and HTML are the assembly language of the web (I first [said this in 2012](http://ig2600.blogspot.com/2012/05/assembly-to-javascript-tsrs-to.html)). While still stuff is fun, it's very brittle because 1) the approach is brittle, and 2) everytime the code changes, which it will everything will break.

<!-- vim-markdown-toc GFM -->

- [Script Injection](#script-injection)
    - [Bookmarklets](#bookmarklets)
    - [Grease Monkey](#grease-monkey)
- [Console Tricks](#console-tricks)
    - [Load Jquery](#load-jquery)
    - [CSS selectors](#css-selectors)
- [Debugging 101](#debugging-101)
    - [Force reloading](#force-reloading)
    - [Capturing an object for later use](#capturing-an-object-for-later-use)
    - [Black boxing](#black-boxing)
    - [Event Handlers](#event-handlers)
- [Real life examples](#real-life-examples)
    - [Reverse Engineering Fly out TOC](#reverse-engineering-fly-out-toc)
    - [Automating todo item creation in omnifocus for web](#automating-todo-item-creation-in-omnifocus-for-web)
- [Other resources](#other-resources)

<!-- vim-markdown-toc -->

## Script Injection

### Bookmarklets

Turns out you can stick javascript in the address bar, that's a bookmarklet. Here it is from the [way back machine](http://ig2600.blogspot.com/2012/05/assembly-to-javascript-tsrs-to.html))

### Grease Monkey

Called Taper Monkey for chrome, it autoloads a script when you enter a webpage. Useful to personalize websites via css and javascript.

## Console Tricks

### Load Jquery

### CSS selectors

I always forget these, but it matters as that's how you select elements in jquery

A full [summary](https://www.w3schools.com/cssref/css_selectors.asp), below are some I often use.

- \$(.class)
- \$(#id)
- \$(element) #e.g. h1

## Debugging 101

### Force reloading

Often needed for CSS -
* A) C-S-R
* Network Tab -> Disable caching

### Capturing an object for later use

Often there's a useful object, that's only available in the closure. You can always assign a refernce on window e.g.

    window.foo = foo_from_within_a_closure_found_from_debugging

### Black boxing

### Event Handlers

## Real life examples

These should break all the time, and be of minimal interst to anyone but Igor, but it's my blog so there.

### Reverse Engineering Fly out TOC

OK, I like the fly out ToC in hack MD.

### Automating todo item creation in omnifocus for web

**Too painful - got into some react/redux sync model, gave up**

Ominfocus doesn't supprot APIs, so we need to automate the web.

In omnifocus, you can add a task by pressing the 'c' key, which brings up a dialog. We can "hook that", by setting a breakpoing on global keypress events.

From there, we get into a closure that has an interesting object. Copy that to global scope.

## Other resources

I first had this idea back in 2012.
