---
layout: post
title: Work in Progress
date: 2026-01-08 08:24:39 +0100
tags: git smartgitty wip worktree
---

## Git Worktree

Did you know about git worktrees? If not, today's as good as any to get to know them. Especially so since they are ridiculously simple and powerful at the same time.

## One Tree to Rule Them All

To put it simply, a worktree is just an additional working copy for an existing, cloned repository. When you clone a repository and checkout a branch, git creates a working copy - the actual files and directories you're working on. These files are all just copies of data in your local git repository, conveniently brought into file-form to be able to work on them (hence the name). Worktrees are the logical extension of this idea - instead of one working copy for one git repository, you can have an arbitrary number of such copies for one git repository. With worktrees, there's seldom a need to clone a repository more than once.

## But Why Not Clone Twice?

Say you're working on a long-lived branch of a big project. Building it takes quite some time, even opening the project in your IDE of choice is something you'd rather not do too often. But that long-lived branch is not the only thing you're working on. Occasionally you're fixing a bug here, implement a simple feature there, maybe build some older version of the software to validate some assumptions. You know, work.

All this requires you to switch between different versions (let's say commits). But doing so in your working tree messes up your build artifacts. Your IDE will probably need to reload the project, files will need to be rebuilt. You may even run into other issues depending on the tools used, some really don't like it when you pull the rug under them. While you can clone your project multiple times, keeping all those clones in sync with upstream can get tedious. And if you want to move commits between these two working trees, it can get messy quite fast. Not to forget that all these clones take up space even though they're almost identical.

Worktrees solve all of this. You get an independent working copy which still shares its history with your other copies, locally. This way, some of your work can stay in progress without getting in the way of other tasks.  

Nice.
