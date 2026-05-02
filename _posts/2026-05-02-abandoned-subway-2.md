\# Rochester Abandoned Subway: Part 02
May 2, 2026 • Joshua DeWinter

## Introduction to the community
### What the project is
For my second contribution, I have continued working on the Rochester Abandoned Subway
VR experience - a recreation of the Rochester Abandoned Subway in VR!

![Rochester Abandoned Subway Picture](../assets/2026-05-02-abandoned-subway-2/abandoned-subway-rl.jpg)
### Why you picked it
I picked this project because VR is a big passion of mine, and I was put on this
project for my DHSS Seminar with Jess
### How Comm Arch showed this would be good to work with
It is a small project that I could really get into and work on in several capacities
### What resources were already available
The project has been in development digitally since 2022, and in VR since 2024,
with lots of photos and references for how the subway is layed out.
## The issue
### How I decided to pick the issue (and what it was)
Building off of getting the smooth locomotion working, the rest of the player
controller (physical hands, climbing) and other interactions (pressing buttons)
needed to be added for complete immersion.

![The "Physical Playground" testing scene](../assets/2026-05-02-abandoned-subway-2/physical-playground.png)
### How I pursued it
I started off by referring back to a project I worked on a couple years ago where
I did something relatively similar in terms of the player controller. Replicating
that was relatively simple, and then it was on to the interactions.
### What happened during the process
The climbing remains a slight issue, with the area the player is able to grab to
pull themself up being to large (with no current discernable cause). Even so, it
worked well enough that it wasn't the most notable and I proceeded to making the
buttons.
### What blocked the project
The buttons themselves caused me much grief. I wanted them to be physical, using
some sort of spring physics to push themselves back up between two points, however
what I had been looking into did not pan out and my physics button was placed on
the backburner. Thus, a simple collider that triggers an animation of the button
being pressed was vastly simpler to create and functioned well.

![VR Buttons](../assets/2026-05-02-abandoned-subway-2/buttons.png)
### How I succeeded in getting it accepted/merged
After a lot of messing around with SSH Keys, I was finally able to push my work
to the repository as I am a primary contributor.
## Conclusion
### What did I learn
That making a physics based button in Godot was not as simple as I was thinking
and it will take more time and effort to get it working how I want.
## Will I contribute to this community again?
I will be contributing to the project continuously for the next calendar year if
everything goes to plan.
