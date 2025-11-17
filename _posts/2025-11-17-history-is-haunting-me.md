---
layout: post
title: History is Haunting me
---

I'm in the process of building an improvement in smartgit (more about it maybe at some other time).

As it so happens, I'm quite new to this codebase, language, standard library and whatnot - you could say I'm a total beginner here, which means learning this stuff on the go is the name of the game. No problem per se, but producing some readable, well-fitting code in the process is a bit of a challenge.

It's even more challenging to do so while not producing only a single commit in the end (which would've turned out too big to be reviewable), but a clean commit history where every commit tells the chapter of a story [link to sasa-talk tell me a story].

Learning on the go, as you know, involves a lot of exploration and even more backtracking. There's areas to get to know, concepts to learn, patterns to detect (in various flavours, as an established codebase wasn't built in a day), new language features to come accustomed to (and other language features you find missing, only to find out the idiomatic way to perform the same in the new language), and so on.

I'm a fan of clean commits, and it should come as no surprise that at smartgit we're taking version control seriously, but let me tell you: Keeping my branch clean from the get-go was impossible for me. There were formatting changes (left overs from explorations), not using the language correctly, breaking all the coding guidelines left and right (I'm looking at you, _final_), and some commits didn't even build even though they absolutely did when I committed them, I swear! But there was also useful stuff, good refactorings, and my improvement.

Anyway, calling my losses and starting from scratch wasn't very appealing, so I got myself a coffee and stared at my git history for quite a while. Split this, undo that, move this one up, ... - some might call this crazy, as the goal was to come up with a branch whose' head was working-tree-identical to the one I already had. Still, I had to do this, and if you're not intimate with your git client of choice yet, I can assure you that you will be after cleaning up a reasonably big (and comparably awful) branch like mine.

It should come as no surprise that we're using smartgit while developing smartgit, but even then I got to learn quite a few new things about git, and by far the most useful git command here was "git rebase -i `git merge-base feature/my-awesome-smartgit-improvement develop`" which makes it a breeze to scuttle through your history and get it cleaned up. However, could you do this with smartgit as well? Turns out you can, just right-click on the first commit you want to modify and select "Modify...", and you'll get essentially the same thing in smartgit.


Suddenly a clean commit history got much more approachable, and the history went from an almost uncomprehensible horror-story to a nice novel with a rhythm and a goal. Nice.
