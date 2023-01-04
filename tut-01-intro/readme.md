# Tut-01

## Questions To Answer

1. _Who are these people around you?!?_
2. _Why  should I bother coming to tuts if they're not worth marks?_
3. _Where are the instructions for tutorials?_
4. _How do get the starting files for tutorials (and for The Project)?_
5. _What are Codespaces, and why are we using them?_
6. _How do I start up a Codespace so I can get coding?_
7. _How can I cut down on the time needed to bang out markup?_
8. _How do I look at my work in a browser?_
9. _How do I keep my code all formatted nicely so it is easier to understand?_
10. _What happens if I don't push my work in Codespaces?_

## Background

Every tutorial will see us doing the same sort of things:

1. Grabbing a GitHub Classroom Assignment.
2. Maybe spinning up a Codespace (esp. at the start of the course, where we're dealing with PHP).
3. Doing some educational things.
4. Pushing your finished (or partially) finished work up to GitHub, so you can access it later and/or have JP provide you some feedbak.

We're going to try to do this process **twice** today, so that you start to feel comfortable with it.

## Do These Things

### Prerequisites

Before you get started, please make sure whatever VS Code installation you are using (personal laptop or lab machine) has the following extensions installed:
- [ ] GitHub Codespaces
- [ ] Dev Containers
- [ ] Markdown All in One
- [ ] Markdown Preview Github Styling
- [ ] PHP Debug
- [ ] PHP Intelephense

_If you plan on working on lab machines a lot, you should look into the [Settings Sync](https://code.visualstudio.com/docs/editor/settings-sync) feature in VS Code. It's very nice._

### Tut-01a

_Things might behave a bit differently for you than what you see here. If they do, don't panic. If you're in the lab while doing this, just flag JP down. If you're not, then just do your best - you're not going to break anything permanently if you poke around a bit!_

1. Accept this GitHub Classroom Assignment: https://classroom.github.com/a/T4pK7w8b

2. Time to spin up your Codespace! Take a look here:

    ![start Codespace](images/codespace-startup.png)

3. Wait a while. Magic takes time, yes?

4. You'll eventually be sitting in a browser tab that looks an **awful** lot like VS Code:

    ![you've arrived](images/home-sweet-home.png)
    
    _You're actually remoting into a virtual machine running somewhere out there in cloud land. Via your browser. Crazy world we live in, yes?_

5. As cool as using your browser as your IDE is, there are some limitations that we bump into that will be show-stoppers for our PHP development, so we want to open up this Codespace in VS Code. Let's do that.

    1. Go to VS Code's Command Palette (`Ctrl + Shift + P`) and search for `Codespaces: Open in VS Code Desktop`.
 
        _**Tip:** getting comfortable with keyboard shortcuts on any tool you frequently use is time well spent and a sign of competence!_
    
        You should see something like this:
    
        ![warning message](images/open-in-vs-code.png)
    
    2. Choose `Open Visual Studio Code`. If you get a dialog asking you whether it's ok to allow GitHub Codespaces to open a URL, say heck yeah and tell it not to bother you again either.
    
        You might also have VS Code open yet another VS Code window...just roll with it.

    3. If/when you get a warning that looks like the following, you can choose `Ignore Pull Request`: 
    
    ![warning message](images/warning.png) 
    

#### Take stock for a second

_So we're jacked in to a remote machine, your own custom-made development machine. Pretty neat!_ 

_If you open up the Command Palette (remember `Ctrl + Shift + P`) and search for `Codespaces: Details`, you can see the details of your box:_

  ![details](images/details.png)
  
_Let's finish off by modifying the README.md, pushing our work, and spinning our Codespace down._

6. Open up the `README.md` file and writing one sentence about how all this is making you feel right now. Excited? Confused? Dead inside? You tell me!

7. Add, commit, and push your work.

8. Use the Command Palette to `Codespaces: Stop Current Codespace`. You can shut down VS Code - though you're going to need it again shortly when we move to Tut-01b!

9. Go back to your GitHub home page, then go to the `Codespaces` menu (or just go to `github.com/codespaces`). You'll see that although you told VS Code to stop the current Codespace - it's still running! The command seems to be more of a "disconnect VS Code from the Codespace" command. :)

  The Codespace will spin down automatically after 30 minutes of activity, but you can also force it to stop by choosing the hotdog menu on the right-hand side and choosing `Stop codespace`:
  
  ![details](images/stop-stopping.png)
  
### Tut-01b

_That might have been a bit exhausting, but you get used to it after a while. You might also find a better way to do it, so if you do, please tell me so that I can look awesome as well!_

Let's do this again - but THIS time, let's spin up a web server inside the Codespace, make a simple webpage on the Codespace machine...and then view that webpage! 