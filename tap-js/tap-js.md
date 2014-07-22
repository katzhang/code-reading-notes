[Github repo](https://github.com/alexgibson/tap.js)

Similar to what Fastclick.js does but a simplified version. Also there is an optional jQuery wrapper that utilizes [jQuery special events API](http://benalman.com/news/2010/03/jquery-special-events/).

The basic idea is create a custom event `tap` when `touchend` fires, as long as certain conditions are met (touches did not move, the event is not `mouseup`, .etc)

Creating custom events:

	if (window.CustomEvent) {
		evt = new window.CustomEvent('tap', {
			bubbles: true,
			cancelable: true
		});
	} else {
		evt = document.createEvent('Event');
		evt.initEvent('tap', true, true);
	}
	
Check if `CustomEvent()` exists first. If no, use `createEvent()` as a fall-back.

	el.addEventListener('touchstart', this, false);
	
	...
	
	Tap.prototype.handleEvent = function(e) { ... };
	
Pass in `this` the object as the second argument of `addEventListner` means that `addEventListner` will automatically look for a method called `handleEvent` and use it as the event handler function.