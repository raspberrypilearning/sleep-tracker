## 1,2,3, sleep!

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

Counting is sometimes used as a way to get to sleep.

In this step, you will display a sequence of numbers before the zZs animation when the program starts.

</div>
</div>

You can create a timer that counts from 1 to 3 using a `for`{:class='microbitloops'} loop.

--- task ---

From the `Loops`{:class='microbitloops'} block menu, drag a `for index`{:class='microbitloops'} block.

Place it inside the `function zZ`{:class='microbitfunctions'} block, above the `repeat`{:class='microbitloops'} block.

Change the `4` to `2`.

--- /task ---

--- task ---

From the `Basic`{:class='microbitbasic'} block menu, drag a `show number`{:class='microbitbasic'} block.

Place it inside the `for index`{:class='microbitloops'} block.

--- /task ---

--- task ---

From the `Basic`{:class='microbitbasic'} block menu, drag a `pause`{:class='microbitbasic'} block.

Place it inside the `for index`{:class='microbitloops'} block, under the `show number`{:class='microbitbasic'} block.

Change the `100` to `1 second`.

--- /task ---

When you added the `for index`{:class='microbitloops'} block to your Workspace, the `index`{:class='microbitvariables'} variable was created.

The `index`{:class='microbitvariables'} variable takes on each value from `0` to `2` (the end number in our example) and counts up by one each time.

Rename the `index`{:class='microbitvariables'} variable `second` because your timer will increase each second.

--- task ---

Click the arrow to the right of the `index`{:class='microbitvariables'} variable and select `Rename variable`.

Replace the text `index` with `second` and click `Ok`.

--- /task ---

--- task ---

From the `Variables`{:class='microbitvariables'} blocks menu, drag a `second`{:class='microbitvariables'} variable.

Place it in the `0` of the `show number`{:class='microbitbasic'} block.

--- /task ---

--- task ---

**Test your program**

+ The LEDs will display `0` then `1` then `2` with a one second pause between each.

--- /task ---

It is more natural to see '1, 2, 3' than '0, 1, 2'.

We can do this with some simple maths.

--- task ---

From the `Math`{:class='microbitmath'} blocks menu, drag a `+`{:class='microbitmath'} block.

Place it in the `show number`{:class='microbitbasic'} block, replacing the `second`{:class='microbitvariables'} variable.

--- /task ---

The `second`{:class='microbitvariables'} variable will be pushed out, but you can still use it.

--- task ---

Drag the `second`{:class='microbitvariables'} variable to the first `0` in the `+`{:class='microbitmath'} block.

Change the second `0` to `1`.

--- /task ---

Here are the blocks that have changed in this step:

```microbit
function zZ () {
    for (let second = 0; second <= 2; second++) {
        basic.showNumber(second + 1)
        basic.pause(1000)
    }
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
```

--- task ---

**Test your program**

+ The LEDs will now display `1` then `2` then `3` with a one second pause between each.

--- /task ---

--- task ---

Download your program onto your micro:bit!

--- /task ---

[[[download-to-microbit]]]

Well done! You now have a fully working sleep tracker!

Next, it is time to check what you have learnt!
