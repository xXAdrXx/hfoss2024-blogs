---
layout: post
# If your post title is longer or more complicated
# than can be represented in the filename, uncomment the following line
# and specify a custom title
# title:  "Sample Blog Post"

# Uncomment only one of the below categories
categories: 
- Bug Fix
#- Contribution


# Enter your name below
author: Holly Allen
---
## What and Why
MonoGame is a game API for C# and is maintained at [github.com/MonoGame](https://github.com/MonoGame/MonoGame). MonoGame's Issues tab on their GitHub has a specific label for new contributors and some of these issues have existed since 2019 with no progress made.

I'm currently a TA for IGME 106, so I help students with MonoGame fairly frequently. It's a project I'm used to working in, but have never personally contributed to yet. MonoGame has had a few issues recently as they've changed where their documentation lives, so it was a project I'd been considering contributing to for most of the semester.

## Community Evaluation
MonoGame has a few channels the general community can access to see updates, bug fixes, and get assistance. When reading through thier GitHub docs, it seems they switch the people managing the project every month, so only two people are in charge of the project at any given time. This did cause a little grief for me. My process in solving the bug fix started with one pair of maintaners and since I submitted a pull request at the beginning of April, it should now be a new set.

MonoGame has a [great guide](https://github.com/MonoGame/MonoGame/blob/develop/CONTRIBUTING.md) on how to contribute to the project, but there isn't a Code of Conduct on their GitHub. The foundation running MonoGame has [bylaws](https://monogame.net/foundation/), but that's as much as I can find even related to a community standard.

MonoGame's main way to communicate while contributing is their Discord. I personally didn't join because it appeared to be a server focused both on the development and usage of MonoGame and I don't particularly enjoy being in giant servers. Silas, who also chose to contribute to MonoGame did join the server and gave me a little insight onto how it was set up. Should I have probably joined? Yes. Would it have personally helped me? Probably not. 

## Choosing an Issue
There were a lot of problems in the new contributor tag! The hard part came with choosing. Some seemed to take a little more knowledge of the project while others seemed like they may not even be issues at all. I chose [Issue #6661](https://github.com/MonoGame/MonoGame/issues/6661), which was originally submitted in 2019 and had only seen 1 post of conversation in its thread. MonoGame asks that you post that you're looking at an issue before you start working on it so there aren't overlaps in progress. 

![Issue post by sharkist on GitHub discussing problem with the Content Writer](https://h3allen.github.io/assets/2024-03-26-monogame-bug-fix/Issue_Post.png)

## Fixing the Bug
So I made my post and started looking at the problem. The biggest thing I wanted to know from the maintainers was if it was even still a problem. The initial issue had a dead link to an image and only a fleeting discussion on what the actual problem is on the technical end.

IMAGE TIME

Looking at the bug, it really was a simple fix. Pull all of the text generation code out of the Flush method and put it elsewhere. That's simple enough! See?

{% highlight c# %}
/// <summary>
/// All content has been written, so now finalize header, 
/// footer and anything else that needs finalizing
/// </summary>
public void FinalizeContent()
{
  // Write shared resources to the end of the body stream
  WriteSharedResources();

  using (var contentStream = new MemoryStream())
  {
    this.OutSteam = contentStream;
    WriteTypeWriters();
    bodyStream.Position = 0;
    bodyStream.CopyTo(contentStream);
    contentStream.Position = 0;

    // etc.
  }
}

/// <summary>
/// Clears buffer using BinaryWriter's Flush method
/// </summary>
public override void Flush()
{
  base.Flush();
}
{% endhighlight %}

That was pretty simple. I can mostly deduce what the solution was from the maintainer's response to the posted issue. Ideally, tossing this method in to the existing structure and making sure to call it before the current Flush method wherever it shows up, which happened to only be one.

### Maintainer Response
After I'm partway through the solution, one of the maintainers finally responds. This starts a discussion with the maintainer who initially posted on the issue about whether or not this is an actual problem.

IMAGE TIME

After their conversation and agreement that this was, in fact, still an issue, I made a quick post about what the solution should look like. I mostly just wanted to ensure I actually understood what the problem was and how to solve it, since I've never worked on a content writer before and I didn't know how their actual system worked. 

IMAGE

I never got a response.

## Pull Request
After two weeks of hoping that maybe they'd suddenly respond with some more information, I just took the plunge and submitted my pull request. You can find it [here](https://github.com/MonoGame/MonoGame/pull/8266)!

## Conclusion
It was certainly an experience I had! Frustrating to be stuck in quasi-limbo because the maintainers weren't paying attention to the problem. MonoGame has larger issues and feature requests open at the moment (including some bounties), so it makes sense that I wasn't a high priority. As of right now, my pull request hasn't been looked at and I don't exactly hold a high hope that it will any time soon. Some PR's have been open for years with no updates and I may just be the next one on the list. 

![a meme depicting a cartoon person screaming "OPEN SOURCE"](https://ankitrokdeonsns.github.io/assets/img/open_source.jpeg)


[Here](https://www.markdownguide.org/basic-syntax/#images-1) is a link to more documentation on markdown images.

[Here](https://www.markdownguide.org/extended-syntax/#tables) is a link to more documentation on markdown tables.

[jekyll-docs]: https://jekyllrb.com/docs/home
