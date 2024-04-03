---
layout: post
categories: 
- Bug Fix
author: Silas Mercer
---

# What is MonoGame

MonoGame is a framework built off an as a successor to the deprecated Microsoft XNA framework for cross-platform video game development. This framework is used by a fair number of indie hit games, such as Stardew Valley. I picked it as it is a framework I am familiar with for hobby development and through academic development in the Game Design and Development program. I figured it would be good to work in as it has a fair number of simple and complex issues that can be good for both a Bug Fix and a larger contribution.

# Community Evaluation

MonoGame is a large community as a whole. It has a few active contributors outside of the core maintainer group, and has a consistent flow of drive-by contributors. Their Code of Conduct is outlined pretty well and has good overall resources for how to contribute to the framework and documentation. MonoGame is a Federation-style community. This can be seen by the increase in active users over the years and the consistent flow of contributors. It utilizes some automation in the contribution process to first confirm that any pull request will not cause build issues or merge issues. There were plenty of resources, both from a contribution standpoint, and a user standpoint. Both groups of people need to know how the API works in order to better improve or contribute to the framework. Mainly what MonoGame is lacking on is more up-to-date tutorials with more recent versions of .NET.

# Choosing an Issue

When looking at issues to pick once I decided on MonoGame, I first looked at the "Good First Issues" tab. It had some good options, but quite a few were several years old. Mainly because a lot of them are very minor fixes or heavily tutorial and documentation based. These get skimmed over by more experienced contributors in order to let newer contributors add to them. However, I was able to find one that was posted fairly recently. It was posted a week before I saw it. It was a potential issue with the asset creation tool that utilized a PathHelper class. It seemed like a very small issue at first, and figured it'd get processed a lot quicker as it was more critical to the framework if there was a bug. The issue was reported as a possible bug due to how the GetRelativePath() function would have extra symbols that would mess up creating a path inside the project.

# How was it Fixed?

The first step was to see if the issue existed and what the PathHelper was spitting out. This was done by using the Debug.WriteLine("string") function. What this function does is it prints out the given string to the output console in debug mode. This is perfect as it allows me to see the paths at different points in the asset creation process. What I noticed, however, is that the extreneous symbols that should be there causing issues, weren't. This went against what the issue on GitHub said was supposed to happen. After reading through some relevent Microsoft documentation on the URI (Uniform Resource Identifier) in the .NET framework, it is working as intended and the issue didn't exist in the mainline .NET version used for the framework. In this case, this is .NET 8. Granted, the issue did say it was a potential bug afterall. I reported these findings to the GitHub issue and waited for a response. This waiting became a blocker.

# Now What?
After a brief email chain with SJ and Adrian, we agreed that I should do a different issue since no PR was submitted as a result. This led me to work towards the tutorial and documentation side of things. So, as a result, I went back and looked through the project posted on the GitHub called "Call to Improve Tutorials." This project has a list of issues where documentation and tutorials that need to be done or be improved go. I noticed this one issue from 2019 that was still not done. It was an issue requesting a tutorial for the Joystick class. I know a bit about programming for different input devices, so I figured I'd look at the relevent API documentation and work on it. 

# Fixing it Part 2

After reading through the documentation, I made a test project to test out some code in order to write up the tutorial with code samples as the other tutorials on the website do. I also read through the writing style guidelines in order to ensure that my tutorial would have the best shot at being approved. Once I got the input working for the test project, I used the pre-existing introductory tutorial series as a place to add this tutorial. Since the fifth tutorial goes over basic input, I figured it would fit best there. Since it was simply editing and adding a stylized tutorial to an existing one that follows the same style, there wasn't anything blocking me for this issue. I sent in the PR on 4/3/2024 and I am blocked by waiting for a response.

# Resolution

The first issue got closed as a result of my report and is no longer an issue to be worried about for MonoGame. The second issue I worked on is still in the process of being reviewed. I am quite happy with how things turned out. The main thing I wish would be different is that my first issue resulted in a PR instead of me having to hop around midway through the time frame to get something else done by the class' timeline.