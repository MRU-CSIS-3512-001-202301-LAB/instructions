# Tut-07

## Links You'll Need

| What              | Where                                                                              |
| ----------------- | ---------------------------------------------------------------------------------- |
| Tut-07 Screencast | None needed! This sucker's very straightforward!                                   |
| GH Classroom Asg  | [https://classroom.github.com/a/7jVH7GzO](https://classroom.github.com/a/7jVH7GzO) |

## Background

This is a super-super short lab; let's just get familiar with working in a front-end environment, and put Apache and company behind us...for the tutorials at least. ;)

I've decided to continues using Codespaces for the remaining tutorials, though it isn't technically necessary. You see, there are a few tools I'd like you to use - mainly eslint to catch common issues with JS code and Prettier to keep your code nice and purdy. And these tools require something called Node to be installed, and it's just easier to have all these pieces in place and set up correctly in a cloud environment.

## Things You'll Be Doing

The three short exercises below will have you dealing with skills you'll be using a LOT:

1. Adding external JavaScript files to a web page. 
   > _Unlike past years where the common way to do this was with a `<script>` tag without any `type` attribute, we're going to use `type="module"`, which will solve a number of problems that previous students had to struggle with. Aren't you lucky?!?_
2. Writing things to the browser console via `console.log()`.
3. Debugging with the lovely `debugger` statement.
4. Concatenating via `template literals` - this will be **very** similar to the variable interpolation we used in PHP.
5. Looping over an array in the preferred way: with a `for..of` loop.

---

## Exercise-01

If you look in the `ex-01` folder, you'll see two files: 
1. `index.html`
2. `index.js`

Use them to do the following: 

1. Make the `index.html` file uses `index.js` as an external script. Use `type="module"` in the `<script>` tag.
2. Have `index.js` print out the message `**ex-01 has been loaded**` to the console.

Check the browser's console and confirm the message is there!

---

## Exercise-02

1. This time, **you** create an `index.html` and `index.js` (in the `ex-02` folder).
2. Add a variable called `name` with a value of your name to `index.js`.
3. Log the message **`(your name) is Javascripting!`** to the console. Use the `name` variable and a template literal to do this.
4. Now toss a `debugger` statement before the code that logs to the console. Observe what happens - see if you can find **two different ways** to observe what value is in `name`.

---

## Exercise-03

If you look in the `ex-03` folder, you'll see two files: 
1. `index.html`
2. `index.js`

Use them to do the following:

1. Log the contents of the `airports` array to the conole. Observe how it looks when logged this way.
2. Now, log the elements of `airports` one at a time to the console using a `for..of` loop. Observe what logging things this way looks like.
   > _It's pretty easy to make mistakes here...you might use `in` or `as` instead of `of`. Or maybe you might put `airports` first, like it happens in PHP. Or you might forget to use `let` or `const`!_
3. Toss a `debugger` statement before your loop. Look at the different ways you can examine the array. 
4. One last thing: remove the `type="module"` from the `<script>` tag over in `index.html`. Then refresh the browser and let it hit the breakpoint again. Do you notice anything different about the scope of the array now?
    > _Park that little nugget of info in the dark recesses of your brain for the time being._

That's it for now!

---

## Don't forget to push!

If you remember to push your work back to GitHub, I'll have a look at it on Saturday/Sunday/Monday and provide some feedback. If you don't push in that time, no feedback will be provided - **BUT you can always come and talk to me in person after those days if you want me to look over your work!**
