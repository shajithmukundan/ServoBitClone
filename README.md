# MakeCode Package for [4tronix ServoBit Servo Controller Board](https://4tronix.co.uk/servobit)

The 4tronix ServoBit uses a PCA9685 to control 16 independent servos.
Helper commands are available to centre all servos, or set individual servos to any angle from -90 to +90 degrees

It is also possible to set the speed at which each servo moves to its new position, which gives a smoother operation

In addition, the 4tronix ServoBit contains a single FireLed status indicator which can be set to any colour and brightness
with a flashing function also available.


## Setting the servos

Set all 16 servos to position zero, centre:

```block
ServoBit.centreServos()
```

Set Servo 5 to +30 degrees:

```block
ServoBit.setServo(5, 30)
```

Set Servo 13 to -90 degrees:

```block
ServoBit.setServo(13, -90)
```

## Controlling servo movements and speeds
You can control the number of degrees per second that the servo moves. A typical servo would have a maximum speed of around 500 degrees per second.
Reasonable values for slower movements are between 30 and 200 degrees per second, although a range of 1 to 1000 is supported.
Setting the servo position whilst it is still moving, will cancel the movement command.
Creating a new movement command for a servo with an existing movement will cancel the first and then start the second.
You can also check if the servo has reached its target position, or wait until it has completed.

Move servo 5 to 30 degrees at 40 degrees per second:

```blocks
ServoBit.moveServo(5, 30, 40)
```

Check current actual position of servo 5:

```block
let variable = ServoBit.getServoActual(5)
```

Check current target positon for servo 5:

```block
let variable = ServoBit.getServoTarget(5)
```

Wait for servo 5 to complete its movement:

```block
ServoBit.waitServo(5)
```

## FireLed helpers

The 4tronix ServoBit has a single FireLed fitted to act as a status indicator.
This library defines some helpers for using it.
The LED is automatically updated after every setting

Clear LED:

```block
ServoBit.ledClear()
```

Set LED to Red:

```block
ServoBit.setLedColor(ServoBit.vColours(vColors.Red))
```

Set brightness of LED:

```block
ServoBit.ledBrightness(40)
```

Use the `startFlash(...)` function to start flashing the LED with a selected colour, eg. Green:

```block
ServoBit.startFlash(ServoBit.vColours(vColors.Green), 100)
```

Use the `stopFlash(...)` function to stop flashing the LED:

```block
ServoBit.stopFlash();
```


## Supported targets

* for PXT/microbit

## License

MIT
