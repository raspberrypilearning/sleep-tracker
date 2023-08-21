## Track and display

### Opening MakeCode

To get started creating your micro:bit project, you will need to open the MakeCode editor.

--- task ---

Open the MakeCode editor at [makecode.microbit.org](https://makecode.microbit.org){:target="_blank"}

--- collapse ---

---
title: Offline version of the editor
---

There is also a [downloadable version of the MakeCode editor](https://makecode.microbit.org/offline-app){:target="_blank"}.

--- /collapse ---

--- /task ---

Once the editor is open, you will need to create a New Project and give your project a name. 

--- task ---

Click on the **New Project** button.

![The new project button inside MakeCode](images/new-project-button.png)

--- /task ---

--- task ---

Give your new project the name `Sleep tracker` and click **Create**.

![The name 'Sleep tracker' written in the New Project dialogue box](images/sleep-tracker.png)

**Tip:** Give your project a helpful name that relates to the activity you’re creating. This will make it easier to find if you create other projects on MakeCode.

--- /task ---

[[[makecode-tour]]]

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step you will program the micro:bit to sense if it moves and make the LEDs light if it does.
</div>
<div>

![TODO: Replace animation]()
![Animation showing the LEDs turning on, as the micro:bit simulator is tilted left and right](images/tilt-test.gif)

</div>
</div>

The micro:bit uses a sensor called an accelerometer to sense when it has been rolled.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">

<span style="color: #0faeb0">Accelerometers</span> are used in many devices. They can tell if we're moving, like when we run or jump, and they help our tablets and smartphones know which way they're being held. These clever sensors make games more fun, letting you control how a character moves by tilting a controller. So next time you play a game, remember that accelerometers are making it super cool!

</p>

### Roll

We need to check **if** the micro:bit has been rolled right **or** left. 

If this happens, we will assume there has been movement during sleep.

--- task ---

From the <code style="background-color: #00A4A6">Logic</code> menu, drag out an <code style="background-color: #00A4A6">if</code> block and place it inside the <code style="background-color: #1E90FF">forever</code> block.

<img src="images/if-block-location.png" alt="The Logic menu, with the 'if .. then' block highlighted" width="350"/>

--- /task ---

--- task ---

Open the <code style="background-color: #00a4a6">Logic</code> menu again and take an <code style="background-color: #00a4a6">or</code> block. 

<img src="images/or-block-location.png" alt="The bottom part of the Logic menu, showing the location of the 'or' block in the 'Boolean' section" width="250"/>

Place it in the `true` section of the <code style="background-color: #00a4a6">if</code> block. 

![TODO: Replace embed]()
<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_WLaErMYLvHpo" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

Now you need to add the **two** conditions either side of the **or**. 

This will mean that the code inside your <code style="background-color: #00a4a6">if</code> block will run **either** condition is met.

--- task ---

From the <code style="background-color: #00A4A6">Logic</code> menu, drag out the <code style="background-color: #00a4a6">0 < 0</code> comparison block.

Place it on the left side of the <code style="background-color: #00a4a6">or</code> block.

![TODO: Replace embed]()
<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_XXXXXXXX" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

From the <code style="background-color: #D400D4">Input ... more</code> menu, drag out a <code style="background-color: #D400D4">rotation</code> block.

<img src="images/rotation-location.png" alt="The 'Input ... more' menu, with the 'rotation' block highlighted" width="350"/>

Place it inside the first `0` in the <code style="background-color: #00a4a6">0 < 0</code> comparison block.

Use the dropdown to change <code style="background-color: #D400D4">pitch</code> to <code style="background-color: #D400D4">roll</code>. 

Change the other `0` to `-10`.

![TODO: Replace embed]()
<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_XXXXXXXX" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

**Debug** Check you have:
+ Clicked on the Input **more** menu, not the normal Input menu.
+ Changed the second value from `0` to **`-10`**, not `10`.

--- task ---

Right click on the <code style="background-color: #00a4a6">0 < 0</code> comparison block and select Duplicate.

You will now have two comparison blocks.

Drag the duplicated comparison block on the right of the <code style="background-color: #00a4a6">or</code> block.

Use the dropdown to change the less than symbol (`<`) to a greater than (`>`) symbol. 

Change the `-10` to `10`.

![A demo of clicking the drop down and changing the < symbol to a > symbol in the condition.](images/duplicting-rotation-comparison.gif)

![TODO: Replace embed]()
<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_XXXXXXXX" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

When either condition is met, the micro:bit will have been rolled left or right.

We need to:
+ Light the LEDs
+ Record that there has been a movement

To keep a count of sleep movements, we will use a variable.

--- task ---

Open the <code style="background-color: #dc143c">Variables</code> menu and click `Make a Variable`.

<img src="images/variable-menu.png" alt="The Variables block menu, open with the 'Make a variable' button highlighted" width="350"/>

--- /task ---

--- task ---

Name your new variable `movements`. 

<img src="images/movements-variable-name.png" alt="The 'New variable name' window, with the name 'movements' written in the box" width="350"/>

--- /task ---

We will increase the movements variable by `1` each time a movement is detected.

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, grab the <code style="background-color: #dc143c">change movements</code> block. 

<img src="images/change-movements.png" alt="The Variables menu with the 'change movements by 1' block highlighted" width="350"/>

Place the block inside the <code style="background-color: #00A4A6">if</code> block.

![TODO: Replace embed]()
<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_XXXXXXXX" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---





--- task ---



--- /task ---








Use the dropdown to change the less than symbol (`<`) to a greater than (`>`) symbol. 

![A demo of clicking the drop down and changing the < symbol to a > symbol in the condition.](images/changing-condition.gif)

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_MtYUvfg1RT9a" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>








Place it inside the `true` space in the `if..true..then` block. 

Change the <code style="background-color: #00A4A6"><</code> to a <code style="background-color: #00A4A6">></code>

--- /task ---



We will use a 'rotation' block.

--- task ---

From the <code style="background-color: #D400D4">Input ... more</code> menu, drag out a <code style="background-color: #D400D4">rotation</code> block and place it inside the <code style="background-color: #D400D4">on button</code> block.

<img src="images/set-brightness-location.png" alt="The 'Input ... more' menu, with the 'set brightness' block highlighted" width="350"/>

**Debug** Check you have clicked on the Input **more** menu, not the normal Input menu.





From the <code style="background-color: #D400D4">Input</code> menu, drag out an <code style="background-color: #D400D4">on shake</code> block and place it on the code editor panel.

<img src="images/on-shake.png" alt="The 'Input' menu, with the 'on shake' block highlighted" width="350"/>

Click the arrow next to <code style="background-color: #D400D4">shake</code> and choose <code style="background-color: #D400D4">tilt left</code>.

<img src="images/tilt-left.png" alt="The 'on shake' block, with the menu expanded showing the 'tilt left' option highlighted" width="350"/>

--- /task ---

### Variables

To keep a count of sleep movements, we will use a variable.

--- task ---

Open the <code style="background-color: #dc143c">Variables</code> menu and click `Make a Variable`.

<img src="images/variable-menu.png" alt="The Variables block menu, open with the 'Make a variable' button highlighted" width="350"/>

--- /task ---

--- task ---

Name your new variable `movements`. 

<img src="images/movements-variable-name.png" alt="The 'New variable name' window, with the name 'movements' written in the box" width="350"/>

--- /task ---

We will increase the movements variable by `1` each time a movement is detected.

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, grab the <code style="background-color: #dc143c">change movements</code> block. 

<img src="images/change-movements.png" alt="The Variables menu with the 'change movements by 1' block highlighted" width="350"/>

Place the block inside the <code style="background-color: #D400D4">on tilt left</code> block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_2pRiwLdtbfCL" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

You can use the LEDs on the micro:bit to display how many sleep movements there have been.

--- task ---

From the <code style="background-color: #5C2D91">Led</code> menu drag a <code style="background-color: #5C2D91">plot bar graph of</code> block.

<img src="images/plot-bargraph.png" alt="The Led menu, open with the 'plot bar graph of' block highlighted" width="350"/>

Place it inside the <code style="background-color: #D400D4">on tilt left</code> block, under the <code style="background-color: #dc143c">change movements</code> block.

From the <code style="background-color: #dc143c">Variables</code> menu, grab the <code style="background-color: #dc143c">movements</code> block.

Place it inside the first `0` on the <code style="background-color: #5C2D91">plot bar graph of</code> block.

Change the second `0` to `10`. This value is the high value.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">

The LEDs will light all the way to the top when <code style="background-color: #dc143c">movements</code> reaches the <span style="color: #0faeb0">high value</span> of `10`. For each single increase up to 10, the LEDs will light up 1/10th of the way. If the high value was 15, then the LEDs will light up 1/15th of the way, etc.
</p>

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_22PFRwfcCJzU" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

Now you have programmed a movement to be recorded when the micro:bit senses a left tilt, you can do the same when it senses a right tilt.

--- task ---

Right-click on the entire <code style="background-color: #D400D4">on tilt left</code> block and click `Duplicate`.

There will now be two <code style="background-color: #D400D4">on tilt left</code> blocks on the code editor panel.

--- /task ---

--- task ---

Click on the arrow next to `tilt left` on the duplicated block. 

A drop down menu will open.

Choose <code style="background-color: #D400D4">tilt right</code>.

--- /task ---

When you make a change to a code block in the code editor panel, the simulator will restart.

**Test** When the program runs, move over the right and left of the micro:bit. 
The LEDs will light up in ten stages (because you set the high value to `10`).

![Animation showing the LEDs lighting up in stages, starting from the bottom row, as the micro:bit simulator is tilted left and right.](images/tilt-test.gif)

Next you are going to use the `A+B` button press event to reset your sleep tracker!