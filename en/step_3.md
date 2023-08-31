### Dealing with different resting head positions

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

At the moment, the micro:bit is recording a movement whenever the micro:bit is **not** level.

For this project, the micro:bit will be placed under a pillow (it would be uncomfortable to wear it on your head!)

When you lie down, the weight of your head on your pillow will probably roll the micro:bit so that it is not completely level.

This will be the **resting position**. 

You need to record a movement only if the micro:bit is rolled away from the resting position. 

</div>
</div>

### Check for movement to the LEFT from the resting position

You need to know if there is a difference between the resting position and the current roll position.

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

<div style="position:relative;height:calc(150px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_hmmgeHXfb5xH" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

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

<div style="position:relative;height:calc(170px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_VooFR6cseED5" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

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

<div style="position:relative;height:calc(170px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_Aqgc2mHrw529" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- task ---

**Test** your program:
+ Move from the centre of the micro:bit to the right or left. 

The LEDs will light up and stay on for **five seconds**. 
***Keep your mouse still until the LEDs turn off.***

+ When the LEDs turn off, move from the new position (your resting position) to the right or left again. 

The LEDs will light up and stay on for five seconds again.

--- /task ---

Next you are going to use the `A+B` button press event to **reset** your sleep tracker!