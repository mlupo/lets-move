# Buggin' Around

## _ @unplugged
### Let's Drive This Buggy!
Okay! Let's move our robot for the first time! In this tutorial, we will write some short code to test out the code loading process, and the robot's movement.  

Then we will make the code more interesting by adding loops and beeps!

## _
### Take in Some Input
First we are going to use an ``||input:input||`` block to initiate movement! Bring a ``||input:on button A pressed||`` block from the ``||input:input||`` drawer into the workspace.  

```blocks
input.onButtonPressed(Button.A, function () {
})
```

## _
### Get Moving!
Click on the **Move Motor** drawer, then select the **Motors** subcategory.  

Find the **move Forward at speed 0** block, and drag it into ``||input:on button A pressed||``. Change the number **0** to **30**.  
Next, from the ``||Basic:basic||`` find the ``||Basic:pause (ms) 100||`` block, and add it underneath the **move** block in your code. Change the **100** to **1000** (or 1 second).

```blocks
input.onButtonPressed(Button.A, function () {
    // @highlight
    Kitronik_Move_Motor.move(Kitronik_Move_Motor.DriveDirections.Forward, 30)
    basic.pause(1000)
})
```
## _ @unplugged
### Hold on Wait a Minute!
Okay! Let's put this code on the micro:bit!  

If you've gotten this far tell the instructor you're ready to put this code on the micro:bit!

## _
### Make it Turn!
From the **Move Motor** drawer, find the **spin Left at speed 0** block, and place it under the ``||basic:pause (ms) 1000||`` block in your code.  

```blocks
input.onButtonPressed(Button.A, function () {
    Kitronik_Move_Motor.move(Kitronik_Move_Motor.DriveDirections.Forward, 30)
    basic.pause(1000)
    // @highlight
    Kitronik_Move_Motor.spin(Kitronik_Move_Motor.SpinDirections.Right, 30)
    basic.pause(250)
    Kitronik_Move_Motor.stop()
})
```

## _
### Make it Loop!
Now let's try to loop our existing code so that our buggy drives in a square pattern.  

From the ``||loops:loops||`` drawer, find the ``||loops:

## Thanks
Thanks for joining us!

```package
loops
input
kitronik-move-motor=github:KitronikLtd/pxt-kitronik-move-motor
```