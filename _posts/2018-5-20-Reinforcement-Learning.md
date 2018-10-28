---
layout: post
title: Reinforcement Learning
---

Hello welcome to my second post! Today I want to talk about Reinforcement Learning!

## What is Reinforcement Learning?

An **agent** will learn from the environment **stage** by stage by interacting with it and receiving **rewards** for performing **actions**.
This RL loop outputs a sequence of state, action and reward. The goal of the agent is to **maximize the expected cumulative reward**.
The cumulative reward at each time step $t$ can be written as:
$G_t = \sum_{k=0}^TR_{t+k+1}$
However we should discount our reward over time.

##
