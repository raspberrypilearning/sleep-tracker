## Track and display

### Opening MakeCode

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

![The new project button inside MakeCode](images/new-project-button.png)

--- /task ---

--- task ---

Give your new project the name `Sleep tracker` and click **Create**.

![The name 'Sleep tracker' written in the New Project dialogue box](images/sleep-tracker.png)

**Tip:** Give your project a helpful name that relates to the activity you’re creating. This will make it easier to find if you create other projects on MakeCode.

--- /task ---

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step you will program the micro:bit to sense if it moves and make the LEDs light if it does.
</div>
<div>

![Animation showing the LEDs turning on, as the micro:bit simulator is tilted left and right](images/tilt-test.gif)

</div>
</div>

The micro:bit uses a sensor called an accelerometer to sense when it has been rolled.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">

<span style="color: #0faeb0">Accelerometers</span> are used in many devices. They can tell if we're moving, like when you run or jump, and they help our tablets and smartphones know which way they're being held. These clever sensors make games more fun, letting you control how a character moves by tilting a controller.

</p>

### Roll

You need to check **if** the micro:bit has been rolled right **or** left. 

If this happens, you will assume there has been movement during sleep.

--- task ---

From the <code style="background-color: #00A4A6">Logic</code> menu, drag out an <code style="background-color: #00A4A6">if</code> block and place it inside the <code style="background-color: #1E90FF">forever</code> block.

<img src="images/if-block-location.png" alt="The Logic menu, with the 'if .. then' block highlighted" width="350"/>

--- /task ---

--- task ---

Open the <code style="background-color: #00a4a6">Logic</code> menu again and take an <code style="background-color: #00a4a6">or</code> block. 

<img src="images/or-block-location.png" alt="The bottom part of the Logic menu, showing the location of the 'or' block in the 'Boolean' section" width="150"/>

Place it in the `true` section of the <code style="background-color: #00a4a6">if</code> block. 

<div style="position:relative;height:calc(175px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_d6KcohD3RCjK" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

Now you need to add the **two** conditions either side of the **or**. 

This will mean that the code inside your <code style="background-color: #00a4a6">if</code> block will run if **either** condition is met.

--- task ---

From the <code style="background-color: #00A4A6">Logic</code> menu, drag out the <code style="background-color: #00a4a6">0 < 0</code> comparison block.

Place it on the left side of the <code style="background-color: #00a4a6">or</code> block.

<div style="position:relative;height:calc(150px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_6zUfDw2k274E" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

From the <code style="background-color: #D400D4">Input ... more</code> menu, drag out a <code style="background-color: #D400D4">rotation</code> block.

<img src="images/rotation-location.png" alt="The 'Input ... more' menu, with the 'rotation' block highlighted" width="350"/>

Place it inside the first `0` in the <code style="background-color: #00a4a6">0 < 0</code> comparison block.

--- /task ---

--- task ---

Use the dropdown to change <code style="background-color: #D400D4">pitch</code> to <code style="background-color: #D400D4">roll</code>. 

--- /task ---

--- task ---

Change the `0` to `-10`, to check if the micro:bit is rolled 10° to the **left**.

--- /task ---

Your code should look like this:

<div style="position:relative;height:calc(100px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_XefbaDJ4uTvi" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- task ---

**Debug** 

Check you have:

+ Clicked on the Input **more** menu, not the normal Input menu.
+ Changed the second value from `0` to **`-10`**, not `10`.

--- /task ---

--- task ---

Right click on the <code style="background-color: #00a4a6">0 < 0</code> comparison block and select Duplicate.

--- /task ---

You will now have two comparison blocks.

--- task ---

Drag the duplicated comparison block to the right of the <code style="background-color: #00a4a6">or</code> block.

--- /task ---

--- task ---

Use the dropdown to change the less than symbol (<code style="background-color: #00a4a6"><</code>) to a greater than symbol (<code style="background-color: #00a4a6">></code>). 

--- /task ---

--- task ---

Change the `-10` to `10`, to check if the micro:bit is rolled 10° to the **right**.

![A demo of duplicating the comparison block and making the changes.](images/duplicting-rotation-comparison.gif)

--- /task ---

### Keep a count

When either condition is met, the micro:bit will have been rolled left or right.

You need to:
+ Keep a count of sleep movements
+ Light the LEDs

To keep a count of sleep movements, you will use a variable.

--- task ---

Open the <code style="background-color: #dc143c">Variables</code> menu and click `Make a Variable`.

<img src="images/variable-menu.png" alt="The Variables block menu, open with the 'Make a variable' button highlighted" width="350"/>

--- /task ---

--- task ---

Name your new variable `movements`. 

<img src="images/movements-variable-name.png" alt="The 'New variable name' window, with the name 'movements' written in the box" width="400"/>

--- /task ---

You will increase the movements variable by `1` each time a movement is detected.

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, grab the <code style="background-color: #dc143c">change movements</code> block. 

<img src="images/change-movements.png" alt="The Variables menu with the 'change movements by 1' block highlighted" width="350"/>

--- /task ---

--- task ---

Place it inside the <code style="background-color: #00A4A6">if</code> block.

--- /task ---

<div style="position:relative;height:calc(100px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_iT2FmD3d7TE2" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

### Lighting the LEDS

You can use the LEDs on the micro:bit to show there has been a movement. 

This will help you test your project.

--- task ---

From the <code style="background-color: #1E90FF">Basic</code> menu, drag a <code style="background-color: #1E90FF">show icon</code> block.

<img src="images/show-icon-location.png" alt="The Basic menu, open with the 'show icon' block highlighted" width="350"/>

--- /task ---

--- task ---

Place it under the <code style="background-color: #dc143c">change movements</code> block.

--- /task ---

--- task ---

From the <code style="background-color: #1E90FF">Basic</code> menu, drag a <code style="background-color: #1E90FF">pause</code> block.

Place it under the <code style="background-color: #1E90FF">show icon</code> block.

--- /task ---

--- task ---

From the <code style="background-color: #1E90FF">Basic</code> menu, drag a <code style="background-color: #1E90FF">clear screen</code> block.

Place it under the <code style="background-color: #1E90FF">pause</code> block.

--- /task ---

Your code should look like this:

<div style="position:relative;height:calc(250px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_UL1DcWbiR5Ey" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- task ---

**Test** your program:

When you make a change to a code block in the code editor panel, the simulator will restart.

+ Move over the right or left of the micro:bit. 

The LEDs will light up and show a heart icon.

+ Move away from the micro:bit 

The LEDs will continue to flash until the micro:bit is at a level position.

--- /task ---

### Dealing with different resting head positions

At the moment, the micro:bit is recording a movement whenever the micro:bit is **not** level.

For this project, the micro:bit will be placed under a pillow (as it would be uncomfortable to wear it on the head!)

When you lie down, the weight of your head on your pillow will probably roll the micro:bit so that it is not completely level.

This will be the **resting position**. 

You need to record a movement only if the micro:bit is rolled away from the resting position. 

In other words, you need to know if there is a difference between the resting position and the current roll position.

### Check for movement to the LEFT from the resting position

--- task ---

From the <code style="background-color: #9400D3">Math</code> menu, grab a <code style="background-color: #9400D3">0 - 0</code> block.

Place it in the `-10` of the <code style="background-color: #00A4A6"><</code> comparison block.

--- /task ---

--- task ---

Open the <code style="background-color: #dc143c">Variables</code> menu and click `Make a Variable`.

Name your new variable `restingPosition`.

--- /task ---

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, grab the <code style="background-color: #dc143c">restingPosition</code> block. 

Place it in the first `0` on the left of the <code style="background-color: #9400D3">0 - 0</code> block. 

--- /task ---

--- task ---

Change the `0` to `10` on the right of the <code style="background-color: #9400D3">-</code>.

--- /task ---

Your code should look like this:

<div style="position:relative;height:calc(250px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_i6zFuRE2K8ew" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

### Check for movement to the RIGHT from the resting position

--- task ---

From the <code style="background-color: #9400D3">Math</code> menu, grab a <code style="background-color: #9400D3">0 + 0</code> block.

Place it in the `10` of the <code style="background-color: #00A4A6">></code> comparison block.

--- /task ---

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, grab another <code style="background-color: #dc143c">restingPosition</code> block. 

Place it in the first `0` on the left of the <code style="background-color: #9400D3">0 + 0</code> block.

--- /task ---

--- task ---

Change the `0` to `10` on the right of the <code style="background-color: #9400D3">+</code>.

--- /task ---

Your code should look like this:

<div style="position:relative;height:calc(150px + 0em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_hmmgeHXfb5xH" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

### Setting a new resting position after each movement

Each time the micro:bit is rolled to a new resting position, you need to set the current position as the new resting position, so you can use it in our comparison.

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, grab the <code style="background-color: #dc143c">set</code> block. 

Place it under the <code style="background-color: #1E90FF">pause</code> block.

--- /task ---

--- task ---

Duplicate the <code style="background-color: #D400D4">rotation</code> block and place it in the `0` of the <code style="background-color: #DC143C">set</code> block.

--- /task ---

Your code should look like this:

<div style="position:relative;height:calc(170px + 1em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_VooFR6cseED5" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- task ---

When you make a change to a code block in the code editor panel, the simulator will restart.

**Test** your program:

+ Move from the centre of the micro:bit to the right or left. 

The LEDs will light up and stay on for a short time. 
***Keep your mouse still until the LEDs turn off.***

+ When the LEDs turn off, move from the new position (your resting position) to the right or left again. 

The LEDs will light up and stay on for **a short time**.

Repeat this process to see how the LEDs will turn on only when there is movement away from the resting position.

--- /task ---

### Letting the micro:bit come to rest

You should give the micro:bit some time to come to rest before setting the new <code style="background-color: #DC143C">restingPosition</code> to the variable.

--- task ---

Change the value in <code style="background-color: #1E90FF">pause</code> from `100` to `5 seconds`.

--- /task ---

<div style="position:relative;height:calc(170px + 3em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_Aqgc2mHrw529" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- task ---

**Test** your program:
+ Move from the centre of the micro:bit to the right or left. 

The LEDs will light up and stay on for **five seconds**. 
***Keep your mouse still until the LEDs turn off.***

+ When the LEDs turn off, move from the new position (your resting position) to the right or left again. 

The LEDs will light up and stay on for five seconds again.

--- /task ---

Next you are going to use the `A+B` button press event to **reset** your sleep tracker!