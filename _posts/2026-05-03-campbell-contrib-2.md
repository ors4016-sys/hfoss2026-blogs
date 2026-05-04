---
layout: post
title:  "WiiLink CI Additions"

categories: 
 - Contribution

author: Campbell Bagley
---

As established in my [contribution 1]({% post_url 2026-04-05-campbell-contrib-1 %}), I've been involved in the Wii modding community for a while now. I've primarily been working on my own stuff, but a little while back a library I made was picked up by [WiiLink](https://wiilink.ca), a group that has been working on modern and open source revivals for the Wii's discontinued online services, to make a new and better installer/patcher. Because they were suddenly reliant on something I made, they pulled me into their development Discord server so that I could fix any bugs that pop up or answer any questions they might have.

Over time, I've started to move from just helping them use my library to helping more directly with some of the WiiLink projects. A month or so ago, there were some minor incidents involving newer team members being able to make changes they probably shouldn't be able to make, and that causing things to break in production. This sparked one of the older team members to create a list of all the major infrastructure issues that the WiiLink projects suffer from, ranging from fairly minor to huge issues like no branch protection and no required code review. I won't include the full message here because this was an internal message and I'm not going to make it public, but there were a lot of issues to be addressed.

Among these problems was that the majority of repositories have no automatic build and test CI jobs, and no automatic linting. The build and test CI is necessary so that each project will be compiled and tested on every commit, allowing you to quickly make sure that every new commit is at least theoretically functional. It also allows you to make sure that an incoming pull request will be able to build before merging it. On top of that, the linting is necessary to make sure that people are following code standard guidelines, so that things are more readable and less cursed overall.

I may not understand Go or know a lot about how the Wii's online services work to contribute code, but I understand how to write a GitHub Actions workflow! And so I embarked on a quest to add the missing CI to as many repositories as possible...

## The Spreadsheet (of Doom)

The first thing I did was go through the active (or at least somewhat recently active) projects on the WiiLink GitHub and make a spreadsheet of which ones already had CI workflows, and what they were for. This gave me an idea of what projects I needed to work on, what languages they were in, and any additional notes I needed to worry about.

![]({{ site.baseurl }}/assets/2026-04-05-campbell-contrib-2/spreadsheet-start.png)

Nearly all repositories were missing at least one components, and even the ones that weren't were using action steps that ran on Node.js 20, which is EoL and GitHub will be deprecating soon.

Each repository needed a specific list of CI actions run depending on the language.

For Go repositories, this was:
1. A build step, to make sure the commit can compile.
2. A test step for all repositories with tests written, to ensure that they're passing.
3. A linting run to flag formatting and related issues.

And for Python, this was:
1. An optional build step, for repositories that are meant to be built with PyInstaller or Nuitka.
2. A test step.
3. A linting run.

These are mostly the same, but the implementations between the repositories did have to be a little different.

## PR Speedrun

Once I had my plans laid out, I went through and set up proper CI with updated Node.js 24 actions for the first Go repository in the list, committed, and made sure that everything ran as expected. From there, I had a base that was applicable to essentially all of the other Go repositories, since the linting and a basic `go build` then `go test` workflow are fairly universal.

Once I had that down, I was able to open a lot of PRs in a very short time adding the same workflows to everything (and don't worry, they knew this was coming). I didn't think to take too many screenshots of my open PRs, but I did grab this one of the largest number of PRs I've had open at once:

![]({{ site.baseurl }}/assets/2026-04-05-campbell-contrib-2/pr-speedrun.png)

For most of these repositories, it was mostly just a waiting game once the PRs were opened. The workflows all worked, I just needed someone to take a peek at them and merge them in. However, like with many projects, I had my fair share of...

## Edge Cases

Most of the Go repositories passed tests without any trouble, but some of these repositories expect to actually have data in order to test them. And one of this repositories, [EVC](https://github.com/WiiLink24/EVC), is notable for requiring an active PostgreSQL database connection in order to run the tests.

I don't have a good way to provide visuals for the conversation around this, but I was told that if I was going to add CI to the EVC repository, it was expected that I would actually get the tests running. Now, I had no idea how to do that given that I needed a database. I also did not really receive any direction from the other WiiLink people (everyone is kind of busy and this is not there #1 priority), so I was left on my own to figure it out. And I learned something really interesting! Did you know that you can run Docker containers as services as part of your GitHub Actions workflow? Because you can!

![]({{ site.baseurl }}/assets/2026-04-05-campbell-contrib-2/services-in-gha.png)

It's kind of like writing a `compose.yaml` file, you just tell it what container you want and any parameters it needs, and then your actions workflow will have access to it.

With a functioning database in hand, I also spun up a local PostgreSQL container and figured out what the table needed to actually look like, based on the code that connects to it, and then I was able to add all the columns I needed to actually run the tests. I also needed a signing key because the files it creates during testing are signed, so I added a step for the workflow to create a new signing key during the run, since the key should just be a dummy key and isn't being used for anything anyway.

I'm definitely skimming over some details here to not get way too technical, but the summary is that this was a really difficult repository to work with, and I was kind of left out on my own to figure out how to get it working.

## Conclusions

Lots and lots of the PRs I made have been merged! Here, just take a look:

![]({{ site.baseurl }}/assets/2026-04-05-campbell-contrib-2/prs-merged.png)

I'm still waiting on a few though, which you can also see if we consult the spreadsheet:

![]({{ site.baseurl }}/assets/2026-04-05-campbell-contrib-2/spreadsheet-end.png)

But the majority and done and merged! The few that are still marked NO are only NO because I either have unanswered questions about what's supposed to happen with those repositories, or just because the same CI I've been implementing everywhere else doesn't really make sense (because the project is essentially completed and won't really be getting any more contributions).

This was a lot of fun to work on overall, and it was nice to be able to contribute to WiiLink directly more. I hope to be able to do more infrastructure stuff for them in the future, because I like that kind of stuff and also any gained experience is good experience. I also want the their infra to be less scary, because in many ways they are legitimately one small issue away from everything going down. So y'know, I want to help it not be like that.

And now I'm going to go ping sketch and ask him to merge some of those last open PRs, because writing this article has reminded me of them.
