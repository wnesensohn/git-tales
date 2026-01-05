---
layout: post
title: Do You Even Split?
date: 2026-01-05 17:35:19 +0100
tags: git smartgitty split modify rebase-interactive
---

## The Making of a Crime Scene

I'm working on a feature, nothing out of the ordinary, when suddenly I come across a glaring violation of all that is holy, _a newline where no newline should go_ in some code far, far away.
Being no barbarian, I do what must be done in such a situation: Getting rid of the newline, it's not like there are other options.  

But attention, although being [all you need apparently](https://en.wikipedia.org/wiki/Attention_Is_All_You_Need), is not one of *my* strong suits, so I quickly forget about the newline and proceed with my feature.

_Of course_ it gets committed with the other changes. I'm no machine, and even if I was, Rube Goldberg would be my mother.

## The Crime

Git was not made to forget, but was made not to forget. And so there comes the time when I go through the commits and detect this totally unrelated change. You may think such matters not, but imagine: You're reading a novel about a king and his castle, and just as the intruders are knocking at the door and the story really picks up the pace, the book mentions that the weather four weeks ago has been splendid for taking a walk.

The book isn't wrong, the weather really was that good, but the reader is thrown off, the pacing ruined. It takes attention away from where it should rather be, and attention is a precious good.

## The Solution

Do your reviewer (or your future self) a favour. Split away the change. Move the commit to another branch, or push it in front of your current changes. Clean up the history.  

Use whatever tool you like, but make the change, no excuses.  

Of course, with SmartGit, you can just split away an arbitrary number of files, or even hunks.  

Nice.
