eventtarget.js
========

#### Javacript events for custom objects ####

### Usage ###

```html
<script src="EventTarget.js"></script>
<script>

	// Applying EventTarget to custom object

	var Car = function () {

		EventTarget.call( this );

		this.start = function () {

			this.dispatchEvent( { type: 'started', foo: 'bar' } );

		};

	};
	Car.prototype = new EventTarget();
	Car.prototype.constructor = Car;


	// Using events

	var car = new Car();
	car.addEventListener( 'started', function ( event ) {

		alert( 'vroom vroom!' );

	} );
	car.update();

</script>
```
