# Atem
Implementation of BlackMagicDesign's ATEM communication protocol (version 6.1) in javascript (written for nodejs).

## Usage
### Connect to an atem
To connect to an atem, simply create a new `Atem` instance and pass an IP address as first parameter of the constructor:
```js
var Atem = require('atem') // Load the atem module
var myAtemDevice = new Atem("10.1.0.9") // Create a new Atem instace with an IP address
```
You can also create a new `Atem` instance and specify the IP address later on. Notice that if you do this, you need to call the `connect` method yourself:
```js
var Atem = require('atem') // Load the atem module
var myAtemDevice = new Atem() // Create a new Atem instace without an IP address
myAtemDevice.ip = "10.1.0.9" // specify the ip address
myAtemDevice.connect() // manually connect to the atem
```
### Receive notifications from your atem
To receive notifications about the connection state:
```js
var Atem = require('atem') // Load the atem module
var myAtemDevice = new Atem() // Create a new Atem instace without an IP address
myAtemDevice.on('connectionStateChange', function(state) {
  console.log('state', state);
});
```
You can read more about all the available events in the [API reference](http://dev1an.github.io/Atem/Device.html)
