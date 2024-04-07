---
layout: post
# If your post title is longer or more complicated
# than can be represented in the filename, uncomment the following line
# and specify a custom title
# title:  "Implement uninstaller.exe to wincuts"

# Uncomment only one of the below categories
categories: 
- Bug Fix
#- Contribution


# Enter your name below
author: Weijie Ye
---
# What is Wincuts

[Project Website](https://lyubomirt.github.io/wincuts/pages/download.html)

[GitHub Page](https://github.com/LyubomirT/wincuts)

WinCuts is a Windows-native (via Qt) tool for easily setting up and managing custom keyboard shortcuts. It's designed for usage simplicity and is aimed at anyone who wants to save time and increase productivity by using keyboard shortcuts.

#How it works
As of now, WinCuts lets you set up custom keyboard shortcuts for running shell/cmd commands that get launched whenever the shortcut is activated. It's useful if you need to launch specific commands frequently and want to save time by using a keyboard shortcut instead of typing the command every single time.
What's also cool is that none of the shortcuts will go deep enough in your system to cause any damage. They're all running in the context of the user and are limited to the user's permissions. And, of course, the shortcuts are only active within the app and hence won't interfere with any other shortcuts you might have set up (basically, you can't accidentally override a system shortcut).

I chose to contribute to WinCuts because it's something that could improve my productivity when developing on Windows. Since there are several issues that I can fix, I decided to help this project out.

# Relevance from Comm Arch Experiences
From my previous HFOSS (IGME-582) experiences in Comm Arch assignments, we were tasked with investigating existing open-source projects of different sizes. We collected much information, including onboarding processes, contribution guidelines, and recommending projects for a specific skill level. These skills were relevant in my selection of this project, as I was able to find a bug tailored to my skills and provide a window system related feature in the project. 

The project provided both [contribution guide](https://github.com/LyubomirT/wincuts/blob/main/CONTRIBUTING.md), [code of conduct](https://github.com/LyubomirT/wincuts/blob/main/CODE_OF_CONDUCT.md) and the license this project uses is BSD-3-Clause license.
Since this is a relatively new project, there aren't many participants, but the owner of the project is very active; he can always respond to you within a day, from my experience.

# The Issue
The issue that I investigated in this project was Creating an uninstaller for the app. Instead of the cleanup file, an uninstaller can be created that will make sure everything is done swiftly. Also, it may help people who aren't quite tech-savvy avoid confusion and any potential mistakes.
![issue](https://github.com/LyubomirT/wincuts/issues/2)

![Screenshot 2024-04-07 131600](https://github.com/wy8933/hfoss2024-blogs/assets/112401719/c48b0db1-2885-4440-9b6c-709a1237023e)

So, I forked the repository and opened a branch and made the appropriate changes, which lead to me making a pull request. Before pushing anything, I made sure the code ran without issues on my own machine and when containerized with the Dockerfile, and everything built and ran without new errors. 

As of the writing of this blog post, the PR opened has not been accepted yet since there are still some small problems with my solution which I am still working on it now, 

[Link to pull request](https://github.com/LyubomirT/wincuts/pull/10)
