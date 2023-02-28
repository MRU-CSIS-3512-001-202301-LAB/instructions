# Tut-10

## Links You'll Need

| What              | Where        |
| ----------------- | ------------ |
| Tut-10 Screencast | Coming Later |
| GH Classroom Asg  | Coming Later |

## Things You'll Be Doing

This tutorial is meant to get you used to working with event handlers. Some of the handling will involve event delegation, 'cause you need to know how to do that! (In the assignment, for example.) 


---

## The Final Product

The goal of this tutorial is to make a little application that does the following:

- loads images from the [Lorem Picsum site](https://picsum.photos/) (very cool site btw) when a button is pressed
- removes images when they are clicked
- removes all images when the `a` key is pressed on the keyboard
- causes all images to fade (decrease opacity by 80%) when the `f` key is pressed

Here's a quick (like 22 seconds quick) screencast showing the finished product in action. There's no sound.

https://youtu.be/chRYQRRGBaU


We'll break this up into chunks of manageable exercises. 

You have to do these in order, so don't try and skip ahead, 'cause public displays of weeping make me uncomfortable.

--- 

## ex-01: turn JSON into an array of JS objects

### prerequisites

To complete this exercise, you should know how to:

- [ ] convert JSON that's in a file into JS objects
- [ ] link external JS to an HTML file
- [ ] ensure the DOM is loaded before attempting to run JS that uses the DOM

### goal

The file `data/pics.js` contains JSON for an array of objects holding information about the images that need to be created when the Load button is clicked.

_Take a quick look at the file contents - it's always a good idea to get a feel for data you're dealing with._

Our goal is to turn the contents of this file into an array of JS objects, store that array in a const/variable, and log it to the console.

Here's what I see in my console when I do that:

![console results](images/ex01-console-output.png)

_Note: I expanded the array in the console and then took the screenshot._

### what you'll need to do in `ex-01/index.js` and `ex-01/index.html`

1. Create a well-named variable that holds the JS objects represented by the contents of `data/pics.js`.

_Don't forget to make any necessary changes in `index.html`! You can decide where to put necessary `<script>` tags and whether you want to practice using `DOMContentLoaded` or not._

---

## ex-02: turn JS objects into `<img>` DOM elements

### prerequisites

To complete this exercise, you should know how to:

- [ ] create and use a function that returns image DOM elements
- [ ] turn an array of objects into an array of different, but related, objects
- [ ] iterate through arrays

### goal

We want to turn the array of JS objects you created in ex-01 into an array of `<img>` DOM elements. Since we have multiple objects to convert, it makes sense to create a function that converts a _single_ JS object into a _single_ `<img>` element, so we'll do that. 

We'll use our function to convert one array (of JS objects) into another array (of `<img>` elements) and log those elements to the console.

Here's what logging these elements looks like:

![console results](images/ex02-console-output.png)

_Since we're copying our work from ex-01 over, we see our array from ex-01 being displayed here as well._

_**WARNING**: those things in the screenshot are NOT Strings! They are `<img>` elements!_

### what you'll need to do in `ex-02/index.js`

1. Copy your code from `ex-01` into `ex-02`. Don't forget your markup.

    _You'll be doing this - copying your working code from a previous exercise into the one you're currently working on - for the remaining exercises as well._

2. Create a well-named function that takes in a single image object (the ones from the JSON file) and returns an `<img>` DOM element that has these properties:
   1. the `src` property should be the URL `https://picsum.photos/id/(id)/(dim)`. `(id)` and `(dim)` come from the image object. For example, the first object would help you build this `src`: `https://picsum.photos/id/1025/200`
   2. the `alt` property should be the `alt` property from the image object. For example, the first object would help you build this `alt`: "A none-too-impressed dog."

3. Turn the array of JS objects into an array of `<img>` DOM elements. What JS array method was **made** for that task?

4. Loop through the results from 3 and output each DOM element to the console.

---

## ex-03: add `<img>` elements to the DOM when the Load button is clicked

### prerequisites

To complete this exercise, you should know how to:

- [ ] select a DOM element
- [ ] create an event handler
- [ ] register an event handler
- [ ] add elements to the DOM

### goal

When the Load button is clicked, the image elements from `ex-02` should appear in the browser. (See the screencast mentioned in [The Final Product](#the-final-product) for a demo.)

### what you'll need to do in `ex-03/index.js`

1. Copy your code from `ex-02` into `ex-03`. 

2. Add code that appends COPIES of the elements you created in `ex-02` to `div#pics` (look at the markup) when the Load button is clicked.

    _If you don't make COPIES of the elements you're appending to the div, you'll only ever see 4 images! If you look at the docs for `appendChild`, you can figure out why this is true. To avoid this, you'll need to use the `cloneNode` method. For example, if you have a DOM element called `elem` that you want to append to a DOM element called `theDiv`, you should go `theDiv.appendChild(elem.cloneNode())`._

---

## ex-04: use event delegation to remove images from the DOM when they are clicked

### prerequisites

To complete this exercise, you should know how to:

- [ ] select a DOM element
- [ ] create an event handler
- [ ] register an event handler
- [ ] remove elements from the DOM
- [ ] handle events using event delegation

### goal

When an image is clicked, it should be removed from the DOM. (See the screencast mentioned in [The Final Product](#the-final-product) for a demo.)

### what you'll need to do in `ex-04/index.js`

1. Copy your code from `ex-03` into `ex-04`. 

2. Add code that removes clicked images from the DOM. You must use event delegation for this.

_Hint: who is the parent that needs to do all the work?_

---

## ex-05: make the app react to the `a` key being pressed

### prerequisites

To complete this exercise, you should know how to:

- [ ] select a DOM element
- [ ] create an event handler
- [ ] register an event handler
- [ ] react to keyboard input (look into the `keydown` event)

### goal

When the `a` key is pressed, all images in the DOM should be removed. (See the screencast mentioned in [The Final Product](#the-final-product) for a demo.)

### what you'll need to do in `ex-05/index.js`

1. Copy your code from `ex-04` into `ex-05`. 

2. Add code to remove all images when the `a` key is pressed.

_Have the `document` listen for the `keydown` event to do this._

---

## ex-06: make the app react to the `f` key being pressed

### prerequisites

To complete this exercise, you should know how to:

- [ ] select multiple DOM elements
- [ ] create an event handler
- [ ] register an event handler
- [ ] react to keyboard input
- [ ] access and also change the opacity of a DOM element

### goal

When the `f` key is pressed, all images currently in the DOM should fade by 80%. Think carefully about what this means!

> _**Hint:** What is the starting opacity of these images? When we reduce something by a certain %, what does that mean? For example, imagine somebody says to you "Here's $100. Every time I say 'poof!', I want you to destroy 50% of the money you have." After you hear 'poof!' 3 times, how much money would you have left?..._

(See the screencast mentioned in [The Final Product](#the-final-product) for a demo.)

### what you'll need to do in `ex-06/index.js`

1. Copy your code from `ex-05` into `ex-06`. 

2. Add to your `keydown` handler code to now also reduce the opacity of all image elements by 80% when the `f` key is pressed.


---

## Don't forget to push!

If you remember to push your work back to GitHub, I'll have a look at it on Saturday/Sunday/Monday and provide some feedback. If you don't push in that time, no feedback will be provided - **BUT you can always come and talk to me in person after those days if you want me to look over your work!**
