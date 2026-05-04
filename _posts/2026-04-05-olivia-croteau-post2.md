---
layout: post
# If your post title is longer or more complicated
# than can be represented in the filename, uncomment the following line
# and specify a custom title
title:  "Olivia Croteau Contribution 2: CampusPulse"

# Uncomment only one of the below categories
categories: 
#- Bug Fix
- Contribution


# Enter your name below
author: Olivia Croteau
---

<!-- 
What happened when you did
What blocked you if you were blocked
How you succeeded getting it accepted/merged (if you did) -->


## How did I pick my issue? [CampusPulse](https://access.campuspulse.app/catalog)?
I chose to stick with contributing to the same community for this assignment. However, I did choose a different repository this time since I had originally done a smaller offshoot project. I found an [issue](https://github.com/CampusPulse/access-directory/issues/34) in the [access directory repository](https://github.com/CampusPulse/access-directory) that was focused on licensing; particularly that the repository didn't have one at all. I'm interested in licensing for my own projects; I was recently discussing with a professor about utilizing a particlar license that differentiates rights for non-profits vs proprietary companies. This is slightly tangental to that subject, but I figured it would be a solid introduction to adding licenses. So this was different from my previous contribution because it wasn't a big fix.


## How did I create the license?
The comments under the issue had differing opinions on which license to use, but I knew that many open source projects utilize the MIT license, so that's the one I went with. I found instructions from GitHub and MIT themselves on how to add the license, and I listed Adrian Edwards as the owner of the repository. The comments discussed how the README should specify which parts of the code had been written by TunnelVision, but I decided that these qualifiers should be added by somebody with more subject matter expertise, and noted this in my pull request.

![Screenshot of comments under issue.](_posts\assetsCroteau\issueComments.png)


## How did it go?
For my previous contribution I did everything in the command line. This time, because I want just creating .md file, I did everything with the GUI. GitHub kept prompting me with the next steps, like creating a pull request for my contribution. It automatically passed all checks because the file creation didn't conflict with anything. I was surprised to see the prompt to automatically merge my own pull request. I clicked the button and it merged and closed, so I'm hoping that was the correct move. There is a trail between the issue and my closed [pull request](https://github.com/oliviacroteau667/access-directory/pull/1) so the maintainers can double-check that everything looks good, and I haven't recieved any comments back, so I think it's all good.

![Screenshot of pull request with description and closed notification.](_posts\assetsCroteau\PR3.png)



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
