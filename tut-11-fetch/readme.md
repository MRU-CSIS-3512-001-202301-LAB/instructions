# Tut-11: Fetch, Rover

## Links You'll Need

| What              | Where        |
| ----------------- | ------------ |
| Tut-11 Screencast | Coming Later |
| GH Classroom Asg  | Coming Later |

## Things You'll Be Doing

This tutorial will give you some more practice using fetch (and the resulting funky Promises). We're going to be grabbing [Mars Curiosity rover](https://en.wikipedia.org/wiki/Curiosity_(rover)) images. That sucker landed up there in 2012...and is still operational, doodling around and checking stuff out. That's pretty neat.

_If you have purchased the labs, Exercise 10.8 might be somewhat helpful in completing this tutorial, though it is by no means necessary!_

---

## The Final Product

The goal of this tutorial is to make a little application that shows the photos available from Curiosity from a given camera (it has multiple ones) on a given date. 

Here's a quick (like 17 seconds quick) screencast showing the finished product in action. There's no sound. 

https://youtu.be/QdWXJy78vZY

_Note that when no pics are available, that fact is displayed to the user._


We'll break this up into chunks of manageable exercises. 


## Getting Your Bearings  

You should take a look at the `index.html` file. Notice how near the bottom there are a pair of divs (`#photos` and `#spinny`), that hold any photos pulled in from the API and the loading animation, respectively. They both start off with a CSS class of "hidden". You should take a quick look in `style.css` to see what that class does.

You should also examine those radio buttons. The `value` attributes they have will be useful to you later....

--- 

## ex-00: grab an API key

You're going to need an API key for this. Fortunately, NASA is plain awesome and the process is free and gobsmackingly simple.

1. Go to https://api.nasa.gov.
2. Generate a key.
3. Write it down somewhere.
4. Say to yourself, "That's it?!?".

---

## ex-01: create an Endpoint constructor function

### prerequisites

To complete this exercise, you should know how to:

- [ ] create a constructor function that creates objects with methods
- [ ] read a simple API doc

### goal

We're going to be querying the Mars Rover Photos API from https://api.nasa.gov. In order to ask the API for photos from the Curiosity rover on a certain date from a certain camera, we need a very specific endpoint format. 

Our goal is to create an Endpoint constructor function that allows us to create Endpoint objects that are tied to our API key (from ex-00) and that we can ask for endpoints from certain dates/cameras.

If your constructor function is working properly, you should be able to do something like this in the console:

```js
const endpoint = new Endpoint();
endpoint.for({date: '2022-01-23', camera: 'rhaz'})
// returns the URL that would provide photos from the Curiosity rover
// for 2022-01-23 from the Rear Hazard Avoidance Camera
```


### what you'll need to do

1. Look at the docs for the Mars Rover Photos API. In particular, see if you can figure out what an endpoint that needs to pull information for the Curiosity rover on a particular Earth date from a particular camera would look like.

2. Create a function called `Endpoint` in a new file called `endpoint.js`.

    _Notice the capital 'E' in the function name - we wanna build our convention-following muscles here._

3. Store off our API key in our constructor function. A constant seems reasonable for this.

4. Create a method in our constructor function called `for` that takes in an object with the properties hinted at in the example shown in our goal and returns a valid endpoint URL.

    _This is a useful technique that you might want to try out some time._

5. Bring the `endpoint.js` file into `index.html`.

6. Test out your function by calling it in the console with different dates and cameras. You should get URLs that you can open up in a browser to observe the resulting JSON. Here's what I see when I go to the URL generated in the example code shown in the goal:

    ![endpoint](images/ex01-endpoint.png) 

---

## ex-02: create functions to show and hide the loading animation

### prerequisites

To complete this exercise, you should know how to:

- [ ] add and remove CSS classes from a DOM element

### goal

Our goal is to create two functions:

1. `showLoadingAnimation`, which hides `#photos` and unhides `#spinny`.
2. `hideLoadingAnimation`, which hides `#spinny` and unhides `#photos`.

These functions should add/remove the necessary CSS class to reach the goal. Do not use inline styling.

When your goal is complete, you should be able to head to the console and see your functions work.

Here's what I see when I use my functions:

https://youtu.be/ZChlI-rL9qc


### what you'll need to do in `index.js` 

1. Create `showLoadingAnimation` and `hideLoadingAnimation` so they work as expected.

---

## ex-03: create a function to find the currently selected camera

### prerequisites

To complete this exercise, you should know how to:

- select all DOM elements matching a given CSS selector
- find the value from a radio button
- ask a radio button DOM element whether it is checked or not

### goal

When we click on the `Display Photos` button, one of the important pieces of information we need is the name of the camera currently selected. This information is stored in the value of the currently checked radio button - but how do we get it?

Our goal here is to make a function called `selectedCamera` that returns the value of the currently selected camera radio button.

If your function is working properly, you should be able to do something like this in the console:

```js
// assume the Front Hazard Avoidance radio button is checked
selectedCamera(); // returns `fhaz`

// assume we now click on the Navigation radio button
selectedCamera(); // now returns `navcam`
```

### what you'll need to do in `index.js` 

1. Create `selectedCamera` so it works as expected.

#### Hints

- There are quite a few ways to do this. Three suggestions:
  1. Select all the radio buttons, loop through them until you find the one that's been checked, and return that checked one's value.
  2. Start off selecting all radio buttons the same as (1), but then turn the NodeList into an Array with the `Array.from` method, and then use `find` to find the checked one (and return its value).
  3. The easiest way? Use the proper CSS selector to grab the checked one and return its value.

---

## ex-04: put the pieces together!

### prerequisites

To complete this exercise, you should know how to:

- register an event handler 
- use fetch to get JSON from an API endpoint
- use a Promise chain to use fetched data

### goal

Our goal is to get the app behaving as shown in [The Final Product](#the-final-product) section above. 

### what you'll need to do in `index.js` 

1. Create an event handler for the button being clicked. You might want to make a function declaration for the handler, though you don't have to.

2. Flesh out the handler. What does it need to do? The helpers you made in ex 01 thru 03 are definitely going to come in handy here! Don't forget to handle the situation where there are no images on a given day and/or for a given camera.

#### Hints

- Since you're using `fetch`, you'll need an endpoint for the currently selected date and camera. How will you create that endpoint? How will you get the currently selected date? Currently selected camera?
- When you do a `resp.json()` on the fetch results, what does the resulting object look like? Which property from that object do you need?
- You'll need to turn the photo objects from the API into `<img>` DOM elements. You've done this kind of thing before....
- How are you going to handle the loading animation show/hide? You've got helpers to do this...but when are you going to call them?

---

## Don't forget to push!

If you remember to push your work back to GitHub, I'll have a look at it on Saturday/Sunday/Monday and provide some feedback. If you don't push in that time, no feedback will be provided - **BUT you can always come and talk to me in person after those days if you want me to look over your work!**