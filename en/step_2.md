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

From the <code style="background-color: #00A4A6">Logic</code> menu, drag an <code style="background-color: #00A4A6">if</code> block and place it inside the <code style="background-color: #1E90FF">forever</code> block.

<img src="images/if-block-location.png" alt="The Logic menu with the 'if...then' block highlighted." width="350"/>

--- /task ---

--- task ---

Open the <code style="background-color: #00a4a6">Logic</code> menu again and take an <code style="background-color: #00a4a6">or</code> block. 

<img src="images/or-block-location.png" alt="The bottom part of the Logic menu, showing the location of the 'or' block in the 'Boolean' section." width="150"/>

Place it in the `true` section of the <code style="background-color: #00a4a6">if</code> block. 

<div style="position:relative;height:calc(175px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_d6KcohD3RCjK" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

Now you need to add the **two** conditions either side of the **or**. 

This will mean that the code inside your <code style="background-color: #00a4a6">if</code> block will run if **either** condition is met.

--- task ---

From the <code style="background-color: #00A4A6">Logic</code> menu, drag the <code style="background-color: #00a4a6">0 < 0</code> comparison block.

Place it on the left side of the <code style="background-color: #00a4a6">or</code> block.

<div style="position:relative;height:calc(150px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_6zUfDw2k274E" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

From the <code style="background-color: #D400D4">Input...more</code> menu, drag a <code style="background-color: #D400D4">rotation</code> block.

<img src="images/rotation-location.png" alt="The 'Input...more' menu with the 'rotation' block highlighted." width="350"/>

Place it inside the first `0` in the <code style="background-color: #00a4a6">0 < 0</code> comparison block.

--- /task ---

--- task ---

Use the drop-down menu to change <code style="background-color: #D400D4">pitch</code> to <code style="background-color: #D400D4">roll</code>. 

--- /task ---

--- task ---

Change the `0` to `-10`. This will check if the micro:bit is rolled 10° to the **left**.

--- /task ---

Your code should look like this:

<div style="position:relative;height:calc(100px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_XefbaDJ4uTvi" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- task ---

**Debug** 

Check you have:

+ Clicked on the Input **more** menu, not the normal Input menu
+ Changed the second value from `0` to **`-10`**, not `10`

--- /task ---

--- task ---

Right click on the <code style="background-color: #00a4a6"> < </code> comparison block and select **Duplicate**.

--- /task ---

You will now have two comparison blocks.

--- task ---

Drag the duplicated comparison block to the right of the <code style="background-color: #00a4a6">or</code> block.

--- /task ---

--- task ---

Use the drop-down menu to change the less than symbol (<code style="background-color: #00a4a6"> < </code>) to a greater than symbol (<code style="background-color: #00a4a6"> > </code>). 

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

Open the <code style="background-color: #dc143c">Variables</code> menu and click **Make a Variable**.

<img src="images/variable-menu.png" alt="The Variables block menu with the 'Make a variable' button highlighted." width="350"/>

--- /task ---

--- task ---

Name your new variable `movements`. 

<img src="images/movements-variable-name.png" alt="The 'New variable name' window, with the name 'movements' written in the box." width="400"/>

--- /task ---

You will increase the `movements` variable by `1` each time a movement is detected.

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, get the <code style="background-color: #dc143c">change movements</code> block. 

<img src="images/change-movements.png" alt="The Variables menu with the 'change movements by 1' block highlighted." width="350"/>

--- /task ---

--- task ---

Place it inside the <code style="background-color: #00A4A6">if</code> block.

<div style="position:relative;height:calc(100px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_iT2FmD3d7TE2" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

### Light the LEDS

You can use the LEDs on the micro:bit to show that there has been a movement. 

This will help you test your project.

--- task ---

From the <code style="background-color: #1E90FF">Basic</code> menu, drag a <code style="background-color: #1E90FF">show icon</code> block.

<img src="images/show-icon-location.png" alt="The Basic menu with the 'show icon' block highlighted." width="350"/>

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

Your code should look like this:

<div style="position:relative;height:calc(250px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_UL1DcWbiR5Ey" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

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
