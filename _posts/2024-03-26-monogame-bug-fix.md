---
layout: post
# If your post title is longer or more complicated
# than can be represented in the filename, uncomment the following line
# and specify a custom title
# title:  "Sample Blog Post"

# Uncomment only one of the below categories
categories: 
#- Bug Fix
#- Contribution


# Enter your name below
author: Holly Allen
---
## What and Why
For my bug fix, I decided to work on some of the new-contributor-friendly bugs in MonoGame. I'm currently a TA for IGME 106, so I help students with MonoGame fairly frequently. It's a project I'm used to working in, but have never personally contributed to yet. 

MonoGame's Issues tab on their GitHub has a specific label for new contributors and some of these issues have existed since 2019 with no progress made.

## Community Evaluation

## Choosing an Issue

## Fixing the Bug
Looking at the bug, it really was a simple fix. Pull all of the text generation code out of the Flush method and put it elsewhere. That's simple enough! See?

{% highlight c# %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

That was pretty simple. I can mostly deduce what the solution was from the maintainer's response to the posted issue. Ideally, tossing this method in to the existing structure and making sure to call it before the current Flush method wherever it shows up, which happened to only be one.

### Uh Oh...
Building is awful. I need MonoGame stable on my laptop but I also need to tear it out and rebuild it with my version to ensure my bug fix actually fixed the "bug."

Well, I'd started fixing the bug but...
- I didn't have a concrete example of what the bug was from the original issue posted, so I couldn't exactly test it and know it was solved
- The image originally posted with the issue is a dead link and I can't see it
- The current maintainers hadn't paid any attention to this issue in years and my interest in solving it caused them to take notice
- One maintainer wasn't sure this was an issue, the other was
- The issue seems to not be something breaking and more something doing a job it isn't supposed it
- I don't know their architecture nor their goals, so I don't know if my solution will actually work
- They stopped responding to me after having a conversation between themselves on the thread

## Pull Request

## Conclusion

### Images

![a meme depicting a cartoon person screaming "OPEN SOURCE"](https://ankitrokdeonsns.github.io/assets/img/open_source.jpeg)


[Here](https://www.markdownguide.org/basic-syntax/#images-1) is a link to more documentation on markdown images.

[Here](https://www.markdownguide.org/extended-syntax/#tables) is a link to more documentation on markdown tables.

## More Jekyll Features
Jekyll can also provide some formatting and other useful features. Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. Here are some notable examples:


### Code snippets




[jekyll-docs]: https://jekyllrb.com/docs/home
