# dialog

Beginnings of a polyfill for HTML dialog (using x-tags).

**Note: this is barely functional and not fully compliant with the [spec](http://www.w3.org/html/wg/drafts/html/master/interactive-elements.html#the-dialog-element)**.

# Example

```html
<dialog open="">An open dialog</dialog>
```

or:

```js
document.addEventListener('DOMComponentsLoaded', function() {'use strict';

var dialog = document.createElement('dialog');
dialog.appendChild(document.createTextNode('Hello world!'));
document.body.appendChild(dialog);
dialog.show();
setTimeout(function () {
	dialog.close('Later all!');
	alert(dialog.returnValue);
}, 2000);

});
```

# Download it

Clone and reference x-tag-components.js and src/main.js in your HTML as in demo/index.html.

# Dev Setup

Fork this repo, rename it, then clone it.

```
$ npm install	// install bower tasks
$ bower install	// install components
$ grunt build   // build
$ grunt bump-push  // bump the version number, tag it and push to origin master
```

Note, however, that I am currently manually commenting out the line in
x-tag-components.js (line 774) which throws an error on encountering a
hyphen in the name. This is because our dialog is a polyfill.

# Links

* [Yeoman X-Tag Generator](https://github.com/x-tag/x-tag-generator)
* [X-Tags Docs](http://x-tags.org/docs)
* [Guide for creating X-Tag Components](https://github.com/x-tag/core/wiki/Creating-X-Tag-Components)
* [Using X-Tag components in your applications](https://github.com/x-tag/core/wiki/Using-our-Web-Components-in-Your-Application)
