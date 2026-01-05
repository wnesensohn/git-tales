---
layout: post
title: History Is Haunting Me
date:   2025-11-17 09:46:19 +0100
tags: git smartgitty firstpost rebase modify rebase-interactive
---

## Hello, SmartGit

I'm in the process of building an improvement in *SmartGit* (more about it maybe later).

As it so happens, I'm new to this codebase, language, standard library and whatnot - you could say I'm a total beginner here, which means learning this stuff on the go is the name of the game. No problem per se, but producing some readable, well-fitting code in the process is a bit of a challenge.

It's even more challenging to do so while not producing only a single commit in the end (which would've turned out too big to be reviewable), but a clean commit history where every commit tells [the chapter of a story](https://content.subvisual.com/talk-roundtable/sasa-juric-tell-me-a-story/).

## Making an Omelette, and Breaking Eggs

Learning on the go, as you likely know, involves a lot of exploration and backtracking. There's areas to get to know, concepts to learn, patterns to detect (in various flavours, as an established codebase wasn't built in a day), new language features to come accustomed to (and other language features you find missing, only to find out the idiomatic way to perform the same in the new language), and so on. It's elevated when you're learning a new programming language, but realistically every sizable project has its own language and feel.

I'm a fan of clean commits, and at *SmartGit* we're taking version control seriously, but let me tell you: Keeping my branch clean from the get-go was impossible for me. There were formatting changes (left overs from explorations), not using the language correctly, breaking all the coding guidelines left and right (I'm looking at you, _final_, and also you, _var_), and some commits didn't even build even though they absolutely did when I committed them, I swear! But there was also some useful stuff, good refactorings, and my improvement somewhere buried in between.

## If You Leave Me Now...

Anyway, calling my losses and starting from scratch wasn't very appealing, so I got myself a coffee and stared at my git history for quite a while. Split this, undo that, move this one up, ... - some might call this crazy, as the goal was to come up with a branch whose' head was working-tree-identical to the one I already had. Totally crazy. But who is going to read my story when I leave in all the edit marks and redactions? I had to do this, and if you're not intimate with your git client of choice yet, I can assure you that you will be after cleaning up a reasonably big (and comparably awful) branch just like that one.

It should come as no surprise that we're also using *SmartGit* while developing *SmartGit*, but even then I get to learn quite a few new things about the git CLI, and by far the most useful git command recently was
```bash
git rebase -i `git merge-base feature/my-awesome-smartgit-improvement develop`
```
which makes it a breeze to scuttle through your history and get it cleaned up.

What does that accomplish, a rebase of the feature branch to the merge-base of the feature branch? What a nonsensical thing to do. But rest assured, it's not. It's just git naming commands after their implementation, and not after their purpose. Translated, the above basically means

1. reset my feature-branch back to the merge base
2. from there, let me decide what to do with each commit which came afterwards (pick, drop, edit, squash, reword)
4. until we have processed all commits from the current feature-branch

With this tool, it's easy to squash commits, split off other parts squashing them again, pull minor edits in front of the big changes and all that, doing it in one go without having to create sacrificial branches or doing cherry-picks manually.

Can you do this with *SmartGit* as well? Turns out you can, just right-click on the first commit you want to modify, select "Modify...", and you'll get essentially the same thing with a nice UI. Also, it plays nice with git, using the same commands under the hood, so you can switch between git CLI and SmartGit whenever you want.

## Wrapping up

Suddenly a clean commit history got much more approachable, and the history went from an almost incomprehensible meta-horror-story to a nice novel with a rhythm and an ending. The history now documents the intent, and readers are able to capture that intent much faster.

Nice.
