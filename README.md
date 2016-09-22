# [jQuery asScrollbar](https://github.com/amazingSurge/jquery-asScrollbar) ![bower][bower-image] [![NPM version][npm-image]][npm-url] [![Dependency Status][daviddm-image]][daviddm-url] [![prs-welcome]](CONTRIBUTING.md#pull-requests)

> A jquery plugin that generate a styleable scrollbar.

## Table of contents
- [Main files](#main-files)
- [Quick start](#quick-start)
- [Usage](#usage)
- [Examples](#examples)
- [Options](#options)
- [Methods](#methods)
- [Events](#events)
- [No conflict](#no-conflict)
- [Browser support](#browser-support)
- [Bugs and feature requests](#bugs-and-feature-requests)
- [Changelog](#changelog)
- [Copyright and license](#copyright-and-license)

## Main files
```
dist/
├── jquery-asScrollbar.js
└── jquery-asScrollbar.min.js
```

## Quick start
Several quick start options are available:
### Download the latest build

 * [Development](https://raw.githubusercontent.com/amazingSurge/jquery-asScrollbar/master/dist/jquery-asScrollbar.js) - unminified
 * [Production](https://raw.githubusercontent.com/amazingSurge/jquery-asScrollbar/master/dist/jquery-asScrollbar.min.js) - minified

### Install From Bower
```sh
bower install jquery-asScrollbar --save
```

### Install From Npm
```sh
npm install jquery-asScrollbar --save
```

### Build From Source
If you want build from source:

```sh
git clone git@github.com:amazingSurge/jquery-asScrollbar.git
cd jquery-asScrollbar
npm install
npm install -g gulp-cli babel-cli
gulp build
```

Done!

## Usage
### Including files:

```html
<script src="/path/to/jquery.js"></script><!-- jQuery is required -->
<script src="/path/to/jquery-asScrollbar.js"></script>
```

### Required HTML structure

```html
<div class="example"></div>
```

### Initialization
All you need to do is call the plugin inside a `$(document).ready` function:

```javascript
$(document).ready(function() {
	$('.example').asScrollbar(); 
});
```

## Examples
There are some example usages that you can look at to get started. They can be found in the
[examples folder](https://github.com/amazingSurge/jquery-asScrollbar/tree/master/examples).


## Options
asScrollbar can accept an options object to alter the way it behaves. You can see the default options by call $.asScrollbar.setDefaults(). The structure of an options object is as follows:

```
{
  namespace: 'asScrollbar',

  skin: null,
  handleSelector: null,
  handleTemplate: '<div class="{{handle}}"></div>',

  barClass: null,
  handleClass: null,

  disabledClass: 'is-disabled',
  draggingClass: 'is-dragging',
  hoveringClass: 'is-hovering',

  direction: 'vertical',

  barLength: null,
  handleLength: null,

  minHandleLength: 30,
  maxHandleLength: null,

  mouseDrag: true,
  touchDrag: true,
  pointerDrag: true,
  clickMove: true,
  clickMoveStep: 0.3, // 0 - 1
  mousewheel: true,
  mousewheelSpeed: 50,

  keyboard: true,

  useCssTransforms3d: true,
  useCssTransforms: true,
  useCssTransitions: true,

  duration: '500',
  easing: 'ease' // linear, ease-in, ease-out, ease-in-out
}
```

## Methods
Methods are called on asScrollbar instances through the asScrollbar method itself.
You can also save the instances to variable for further use.

```javascript
// call directly
$().asScrollbar('destory');

// or
var api = $().data('asScrollbar');
api.destory();
```

### moveTo(position)
Move the scrollbar handle to the position.
```javascript
// move to 50px
$().asScrollbar('moveTo', '50');

// move to 50%
$().asScrollbar('moveTo', '50%');
```

### moveBy(size)
Move the scrollbar handle by the size.
```javascript
$().asScrollbar('moveBy', '10');
$().asScrollbar('moveBy', '10%');

$().asScrollbar('moveBy', '-10');
$().asScrollbar('moveBy', '-10%');
```

### enable()
Enable the scrollbar functions.
```javascript
$().asScrollbar('enable');
```

### disable()
Disable the scrollbar functions.
```javascript
$().asScrollbar('disable');
```

### destroy()
Destroy the scrollbar instance.
```javascript
$().asScrollbar('destroy');
```

## Events
asScrollbar provides custom events for the plugin’s unique actions. 

```javascript
$('.the-element').on('asScrollbar::ready', function (e) {
  // on instance ready
});

```

Event   | Description
------- | -----------
ready   | Fires when the instance is ready for API use.
enable  | This event is fired immediately when the `enable` instance method has been called.
disable | This event is fired immediately when the `disable` instance method has been called.
destroy | Fires when an instance is destroyed. 

## No conflict
If you have to use other plugin with the same namespace, just call the `$.fn.asScrollbar.noConflict` method to revert to it.

```html
<script src="other-plugin.js"></script>
<script src="jquery-asScrollbar.js"></script>
<script>
  $.fn.asScrollbar.noConflict();
  // Code that uses other plugin's "$().asScrollbar" can follow here.
</script>
```

## Browser support
Safari | Firefox | Chrome | Opera | IE9+ | Edge
------ | ------- | ------ | ----- | -----| ----
   ✔   |    ✔    |    ✔   |   ✔   |   ✔  |  ✔  

As a jQuery plugin, you also need to see the [jQuery Browser Support](http://jquery.com/browser-support/).

## Bugs and feature requests
Anyone and everyone is welcome to contribute. Please take a moment to
review the [guidelines for contributing](CONTRIBUTING.md). Make sure you're using the latest version of jquery-asScrollbar before submitting an issue.

* [Bug reports](CONTRIBUTING.md#bug-reports)
* [Feature requests](CONTRIBUTING.md#feature-requests)

## Changelog
To see the list of recent changes, see [Releases section](https://github.com/amazingSurge/jquery-asScrollbar/releases).

## Copyright and license
Copyright (C) 2016 amazingSurge.

Licensed under [the LGPL license](LICENSE).

[⬆ back to top](#table-of-contents)

[bower-image]: https://img.shields.io/bower/v/jquery-asScrollbar.svg?style=flat
[bower-link]: https://david-dm.org/amazingSurge/jquery-asScrollbar/dev-status.svg
[npm-image]: https://badge.fury.io/js/jquery-asScrollbar.svg?style=flat
[npm-url]: https://npmjs.org/package/jquery-asScrollbar
[license]: https://img.shields.io/npm/l/jquery-asScrollbar.svg?style=flat
[prs-welcome]: https://img.shields.io/badge/PRs-welcome-brightgreen.svg
[daviddm-image]: https://david-dm.org/amazingSurge/jquery-asScrollbar.svg?style=flat
[daviddm-url]: https://david-dm.org/amazingSurge/jquery-asScrollbar
