## Track and display

### Open MakeCode

To start creating your micro:bit project, you need to open the MakeCode editor.

--- task ---

Open the MakeCode editor at [makecode.microbit.org](https://makecode.microbit.org){:target="_blank"}

--- collapse ---

---
title: Offline version of the editor
---

There is also a [downloadable version of the MakeCode editor](https://makecode.microbit.org/offline-app){:target="_blank"}.

--- /collapse ---

--- /task ---

### First micro:bit project?

[[[makecode-tour]]]

### Create your project

Once the editor is open, you will need to create a new project and give your project a name. 

--- task ---

Click on the **New Project** button.

![The new project button in MakeCode.](images/new-project-button.png)

--- /task ---

--- task ---

Give your new project the name `Sleep tracker` and click **Create**.

![The name 'Sleep tracker' written in the New Project dialogue box.](images/sleep-tracker.png)

**Tip:** To make it easier to find your project later, give it a helpful name that relates to the activity you’re creating.

--- /task ---

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will program the micro:bit to sense if it moves and make the LEDs light if it does.
</div>
<div>

![Animation showing the LEDs turning on as the micro:bit simulator is tilted left and right.](images/tilt-test.gif)

</div>
</div>

The micro:bit uses a sensor called an accelerometer to sense when it has been rolled.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">

<span style="color: #0faeb0">Accelerometers</span> are used in many devices. They can tell if we're moving, like when you run or jump, and they help our tablets and smartphones know which way up they're being held. These clever sensors make games more fun, letting you control how a character moves by tilting a controller.

</p>

### Roll

You need to check **if** the micro:bit has been rolled right **or** left. 

If this happens, you will assume there has been movement during sleep.

--- task ---

From the `Logic`{:class='microbitlogic'} menu, drag an `if`{:class='microbitlogic'} block and place it inside the `forever`{:class='microbitbasic'}</code> block.

<img src="images/if-block-location.png" alt="The Logic menu with the 'if...then' block highlighted." width="350"/>

--- /task ---

--- task ---

Open the `Logic`{:class='microbitlogic'} menu again and take an `or`{:class='microbitlogic'} block.

<img src="images/or-block-location.png" alt="The bottom part of the Logic menu, showing the location of the 'or' block in the 'Boolean' section." width="150"/>

Place it in the `true` section of the `if`{:class='microbitlogic'} block.

```microbit
basic.forever(function () {
    if (false || false) {
    	
    }
})
```

--- /task ---

Now you need to add the **two** conditions either side of the **or**. 

This will mean that the code inside your `if`{:class='microbitlogic'} block will run if **either** condition is met.

--- task ---

From the `Logic`{:class='microbitlogic'} menu, drag the `0 < 0`{:class='microbitlogic'} comparison block.

Place it on the left side of the `or`{:class='microbitlogic'} block.

```microbit
basic.forever(function () {
    if (0 < 0 || false) {
    	
    }
})
```

--- /task ---

--- task ---

From the `Input...more`{:class='microbitinput'} menu, drag a `rotation`{:class='microbitinput'} block.

<img src="images/rotation-location.png" alt="The 'Input...more' menu with the 'rotation' block highlighted." width="350"/>

Place it inside the first `0` in the `0 < 0`{:class='microbitlogic'} comparison block.

--- /task ---

--- task ---

Use the drop-down menu to change `pitch`{:class='microbitinput'} to `roll`{:class='microbitinput'}. 

--- /task ---

--- task ---

Change the `0` to `-10`. This will check if the micro:bit is rolled 10° to the **left**.

--- /task ---

Your code should look like this:

```microbit
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < -10 || false) {
    	
    }
})
```

--- task ---

**Debug** 

Check you have:

+ Clicked on the Input **more** menu, not the normal Input menu
+ Changed the second value from `0` to **`-10`**, not `10`

--- /task ---

--- task ---

Right-click on the `<`{:class='microbitlogic'} comparison block and select **Duplicate**.

--- /task ---

You will now have two comparison blocks.

--- task ---

Drag the duplicated comparison block to the right of the `or`{:class='microbitlogic'} block.

--- /task ---

--- task ---

Use the drop-down menu to change the less than symbol (`<`{:class='microbitlogic'}) to a greater than symbol (`>`{:class='microbitlogic'}). 

--- /task ---

--- task ---

Change the `-10` to `10`. This will check if the micro:bit is rolled 10° to the **right**.

![A demo of duplicating the comparison block and making the changes.](images/duplicting-rotation-comparison.gif)

--- /task ---

### Keep a count

When either condition is met, the micro:bit will have been rolled left or right.

You need to:
+ Keep a count of sleep movements
+ Light the LEDs

To keep a count of sleep movements, you will use a variable.

--- task ---

Open the `Variables`{:class='microbitvariables'} menu and click **Make a Variable**.

<img src="images/variable-menu.png" alt="The Variables block menu with the 'Make a variable' button highlighted." width="350"/>

--- /task ---

--- task ---

Name your new variable `movements`. 

<img src="images/movements-variable-name.png" alt="The 'New variable name' window, with the name 'movements' written in the box." width="400"/>

--- /task ---

You will increase the `movements` variable by `1` each time a movement is detected.

--- task ---

From the `Variables`{:class='microbitvariables'} menu, get the `change movements`{:class='microbitvariables'} block. 

<img src="images/change-movements.png" alt="The Variables menu with the 'change movements by 1' block highlighted." width="350"/>

--- /task ---

--- task ---

Place it inside the `if`{:class='microbitlogic'} block.

```microbit
let movements = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < -10 || input.rotation(Rotation.Roll) > 10) {
        movements += 1
    }
})
```

--- /task ---

### Light the LEDS

You can use the LEDs on the micro:bit to show that there has been a movement. 

This will help you test your project.

--- task ---

From the `Basic`{:class='microbitbasic'} menu, drag a `show icon`{:class='microbitbasic'} block.

<img src="images/show-icon-location.png" alt="The Basic menu with the 'show icon' block highlighted." width="350"/>

--- /task ---

--- task ---

Place it under the `change movements`{:class='microbitvariables'} block.

--- /task ---

--- task ---

From the `Basic`{:class='microbitbasic'} menu, drag a `pause`{:class='microbitbasic'} block.

Place it under the `show icon`{:class='microbitbasic'} block.

--- /task ---

--- task ---

From the `Basic`{:class='microbitbasic'} menu, drag a `clear screen`{:class='microbitbasic'} block.

Place it under the `pause`{:class='microbitbasic'} block.

Your code should look like this:

```microbit
let movements = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < -10 || input.rotation(Rotation.Roll) > 10) {
        movements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        basic.clearScreen()
    }
})
```

--- /task ---

--- task ---

**Test your program**

When you make a change to a code block in the code editor panel, the simulator will restart.

+ Move over the right or left of the micro:bit 

The LEDs will light up and show a heart icon.

+ Move away from the micro:bit 

The LEDs will continue to flash until the micro:bit is in a level position.

--- /task ---

Next, you are going to set different resting positions, because it is rare that someone will sleep in a perfectly level position all night!
