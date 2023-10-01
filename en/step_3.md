### Different resting head positions

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

At the moment, the micro:bit records a movement whenever the micro:bit is **not** level.

For this project, the micro:bit will be placed under a pillow as it would be uncomfortable to wear it on your head!

When you lie down, the weight of your head on your pillow will probably roll the micro:bit so that it is not completely level.

This will be the **resting position**. 

You need to record a movement only if the micro:bit is rolled away from the resting position. 

</div>
</div>

### Check for movement to the LEFT from the resting position

You need to know if there is a difference between the resting position and the current roll position.

--- task ---

From the `Math`{:class='microbitmath'} menu, get a `0 - 0`{:class='microbitmath'} block.

Place it in the `-10` of the `<`{:class='microbitlogic'} comparison block.

--- /task ---

--- task ---

Open the `Variables`{:class='microbitvariables'} menu and click **Make a Variable**.

Name your new variable `restingPosition`.

--- /task ---

--- task ---

From the `Variables`{:class='microbitvariables'} menu, get the `restingPosition`{:class='microbitvariables'} block. 

Place it in the first `0` on the left of the `0 - 0`{:class='microbitmath'} block. 

--- /task ---

--- task ---

Change the `0` on the right of the `-`{:class='microbitmath'} to `10`.

Your code should look like this:

```microbit
let movements = 0
basic.forever(function () {
    let restingPosition = 0
    if (input.rotation(Rotation.Roll) < restingPosition - 10 || input.rotation(Rotation.Roll) > 10) {
        movements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        basic.clearScreen()
    }
})
```

--- /task ---

### Check for movement to the RIGHT from the resting position

--- task ---

From the `Math`{:class='microbitmath'} menu, get a `0 + 0`{:class='microbitmath'} block.

Place it in the `10` of the `>`{:class='microbitlogic'} comparison block.

--- /task ---

--- task ---

From the `Variables`{:class='microbitvariables'} menu, get another `restingPosition`{:class='microbitvariables'} block. 

Place it in the first `0` on the left of the `0 + 0`{:class='microbitmath'} block.

--- /task ---

--- task ---

Change the `0` on the right of the `+`{:class='microbitmath'} to `10`.

Your code should look like this:

```microbit
let movements = 0
basic.forever(function () {
    let restingPosition = 0
    if (input.rotation(Rotation.Roll) < restingPosition - 10 || input.rotation(Rotation.Roll) > restingPosition + 10) {
        movements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        basic.clearScreen()
    }
})
```

--- /task ---

### Set a new resting position after each movement

Each time the micro:bit is rolled to a new resting position, you need to set the current position as the new resting position, so you can use it in your comparison.

--- task ---

From the `Variables`{:class='microbitvariables'} menu, get the `set`{:class='microbitvariables'} block. 

Place it under the `pause`{:class='microbitbasic'} block.

--- /task ---

--- task ---

Duplicate the `rotation`{:class='microbitinput'} block and place it in the `0` of the `set`{:class='microbitvariables'} block.

Your code should look like this:

```microbit
let restingPosition = 0
let movements = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < restingPosition - 10 || input.rotation(Rotation.Roll) > restingPosition + 10) {
        movements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        restingPosition = input.rotation(Rotation.Roll)
        basic.clearScreen()
    }
})
```

--- /task ---

--- task ---

When you make a change to a code block in the code editor panel, the simulator will restart.

**Test your program**

+ Move from the centre of the micro:bit to the right or left. 

The LEDs will light up and stay on for a short time. 
**Keep your mouse still until the LEDs turn off.**

+ When the LEDs turn off, move from the new position (your resting position) to the right or left again. 

The LEDs will light up and stay on for **a short time**.

Repeat this process to check that the LEDs only turn on when there is movement away from the resting position.

--- /task ---

### Let the micro:bit come to rest

You should give the micro:bit some time to come to rest before setting the new `restingPosition`{:class='microbitvariables'} to the variable.

--- task ---

Change the value in `pause`{:class='microbitbasic'} from `100` to `5 seconds`.

```microbit
let restingPosition = 0
let movements = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < restingPosition - 10 || input.rotation(Rotation.Roll) > restingPosition + 10) {
        movements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(5000)
        restingPosition = input.rotation(Rotation.Roll)
        basic.clearScreen()
    }
})
```

--- /task ---

--- task ---

**Test your program**
+ Move from the centre of the micro:bit to the right or left. 

The LEDs will light up and stay on for **five seconds**. 
**Keep your mouse still until the LEDs turn off.**

+ When the LEDs turn off, move from the new position (your resting position) to the right or left again. 

The LEDs will light up and stay on for five seconds again.

--- /task ---

Next, you are going to use the `A+B` button press event to **reset** your sleep tracker!
