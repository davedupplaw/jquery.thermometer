jquery.thermometer
==================

An SVG thermometer for jQuery that provides programmatic control of the
temperature.

You can see demos of it's functionality at my website:

[http://david.dupplaw.me.uk/developer/jquery-thermometer](http://david.dupplaw.me.uk/developer/jquery-thermometer)

Installation
------------

You can install via bower:

    bower install jquery.thermometer --save

Usage
-----

The thermometer is a jQuery plugin that turns any div into an SVG thermometer.
Simply create the fixture on your page and then turn it into a jQuery object
by calling the thermometer() method.


    <div id="fixture"></div>
  
         ...
  
    $('#fixture').thermometer();


Options
-------

| Option        | Values        | Description                                     | Default |
|---------------|---------------|-------------------------------------------------|----------
| height        | Integer       | Sets the height of the thermometer in pixels.   |  700    |
| minValue      | Decimal       | Sets the minimum temperature                    |  0      |
| maxValue      | Decimal       | Sets the maximum temperature                    |  8      |
| startValue    | Decimal       | Sets the initial temperature of the thermometer |  0      |
| topText       | String        | The text at the top of the temperature scale    |  "8"    |
| bottomText    | String        | The text at the bottom of the temperature scale |  "0"    |
| textColour    | String        | The colour of the text on the temperature scale | #000000 |
| tickColour    | String        | The colour of the ticks on the temperature scale | #000000 |
| liquidColour  | #dddddd or fn | Colour of the liquid or fn to return colour     | #ff0000 |
| animationSpeed | Integer      | Time in milliseconds for the liquid to move     | 1000    |
| pathToSVG     | String        | If you need to store the SVG in another place   | "svg/thermo-bottom.svg" |
| valueChanged  | fn            | Callback for when the temperature has changed   | undefined |
| onLoad        | fn            | Callback for when the widget has fully loaded   | undefined |

To set the options simply pass them in as an object to the constructor:

    $('#fixture').thermometer( {
         minValue: 0,
         maxValue: 100,
         liquidColour: '#aa00bb'
    } );

Methods
-------

#### setValue( value )

Use `jq.thermometer( 'setValue', newValue )` to set the temperature of the thermometer.
If the new value is outside of the range of the thermometer, it will be clipped or capped.

#### setLiquidColour( newColour )

If you want to set the liquid colour directly, you can call *setLiquidColour* to update the
colour of the liquid. The value must be a string in this format: "#hhhhhh" where h is a hex value.
It must be the 6-digit form of the CSS colour code (this is due to the colour blending function in use).

