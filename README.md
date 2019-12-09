# MakeCode Package for 4tronix ServoBit Servo Controller Board

The 4tronix ServoBit uses a PCA9685 to control 16 independent servos.
Helper commands are available to centre all servos, or set individual servos to any angle from -90 to +90 degrees

It is also possible to set the speed at which each servo moves to its new position, which gives a smoother operation

In addition, the 4tronix ServoBit contains a single Smart RGB status LED which can be set to any colour and brightness
and a flashing function is also available.


## Setting the servos

```blocks
// Set all 16 servos to the centre position
ServoBit.zeroServos();

// Set Servo 5 to +30 degrees
ServoBit.setServo(5, 30);

// Set Servo 13 to -90 degrees
ServoBit.setServo(13, -90);
```

## Smart RGB LED helpers

The 4tronix ServoBit has a single smart RGB LED (aka neopixel) fitted. This library defines some helpers
for using it.
The LED is automatically updated after every setting

```blocks
// Clear LED
ServoBit.ledClear();

// Set LED to Red
ServoBit.setLedColor(ServoBit.vColours(vColors.Red));

// Set brightness of LED
ServoBit.ledBrightness(40);

// Start Flashing the LED with Green
ServoBit.startFlash(ServoBit.vColours(vColors.Green), 100);

// Stop flashing the LED
ServoBit.stopFlash();
```


## Supported targets

* for PXT/microbit

## License

MIT
