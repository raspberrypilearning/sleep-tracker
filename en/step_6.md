## Show some Zs

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

When the program starts, it is good to know that it is ready to start tracking.

In this step, you will display the zZs animation again when the program starts and use a function to organise your code.

</div>
</div>

### Re-use code

You can reuse the animation code.

--- task ---

Right-click on the `repeat`{:class='microbitlogic'} block and click **Duplicate**.

--- /task ---

There will now be two `repeat`{:class='microbitlogic'} blocks in the code editor panel. Each will contain three `show led`{:class='microbitbasic'} blocks.

--- task ---

Put the duplicated `repeat`{:class='microbitlogic'} block inside the `on start`{:class='microbitbasic'} block.

<img src="images/repeat-in-on-start.png" alt="The duplicated code inside the 'on start' block." width="350"/>

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

Click the **Functions** menu and then click **Make a Function**.

Name the function `zZ`.

![Animation showing how to make a function.](images/make-a-function.gif)

--- /task ---

--- task ---

From the `on button A+B`{:class='microbitinput'} block, drag the `repeat`{:class='microbitlogic'} block.

Place it inside your new `function zZ` block.

--- /task ---

--- task ---

Delete the code inside the `on start`{:class='microbitbasic'} block.

--- /task ---

When a `call zZ` block is executed, it runs the code in the `function zZ`.

--- task ---

From the Advanced > Functions menu, drag a `call zZ` block.

Place it inside the `on start`{:class='microbitbasic'} block.

--- /task ---

--- task ---

Drag out another `call zZ` block.

Place it inside the `on button A+B`{:class='microbitinput'} block, under the `set movements`{:class='microbitvariables'} block.

--- /task ---

Here are the blocks that have changed in this step:

```microbit
function zZ () {
    for (let index = 0; index < 2; index++) {
        basic.showLeds(`
            . . . . .
            . . . . .
            # # # . .
            . # . . .
            # # # . .
            `)
        basic.showLeds(`
            . . . . .
            # # # # .
            . . # . .
            . # . . .
            # # # # .
            `)
        basic.showLeds(`
            # # # # #
            . . . # .
            . . # . .
            . # . . .
            # # # # #
            `)
    }
}
input.onButtonPressed(Button.AB, function () {
    basic.clearScreen()
    basic.showString("Movements")
    basic.showNumber(movements)
    movements = 0
    zZ()
})
let movements = 0
zZ()
```

--- task ---

**Test your program** 

+ Check that your zZ animation plays when the simulator starts
+ Check that your zZ animation also plays when the `A+B` button is pressed (after the number of movements is displayed)

--- /task ---

Now you have a function, you can add to it and the code will run every time it is called! 

Next you will add a countdown timer to your function.