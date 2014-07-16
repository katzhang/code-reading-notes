[Github repo](https://github.com/ftlabs/fastclick/blob/master/lib/fastclick.js)

Normally when `click` event is being triggered on mobile devices, a sequence of events take place: first `touchstart` is fired immediately, followed by `touchend`, then after some time interval `click`. A time delay of over 300ms exists between the tap takes place and the `click` event fires. To make the user experience more responsive, Fastclick.js removes that delay by canceling the default `click` event and, if requirements are met, fires `click` immediately on that attached element.

Basic code structure:

	/* constructor */
	function Fastclick(layer, options) {
	
		//options
		
		//instance properties to track touch events
		
		//bind events handlers to the layer
		//(click, touchstart, touchmove, touchend, touchcancel)

	}
	
	/* device detection methods */
	
	/* instance prototype methods */
	
	//determine if the layer still needs default click method
	//(some form elements and video do)
	
	//if needs focus
	
	//synthesize a click event with additional attributes 
	// so it can be tracked and dispatches it
	
	//device-specific fixes
	
	//touchstart handler: update instance properties(namely tracking events)
	
	//if touch has moved past a boundary
	
	//find labelled control for the given label element
	
	//touchend handler: if should send a click event at once
	
	//click handler: if a touch-generated click or a click that should be permitted
	
	/* destroy, remove event handlers */
	
	/* check if needed since some chrome versions now can remove the delay */
	
	/* attach method for instantiating a new FastClick object */
	
	
	


