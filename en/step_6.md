## Show some Zs

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

When the program starts, it is good to know that it is ready to start tracking.

In this step, you will display the zZs animation again when the program starts and use a function to organise your code.

</div>
</div>

### Re-using code

You can reuse the animation code.

--- task ---

Right-click on the <code style="background-color: #00AA00">repeat</code> block and click `Duplicate`.

--- /task ---

There will now be two <code style="background-color: #00AA00">repeat</code> blocks on the code editor panel. Each will contain three <code style="background-color: #1E90FF">show led</code> blocks

--- task ---

Put the duplicated <code style="background-color: #00AA00">repeat</code> block inside the <code style="background-color: #1E90FF">on start</code> block.

<img src="images/repeat-in-on-start.png" alt="The duplicated code insde the 'on start' block" width="350"/>

--- /task ---

### Tidy with a function

The animation is a large group of code blocks. 

Repeating a large group of blocks makes our code untidy.

If you need to re-use code, it is sometimes better to put it in a function and then 'call' the function to run. 

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">

A <span style="color: #0faeb0">function</span> is a group of blocks that you can create and name. You can run those blocks by 'calling' the name of the function. Another word for a function is a <span style="color: #0faeb0">subprogram</span>, because it can be called to run from the main program.
</p>

--- task ---

Click the `Advanced` menu to reveal the Functions menu.

Click the Functions menu and then click `Make a Function`.

Name the function `zZ`.

![Animation showing how to make a function.](images/make-a-function.gif)

--- /task ---

--- task ---

From the <code style="background-color: #D400D4">on button A+B</code> block, drag out the <code style="background-color: #00AA00">repeat</code> block.

Place it inside your new `function zZ` block.

--- /task ---

--- task ---

Delete the code inside the <code style="background-color: #1E90FF">on start</code> block.

--- /task ---

When a `call zZ` block is executed, it runs the code in the `function zZ`.

--- task ---

From the Advanced > Functions menu, drag out a `call zZ` block.

Place it inside the <code style="background-color: #1E90FF"> on start</code> block.

--- /task ---

--- task ---

Drag out another `call zZ` block.

Place it inside the <code style="background-color: #D400D4">on button A+B</code> block, under the <code style="background-color: #DC143C">set movements</code> block.

--- /task ---

Here are the blocks that have changed in this step:

<div style="position:relative;height:calc(800px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_Exxaiz8UhErD" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- task ---

**Test** your program: 

+ Check that your zZ animation plays when the simulator starts
+ Check that your zZ animation also plays when the `A+B` button is pressed (after the number of movements is displayed)

--- /task ---

--- task ---

[[[download-to-microbit]]]

--- /task ---
