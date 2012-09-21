# ReflectaArduinoCore #

Reflecta Arduino Core binds the functions pinMode, digitalRead, digitalWrite, analogRead, and analogWrite to the ardu1 interface.  This is the Arduino library that enables the 'send' side of the Reflecta conversation.

> _Stability: Medium_

## Calling ReflectaArduinoCore from NodeJS

Simply load reflecta using

```
npm install reflecta
```

```javascript
var reflecta = require('reflecta');

reflecta.detect(function(error, boards, ports) {

    board = boards[0];

    if (board.ardu1) {
        board.ardu1.pinMode(ledPin, board.ardu1.OUTPUT);
        board.ardu1.digitalWrite(ledPin, 1);
    }
});
```

Reflecta will use npm to install and load this library automatically if the Arduino exposes the 'ardu1' interface.

A [simple but complete example](https://github.com/JayBeavers/node-reflecta/blob/master/samples/simple.js) can be found in the node-reflecta project.

## Release History

- 0.3.x: Analog & digital io, wire, and servo.

## Futures

- Add Advanced I/O functions (tone, pulseIn, etc.)
- Consider including other Arduino standard libraries such as Stepper, EEPROM, SD, SPI, SoftwareSerial, etc.