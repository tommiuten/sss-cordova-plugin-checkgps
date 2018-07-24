# sss-checkGPS
Plugin to Check if GPS enabled on iOS and Android

## install
```
yourAppDir$ cordova plugin add https://github.com/tommiuten/sss-cordova-plugin-checkgps.git
```

## usage

```javascript
CheckGPS.check(function(){
    //GPS is enabled!

  },
  function(){
    //GPS is disabled!
    turnOnGpsDialog();

  });
  
  function turnOnGpsDialog() {

	/**
	 * @param message {string}       message to be displayed.
	 * @param description {string}   description of the propertie that you want change.
	 * @param callback {function}    callback function to send the index when a button is pressed
	 * @param title {string}         title of dialog
	 * @param buttons {array}        array with the buttons names with a max three names.
	 **/
	cordova.dialogGPS("Your GPS is Disabled, this app needs to be enable to works.", //message
		"Use GPS, with wifi or 3G.", //description
		function (buttonIndex) { //callback
			switch (buttonIndex) {
				case 0:
					break; //cancel
				case 1:
					break; //neutro option
				case 2:
					break; //user go to configuration
			}
		},
		"Please Turn on GPS", //title
		["Cancel", "Later", "Go"]
	); //buttons
}
```
