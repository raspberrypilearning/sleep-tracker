## Change brightness

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

When it is late at night, the LEDs on your micro:bit might be too bright.

In this step, you will use the A button and B button to change the brightness of the micro:bit's LED display.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">

To sleep better, try not to be around really <span style="color: #0faeb0">bright light</span> 2 hours before bedtime. If you can't sleep, make the lights less bright 2 hours before you want to sleep. And if you feel too sleepy in the mornings, go where the lights are bright to feel more awake.
</p>

</div>
<div>

![Animation showing that when the the A button is pressed, the LED display brightness decreases and when the B button is pressed, the LED display brightness increases.](images/brightness-change.gif)

</div>
</div>

Because the A button is on the left, you will use it to turn the brightness down.

### Brightness down

--- task ---

From the `Input`{:class='microbitinput'} menu, drag an `on button`{:class='microbitinput'} block.

Place it in the code editor panel.

<img src="images/on-button-location.png" alt="The Input menu with the 'on button' block highlighted." width="350"/>

--- /task ---

Each time the A button is pressed, you will halve the brightness.

--- task ---

From the `Led...more`{:class='microbitled'} menu, drag a `set brightness`{:class='microbitled'} block.

<img src="images/set-brightness-location.png" alt="The 'Led...more' menu with the 'set brightness' block highlighted." width="350"/>

--- /task ---

--- task ---

Place it inside the `on button`{:class='microbitinput'} block.

**Debug:** Check you have clicked on the Led **more** menu, not the normal Led menu.

--- /task ---

To halve the brightness, you will use a Math block.

--- task ---

From the `Math`{:class='microbitmath'} menu, drag a `0 / 0`{:class='microbitmath'} divide block.

Place it over the `255` value in the `set brightness`{:class='microbitled'} block.

--- /task ---

--- task ---

From the `Led...more`{:class='microbitled'} menu, drag a `brightness`{:class='microbitled'} block.

Place it over the first `0` value in the `0 / 0`{:class='microbitmath'} block.

--- /task ---

--- task ---

Change the second `0` to a `2`.

This will set the brightness to whatever value it currently is, divided by 2.

Your code should look like this:

<div style="position:relative;height:calc(125px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_R06gicKH4Kt2" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

### Brightness up

Now, you will set up the B button to turn the brightness up.

--- task ---

Right-click on the entire `on button A`{:class='microbitinput'} block and click **Duplicate**.

There will now be two `on button A`{:class='microbitinput'} blocks in the code editor panel.

--- /task ---

--- task ---

Click on the arrow next to `A`{:class='microbitinput'} on the duplicated block. 

Choose `B`{:class='microbitinput'}.

--- /task ---

--- task ---

Click on the arrow next to `/`{:class='microbitmath'} on the duplicated block. 

Choose `×`{:class='microbitmath'}.

--- /task ---

You will now have these blocks for the A button and the B button:

<div style="position:relative;height:calc(175px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_7VtHDq1F0884" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- task ---

When you make a change to a code block in the code editor panel, the simulator will restart.

**Test your program** 

+ Click the `A` button until the LEDs go out fully 

+ Click the `B` button and see what happens

If you have pressed the `A` button enough times, pressing the `B` button will not turn the LEDs back on.

This is because the brightness value has reached `0`.

When you multiply `0` by `2` you get... `0`. You can press the `B` button as many times as you want, but you will keep setting the brightness to `0 × 2`, which is **always** `0`!

--- /task ---

You need to stop the brightness value from being set to `0`.

To do this, you will use a Logic block to halve the brightness value only **if** the brightness level is **more than 10**.

--- task ---

From the `Logic`{:class='microbitlogic'} menu, drag an `if`{:class='microbitlogic'} block.

Place it around the `set brightness`{:class='microbitled'} block in the `on button A`{:class='microbitinput'} block.

--- /task ---

--- task ---

From the `Logic`{:class='microbitlogic'} menu, drag a `0 < 0`{:class='microbitlogic'} block

Place it over the `true`{:class='microbitlogic'} part.

--- /task ---

--- task ---

Change the `<`{:class='microbitlogic'} to a `>`{:class='microbitlogic'}.

--- /task ---

--- task ---

From the `Led...more`{:class='microbitled'} menu, drag a `brightness`{:class='microbitled'} block.

Place it inside the first `0` in the `0 > 0`{:class='microbitlogic'} block.

--- /task ---

--- task ---

Change the second `0` to `10`.

--- /task ---

Here is an animation showing the above steps:

<img src="images/if-around-set-brightness.gif" alt="Animation showing the 'if' block being taken from the Logic menu and held over the 'set brightness' block. It is released, making the 'set brightness' block snap inside it. A '0 > 0' block is then taken from the Logic menu and placed inside the first '0' of the '0 > 0' block. A 'brightness' block is then taken from the 'Led...more' menu and placed inside the first '0' of the '0 > 0' block. The second '0' is changed to '10'." width="350"/>

Your code should look like this:

<div style="position:relative;height:calc(175px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_8RWA44daDH1K" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

**Tip:** There is no need to do this for the `on button B` block as the maximum brightness value the LEDs can be set to is `255`.

--- task ---

**Test your program** 

+ Move over the edges of the micro:bit to record and display some movements

+ Press the `A+B` button

+ Press the `A` button a few times

The display should get less bright.

+ Press the `B` button a few times

The display should get brighter.

![Animation showing that when the the A button is pressed, the LED display brightness decreases and when the B button is pressed, the LED display brightness increases.](images/brightness-change.gif)

--- /task ---

Next, you are going to set the sleepy zZ animation to run when the program starts and organise your code using a function!
