# Deforestation

## @showhint
```package
cakLand=github:climate-action-kits/pxt-climate-action-kit-land 
``` 
Add the ``||Input:on Button A Pressed||`` block
```blocks
input.onButtonPressed(Button.A, function () {
})
```
## @showhint
Add the ``||cakLandMotor:turn right motor at speed 0||`` 
block nested under ``||Input:on Button A Pressed||`` 
and change the speed to 50
```blocks
input.onButtonPressed(Button.A, function () {
    cakLandMotor.turnRight(50)
})
```
## @showhint
Add ``||basic:pause||`` block nested in the 
``||input:on Button A pressed||`` block and under 
``||cakLandMotor: turn right motor at speed||`` block.
Change the value of ``||basic:pause||`` to 1 second.
```blocks
input.onButtonPressed(Button.A, function () {
    cakLandMotor.turnRight(50)
    basic.pause(1000)
})
```
## @showhint
This step is to stop the motors from turning. 
Add ``||cakLandMotor:stop motors||`` block and
add it under the ``||basic:pause 1000||`` block

```blocks
input.onButtonPressed(Button.A, function () {
    cakLandMotor.turnRight(50)
    basic.pause(1000)
    cakLandMotor.stop()
})
``` 
## @showhint
Add another ``||basic:pause 1000||`` block after the ``||cakLandMotor:stop motors||`` block
```blocks
input.onButtonPressed(Button.A, function () {
    cakLandMotor.turnRight(50)
    basic.pause(1000)
    cakLandMotor.stop()
    basic.pause(1000)
})
``` 
## @showhint
Now its time to 
add the servo movement block from 
``||cakLandServos:set servo at P0 to position up||`` change the up position to half down.
```blocks
input.onButtonPressed(Button.A, function () {
    cakLandMotor.turnRight(50)
    basic.pause(1000)
    cakLandMotor.stop()
    basic.pause(1000)
    cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.HALF_DOWN)
})
```
## @showhint
After the ``||cakLandServos:servo||`` has opened, it should be closed after
1 second. Add ``||basic:pause||`` block and change the value to 1000 
```blocks
input.onButtonPressed(Button.A, function () {
    cakLandMotor.turnRight(50)
    basic.pause(1000)
    cakLandMotor.stop()
    basic.pause(1000)
    cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.HALF_DOWN)
    basic.pause(1000)
})
```
## @showhint
Next the ``||cakLandServos:servo||`` should move back to its initial position.
Add another ``||cakLandServos:set servo at P0 to position up||`` block. 
```blocks 
input.onButtonPressed(Button.A, function () {
    cakLandMotor.turnRight(50)
    basic.pause(1000)
    cakLandMotor.stop()
    basic.pause(1000)
    cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.HALF_DOWN)
    basic.pause(1000)
    cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.UP)
})
```
## @showhint
In this step a ``||loops:repeat||`` block is used to repeat the operation a certain number of time. 
Add the ``||loops:repeat||`` block and nest it under ``||input:on button A pressed||`` block and 
around or over the whole ``||cakLandMotor:motor||`` and ``||cakLandServos:servo||`` operation
```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        cakLandMotor.turnRight(50)
        basic.pause(1000)
        cakLandMotor.stop()
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.HALF_DOWN)
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.UP)
        basic.pause(1000)
    }
})
```
## @showhint
After the ``||loops:repeat||`` is done the ``||cakLandMotor:motor||`` has to stop.
Use ``||cakLandMotor:stop motors||`` block nested under the ``||input: on button A pressed||``
but outside the ``||loops:repeat||`` block
```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        cakLandMotor.turnRight(50)
        basic.pause(1000)
        cakLandMotor.stop()
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.HALF_DOWN)
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.UP)
        basic.pause(1000)
    }
    cakLandMotor.stop()
})
```
## @showhint
The operational steps are completed. Now to add some informational blocks.
Create a ``||Variables:seedsdropped||`` variable under the ``||Variables:Variables||`` drawer. There will be
three additional blocks added to the ``||Variables:Variables||`` drawer

## @showhint
Add ``||Variables: change seedsdropped by 1||`` nested under the ``||loops:repeat||`` loop which is nested under the 
``||input:on button A pressed loop||``
```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        cakLandMotor.turnRight(50)
        basic.pause(1000)
        cakLandMotor.stop()
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.HALF_DOWN)
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.UP)
        basic.pause(1000)
        seedsdropped += 1
    }
    cakLandMotor.stop()
})
```
## @showhint
The ``||Variables:Variables||`` needs to be always set to a starting number.
Use ``||Variables:set seedsdropped to 0||`` from the ``||Variables:Variables||`` drawer 
```blocks
let seedsdropped = 0
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        cakLandMotor.turnRight(50)
        basic.pause(1000)
        cakLandMotor.stop()
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.HALF_DOWN)
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.UP)
        basic.pause(1000)
        seedsdropped += 1
    }
    cakLandMotor.stop()
})
```
## @showhint
The last step is to continously display the value of the ``||Variables:Variable seedsdropped||``
Drag and drop a ``||basic:forever||`` and nest a ``||basic:showNumber||`` block under the ``||basic:forever||`` loop
```blocks
let seedsdropped = 0
basic.forever(function () {
    basic.showNumber(0)
})
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        cakLandMotor.turnRight(50)
        basic.pause(1000)
        cakLandMotor.stop()
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.HALF_DOWN)
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.UP)
        basic.pause(1000)
        seedsdropped += 1
    }
    cakLandMotor.stop()
})
```
## @showhint
Add the ``||Variables:variable seedsdropped||`` to the ``||basic:showNumber||``.
This would continously update the micro:bit LED display with the number of seeds dropped.
```blocks
let seedsdropped = 0
basic.forever(function () {
    basic.showNumber(seedsdropped)
})
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        cakLandMotor.turnRight(50)
        basic.pause(1000)
        cakLandMotor.stop()
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.HALF_DOWN)
        basic.pause(1000)
        cakLandServos.setServoPosition(cakLandServos.ServoPin.P0, cakLandServos.Position.UP)
        basic.pause(1000)
        seedsdropped += 1
    }
    cakLandMotor.stop()
})
```