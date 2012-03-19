batterystatus
===========

This is an event that fires when a PhoneGap application detects a change in the battery status.

    window.addEventListener("batterystatus", yourCallbackFunction, false);

Details
-------

This event that fires when a PhoneGap application detects the percentage of battery has changed by at least 1 percent. It is also fired if the device has been plugged in or un-plugged.

The battery status handler will be called with an object that contains two properties:

- __level:__ The percentage of battery (0-100). _(Number)_
- __isPlugged:__ A boolean that represents whether or not the device is plugged in or not. _(Boolean)_

Typically, you will want to attach an event listener with `window.addEventListener` once you receive the PhoneGap 'deviceready' event.

Supported Platforms
-------------------

- iOS
- Android
- BlackBerry WebWorks (OS 5.0 and higher)

Quick Example
-------------

    window.addEventListener("batterystatus", onBatteryStatus, false);

    function onBatteryStatus(info) {
        // Handle the online event
       	console.log("Level: " + info.level + " isPlugged: " + info.isPlugged); 
    }

Full Example
------------

    <!DOCTYPE html>
    <html>
      <head>
        <title>PhoneGap Device Ready Example</title>

        <script type="text/javascript" charset="utf-8" src="phonegap.js"></script>
        <script type="text/javascript" charset="utf-8">

        // Call onDeviceReady when PhoneGap is loaded.
        //
        // At this point, the document has loaded but phonegap.js has not.
        // When PhoneGap is loaded and talking with the native device,
        // it will call the event `deviceready`.
        // 
	    function onLoad() {
    	    document.addEventListener("deviceready", onDeviceReady, false);
    	}

        // PhoneGap is loaded and it is now safe to make calls PhoneGap methods
        //
        function onDeviceReady() {
		    window.addEventListener("batterystatus", onBatteryStatus, false);
        }

        // Handle the batterystatus event
        //
        function onBatteryStatus(info) {
        	console.log("Level: " + info.level + " isPlugged: " + info.isPlugged); 
        }
        
        </script>
      </head>
      <body onload="onLoad()">
      </body>
    </html>