# meedee
Easy event binding to MIDI events in Chrome.

##enable MIDI
[chrome://flags/#enable-web-midi]

##usage
```javascript
//log all key/slider/knob movement
Meedee.on('any', function(value, event){
	console.log('inputID:', event.data[1], 'value:', value);
});
```

```javascript
//example slider at input 0, MIDI range is 0..127
Meedee.on(0, function(value){
	console.log('slider at:', 100 / 127 * value, '%');
});
```

```javascript
//example button at input 32, MIDI range is 0..127
Meedee.on(32, function(value, event){
	console.log('button is', (value === 127) ? 'on' : 'off', 'receivedTime:', event.receivedTime);
});
```
