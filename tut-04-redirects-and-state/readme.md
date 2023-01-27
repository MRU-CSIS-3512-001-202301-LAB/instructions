# Tut-04

## Links You'll Need

| What              | Where                                   |
| ----------------- | --------------------------------------- |
| Tut-04 Screencast | https://youtu.be/8sMt_gR0myU            |
| GH Classroom Asg  | https://classroom.github.com/a/5r8HgPY_ |

## Background

Let's imagine you're starting work on the prototype of a site where a user can log in and look at flight information for a variety of airlines.

You want to make sure the flight info is only accessible to people logged in.

Also, as a subtle feature, you want the site to remember the last airline company the uer looked at; if they come back to the page within a month and log in, that airline's flights will be selected automatically for them. Fancy!

### TailwindCSS

If you look at the view files, you'll see...what may seem to be a mess. A mess like this:

```html
<div class="bg-gray-100 rounded-b-lg py-12 px-4 lg:px-24">
```

That funky stuff in the class attribute is a series of CSS commands used by TailwindCSS, which I mentioned at the [start of the course](https://github.com/MRU-CSIS-3512-001-202301-LEC/course-materials/blob/main/resource-list.md#tailwind-css). 

You can safely ignore all of it for this tutorial - our goal isn't dealing with a cool way of doing CSS. 


## Things You'll Be Doing

This tutorial will help you practice redirecting to pages based on session state, as you'll need to do for The Project.

You'll also practice using cookies to "hold" information so that when the user returns to the site - even if they close the browser - that information is still there. This, too, is used in The Project.

---

## Ex 1: Get a Login Form to Redirect on Valid Login and Re-Display Otherwise

Here are the files where you'll need to do some work:

### `login.php`

This is the controller for logging in. 

Here's what needs to be done:

- [ ] If the user lands on this page from a GET, then they should see the login form. 
- [ ] If they're coming in from a POST, then:
    - [ ] If the user has entered `admin` for both the username (yes, I know the icon in the form is an email icon!) and password, then you should store something in PHP's session state to indicate a successful login has happened and redirect to `flights.php`.
    - [ ] If the user has entered in any other username/password combination, redisplay the form with just the username filled in. (You don't have to worry about adding validation messages...though you might want the practice if you're still a bit fuzzy on how to do that!)
    > _Why do you suppose we're not filling in the password, too?..._
    
### `views/login.view.php`

This is the login form's view. You'll need to:

- [ ] Get the head and footer placed in the right spots, and
- [ ] Get the username to persist if the form re-displays, as mentioned in the `login.php` tasks.

---

## Ex 2: Get a Page to Punt You to a Login Form if You're Not Logged In

If a user tries to go to the `flights.php` without first logging in, we want to shunt them back to the login form.

To make this happen, here's what you'll need to do:

### `flights.php`

- [ ] Check to see if the thing you stored in session state on a successful login is there; if not redirect the user to `login.php`.

### `views/flights.view.php`

You don't actually need to do anything here...but I'd take a look around in here and try to get a feel for what's going on. For example:

- Do you see how each airline is actually a link - what's up with those funky `href` entries?
- What on earth is going on with `button_class_for`?
- See the text being printed out in the `<div>` after the airline `<div>`? That's going to need to be dynamically generated soon.

---

## Ex 3: React to User Selections & Use Cookies to Store a Filter Preference

When the user clicks on an airline button, that button should highlight and the name of the airline should appear in the text area underneath the buttons.

Also, if the user closes the browser (or browser tab) and then logs back in to the "site", the airline they last selected should now be pre-selected!

Here's what you'll need to do, and where:

### `views/flights.view.php`

- [ ] Add some PHP to allow the name of an airport to be written in the `<div>` under the airline buttons.
- [x] I _was_ going to get you to call the `button_class_for()` function with the correct args, but then I thought, "Nope - this is big enough." **But** your buttons _won't_ select unless you set `$active_airline` properly as described below!

### `flights.php`

- [ ] If the query string has one of the known airlines (what are they?), set `$active_airline` correctly, make sure the name of that airline appears below the airline buttons...and store off a cookie that lasts for 30 days that holds the proper key/value pair.
- [ ] If there is no query string, but there IS a cookie holding an airline, then do the same thing you did in the previous step: set `$active_airline` correctly, and make sure the name of that airline appears below the airline buttons.
- [ ] If none of the above is true, then make things behave as if the Air Canada button was selected.


---

## Don't forget to push!

If you remember to push your work back to GitHub, I'll have a look at it on Friday/Saturday/Sunday and provide some feedback. If you don't push in that time, no feedback will be provided!
