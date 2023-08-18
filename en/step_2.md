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

In this project, you will make use of the 'on start' block but not the 'forever' block. 

--- task ---

You can delete the 'forever' block now by dragging it to the menu panel.

![Animation showing the forever block being deleted](images/delete-forever.gif)

--- /task ---

The micro:bit uses a sensor called an accelerometer to sense when it has been tilted.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">

<span style="color: #0faeb0">Accelerometers</span> are used in many devices. They can tell if we're moving, like when we run or jump, and they help our tablets and smartphones know which way they're being held. These clever sensors make games more fun, letting you control how a character moves by tilting a controller. So next time you play a game, remember that accelerometers are making it super cool!

</p>

### Gestures

If the accelerometer on the micro:bit has sensed a tilt right or left, we will assume there has been movement during sleep.

We will use 'gesture' blocks for this.

--- task ---

From the <code style="background-color: #D400D4">Input</code> menu, drag out an <code style="background-color: #D400D4">on shake</code> block and place it on the code editor panel.

<img src="images/on-shake.png" alt="The 'Input' menu, with the 'on shake' block highlighted" width="300"/>

Click the arrow next to <code style="background-color: #D400D4">shake</code> and choose <code style="background-color: #D400D4">tilt left</code>.

<img src="images/tilt-left.png" alt="The 'on shake' block, with the menu expanded showing the 'tilt left' option highlighted" width="300"/>

--- /task ---

### Variables

To keep a count of sleep movements, we will use a variable.

--- task ---

Open the <code style="background-color: #dc143c">Variables</code> menu and click `Make a Variable`.

<img src="images/variable-menu.png" alt="The Variables block menu, open with the 'Make a variable' button highlighted" width="300"/>

--- /task ---

--- task ---

Name your new variable `movements`. 

<img src="images/movements-variable-name.png" alt="The 'New variable name' window, with the name 'movements' written in the box" width="300"/>

--- /task ---

We will increase the movements variable by `1` each time a movement is detected.

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, grab the <code style="background-color: #dc143c">change movements</code> block. 

<img src="images/change-movements.png" alt="The Variables menu with the 'change movements by 1' block highlighted" width="300"/>

Place the block inside the <code style="background-color: #D400D4">on tilt left</code> block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_2pRiwLdtbfCL" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

You can use the LEDs on the micro:bit to display how many movements there have been.

--- task ---

From the <code style="background-color: #5C2D91">Led</code> menu drag a <code style="background-color: #5C2D91">plot bar graph of</code> block.

<img src="images/plot-bargraph.png" alt="The Led menu, open with the 'plot bar graph of' block highlighted" width="300"/>

Place it inside the <code style="background-color: #D400D4">on tilt left</code> block, under the <code style="background-color: #dc143c">change movements</code> block.

From the <code style="background-color: #dc143c">Variables</code> menu, grab the <code style="background-color: #dc143c">movements</code> block.

Place it inside the first `0` on the <code style="background-color: #5C2D91">plot bar graph of</code> block.

Change the second `0` to `10` on the <code style="background-color: #5C2D91">plot bar graph of</code> block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_22PFRwfcCJzU" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---