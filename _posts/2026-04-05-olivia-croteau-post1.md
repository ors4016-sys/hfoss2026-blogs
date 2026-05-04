---
layout: post
# If your post title is longer or more complicated
# than can be represented in the filename, uncomment the following line
# and specify a custom title
title:  "Olivia Croteau Contribution 1: CampusPulse"

# Uncomment only one of the below categories
categories: 
#- Bug Fix
- Contribution


# Enter your name below
author: Olivia Croteau   
---

## Why did I pick [CampusPulse](https://campuspulse.app/)?
I originally wanted to contribute to a larger project for a larger humanitarian organization, such as [Open Data Kit](https://getodk.org/) or [Nava](https://www.navapbc.com/), and build connections to those companies. However, as this is the first time I've ever contributed to an open source project, I quickly found that it would be best to start with something like CampusPulse where I already had knowledge of its use cases, connections to its maintainers, and fellow students who were also learning to contribute to it. In short, I chose it for my connection to its mission and community, and will take what I learned to join another community for my second contribution.

## What was contributing to CampusPulse like?
I definitely had the easiest time getting set up with [CampusPulse homepage repo](https://github.com/CampusPulse) compared to the other repos I tried. It only required me to install Hugo to run in a development server. Henry Sanders kindly showed me how to fork a repo and and what making a pull request actually looked like. So big thanks to him. I immediately found a typo in the README file and decided to fix it in order to practice the process. Following the instructions from the sample blog post I made my pull request and got these four automatic errors. (Note: i am unable to add a link to this PR as it was accepted and is no longer visible, but here is the [commit](https://github.com/CampusPulse/homepage/commit/1c79e2300baaaaf2231b23cb71b10366442b706c).)

![Screenshot of 'Fix README typo' pull request with 4 failing checks.](_posts\assetsCroteau\PR1.png)

I sent this screenshot to Adrian, the technical lead and maintainer, and he got back to me within a couple of hours about the issue. He said that there were some out -of-date settings he had to tweak and accepted my pull request. You can see that 'codebase' is now spelled correctly on the [README](https://github.com/CampusPulse/homepage/blob/main/README.md).

## What was my contribution?
With that process cleared up I went ahead and made a more signifigant contribution. I found an open issue 'Idea: link to RIT web resources.' The desired [link](https://www.rit.edu/webresources/) was provided, so all I had to do was add it to the list of services. Each service on the homepage rendered as a clickable bubble with an icon, title, description, and of course the associated link. Each of these was stored in a datafile, so I just had to pick an icon from Fontaweesome, write the description, and add everything to the datafile. I had structured a website this way before, but I could tell it was designed to be easily added to. The CSS and JavaScript automatically applied themselves to the link I added. It definitely took me longer to figure how to go through the pull request process than it did to understand the codebase. I will note that there wasn't a lot of documnetation of how the website was structured, or, for example, where the icons came from. Luckily I was familiar with Fontawesome and recognized links to it when I inspected the page and knew how to reference my chosen icon. This time [my pull request](https://github.com/CampusPulse/homepage/pull/10) immediately passed all checks and awaits merging.

![Screenshot of 'Issue #2: added link to RIT web resources' pull request with 4 passing checks.](_posts\assetsCroteau\PR2.png)

## How much effort did this assignment require?
The contribution itself was fairly low effort! I just had to learn how to actually go through the branching/checkout/pull request process. But I owe the ease of this process to how easy it was to set up my environmment and run the CapusPulse homepage in developer mode. 


<!-- 
## More Markdown features
In addition to the formatting used so far in this document, Markdown offers several other things that may be useful to blog posts. 



[Here](https://www.markdownguide.org/basic-syntax/#images-1) is a link to more documentation on markdown images.

### Tables

| Item         | Price    | # In stock |
| ------------ | -------- | ---------- |
| Juicy Apples | 1.99     | *7*        |
| Bananas      | **1.89** | 5234       |

[Here](https://www.markdownguide.org/extended-syntax/#tables) is a link to more documentation on markdown tables.

## More Jekyll Features
Jekyll can also provide some formatting and other useful features. Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. Here are some notable examples:


### Code snippets

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}


[jekyll-docs]: https://jekyllrb.com/docs/home -->
