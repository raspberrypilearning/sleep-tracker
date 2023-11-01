## Push to reset

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
It's time to make your sleep tracker even better! 

When you press both the A and B buttons together, the micro:bit will show how much it moved and then start counting from zero again. 

You'll also make a special sleepy animation to show that your sleep tracker is all set and ready to help you sleep!

</div>
<div>

![Animation showing the LEDs lit up about half way. When the A+B button is pressed, the word 'Movements' scrolls across the display and the number 6 is shown. A short animation then loops twice, showing a small z growing into a large Z.](images/reset-test.gif)

</div>
</div>

The micro:bit has two buttons, the `A` button and the `B` button.

You can program something to happen when only `A` is pressed, only `B` is pressed, or when `A+B` are pressed together.

### Show the total movements

--- task ---

From the `Input`{:class='microbitinput'} menu, drag an `on button`{:class='microbitinput'} block.

Place it in the code editor panel.

<img src="images/on-button-location.png" alt="The Input menu with the 'on button' block highlighted." width="350" />

Use the drop-down menu to change the button to `A+B`{:class='microbitinput'}.

--- /task ---

Before the micro:bit displays the total number of recorded sleep movements, you will need to clear the screen.

--- task ---

From the `Basic`{:class='microbitbasic'} menu, drag a `clear screen`{:class='microbitbasic'} block and place it inside the `on button`{:class='microbitinput'} block.

The clear screen block turns off all the LEDs.

--- /task ---

Next, you will want to see the total number of sleep movements the micro:bit has recorded.

Before you display the number, it is a good idea to show what the number is.

--- task ---

From the `Basic`{:class='microbitbasic'} menu, drag a `show string`{:class='microbitbasic'} block.

Place it inside the `on button`{:class='microbitinput'} block, under the `clear screen`{:class='microbitbasic'} block.

Replace the word `Hello` with `Movements`.

--- /task ---

Now it is time to display the total number of sleep movements recorded.

--- task ---

From the `Basic`{:class='microbitbasic'} menu, drag a `show number`{:class='microbitbasic'} block.

Place it inside the `on button`{:class='microbitinput'} block, under the `show string`{:class='microbitbasic'} block.

--- /task ---

--- task ---

From the `Variables`{:class='microbitvariables'} menu, drag out the `movements`{:class='microbitvariables'} block.

Place it over the `0` in the `show number`{:class='microbitbasic'} block.

```microbit
input.onButtonPressed(Button.AB, function () {
    let movements = 0
    basic.clearScreen()
    basic.showString("Movements")
    basic.showNumber(movements)
})
```

--- /task ---

You now need to reset the movements variable back to 0, ready to track again.

--- task ---

From the `Variables`{:class='microbitvariables'} menu, drag a `set`{:class='microbitvariables'} block.

Place it under the `show number`{:class='microbitbasic'} block.

--- /task ---

--- task ---

Use the drop-down menu to select `movements`{:class='microbitvariables'} as the variable to set.

```microbit
let movements = 0
input.onButtonPressed(Button.AB, function () {
    basic.clearScreen()
    basic.showString("Movements")
    basic.showNumber(movements)
    movements = 0
})
```

--- /task ---

To show the sleep tracker is ready, you can show an animation. As this is a sleep tracker, you will create an animation of some Z's. 😴

--- task ---

From the `Basic`{:class='microbitbasic'} menu, drag **three** `show leds`{:class='microbitbasic'} blocks and place them under the `set movements`{:class='microbitvariables'} block.

Click the squares on each one to create these patterns:

```microbit
let movements = 0
input.onButtonPressed(Button.AB, function () {
    basic.clearScreen()
    basic.showString("Movements")
    basic.showNumber(movements)
    movements = 0
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
})
```

**Tip:** If you hold down the mouse, you can select multiple LEDs as you move.

--- /task ---

To create an animation, you can put the 'show leds' blocks in a loop.

--- task ---

From the `Loops`{:class='microbitloops'} menu, drag a `repeat`{:class='microbitloops'} block and place it around the three `show leds`{:class='microbitbasic'} blocks.

Change the number of repeats from `4` to `2`.

<img src="images/repeat-around-leds.gif" alt="Animation showing the 'repeat' block taken from the Loops menu. The 'repeat' block is then held over the top 'show leds' block and released, making the three 'show leds' blocks snap inside it. The number is then changed from a '4' to a '2'." width="350" />

--- /task ---

When you make a change to a code block in the code editor panel, the simulator will restart.

--- task ---

**Test** When the program runs, move over the left and right of the micro:bit to record some movements.

Next, press the `A+B` button.

The word 'Movements' will scroll across the display.

The number of movements will then be shown.

The zZ animation will then loop twice.

<img src="images/reset-test.gif" alt="Animation showing the LEDs lit up about half way. When the A+B button is pressed, the word 'Movements' scrolls across the display and the number 6 is shown. A short animation then loops twice, showing a small z growing into a large Z." width="350" />

--- /task ---

Next, you are going to use the `A` button and `B` button to change the display brightness!
