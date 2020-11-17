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
Next, from the ``||Basic:basic||`` drawer find the ``||Basic:pause (ms) 100||`` block, and add it underneath the **move** block in your code. Change the **100** to **1000** (or 1 second).

```blocks
input.onButtonPressed(Button.A, function () {
    // @highlight
    Kitronik_Move_Motor.move(Kitronik_Move_Motor.DriveDirections.Forward, 30)
    basic.pause(1000)
})
```

## _
### But Also... Stop
Next, from the **Move Motor -> Motors** drawer, find the **stop** block and put it at the bottom of your code, in the ``||input:on button A pressed||`` block.

```blocks
input.onButtonPressed(Button.A, function () {
    Kitronik_Move_Motor.move(Kitronik_Move_Motor.DriveDirections.Forward, 30)
    basic.pause(1000)
    // @highlight
    Kitronik_Move_Motor.stop()
})
```

## _ @unplugged
### Hold on Wait a Minute!
Okay! Let's put this code on the micro:bit!  

If you've gotten this far tell the instructor you're ready to put this code on the micro:bit!

## _
### Make it Turn!
From the **Move Motor -> Motors** drawer, find the **spin Left at speed 0** block, and place it under the ``||basic:pause (ms) 1000||`` block in your code.  
Change the number **0** to **30**.

```blocks
input.onButtonPressed(Button.A, function () {
    Kitronik_Move_Motor.move(Kitronik_Move_Motor.DriveDirections.Forward, 30)
    basic.pause(1000)
    // @highlight
    Kitronik_Move_Motor.spin(Kitronik_Move_Motor.SpinDirections.Left, 30)
    Kitronik_Move_Motor.stop()
})
```
## _
From the ``||Basic:basic||`` drawer find the ``||Basic:pause (ms) 100||`` block, and add it underneath the **spin** block in your code.  
Change the **100** to **250**.

```blocks
input.onButtonPressed(Button.A, function () {
    Kitronik_Move_Motor.move(Kitronik_Move_Motor.DriveDirections.Forward, 30)
    basic.pause(1000)
    Kitronik_Move_Motor.spin(Kitronik_Move_Motor.SpinDirections.Left, 30)
    // @highlight
    basic.pause(250)
    Kitronik_Move_Motor.stop()
})
```

## _
### Make it Loop!
Now let's try to loop our existing code so that our buggy drives in a square pattern.

From the ``||loops:loops||`` drawer, find the ``||loops:repeat 4 times||`` block, and place it over the existing code in the ``||input:on button A pressed||`` block.  
If you place the ``||loops:loops||`` block carefully, it will snap perfectly in place, with all of your previous code inside of it.  

Either way, just make sure your code looks like the code in the hint!  

```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        Kitronik_Move_Motor.move(Kitronik_Move_Motor.DriveDirections.Forward, 30)
        basic.pause(1000)
        Kitronik_Move_Motor.spin(Kitronik_Move_Motor.SpinDirections.Left, 30)
        basic.pause(250)
        Kitronik_Move_Motor.stop()
    }
})
```

## _
### Let's test it out!
Upload your new code to the micro:bit, and see if your buggy turns in the circle! Talk to the instructor if things went really wrong!  

If things went really well, click Finish, then your instructor will show you how to add beeps and animations (if there is time)!



```package
loops
input
kitronik-move-motor=github:mlupo/pxt-kitronik-move-motor
```