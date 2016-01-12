---
title: "Roadmap for DC blog"
layout: blog
category: dc
tags: [blog, campaign]
comments: false
published: true
---

There are 2 categories:

* tutorial type post (Monday): mechanistic (how?) vs. understanding (why?)
* example type post (Friday)

## Tutorial posts: mechanics

1. Basic JAGS workflow
2. Using `jags.fit` and updating the model
3. Understanding inits
4. Multiple model definition
5. Understanding modules in rjags
6. DC by hand: the `dclone` functionality
7. `dc.fit`
8. Advanced options: `dciid`, `dcdim`, `dctr`
8. Parallel computing intro (under the hood)
7. RNGs and why they matter
8. rjags in parallel
9. `jags.parfit` and friends
10. `dc.parfit` and size balancing
11. Design decisions and parallel implementation in dclone
12. MCMC diagnostics
13. DC diagnostics
14. MCMC plots
15. DC plots
16. `dcoptions explained`
16. dcmle explained
17. dcmle and package development: PVAClone, sharx, detect as examples

Extra: OpenBUGS, WinBUGS, Stan related posts. Especially when tied to:

* announcing new functionality (Stan)
* or commenting on papers that use Open/WinBUGS.

## Tutorial posts: understanding

1. Understanding summaries: point estimates and interpretation
2. Understanding summaries: intervals and interpretation
3. Identifiability
4. Prior effects: estimates and intervals
5. Prior effects: prediction

## Example posts

These need to be added to dcexamples: need an infrastructure

* Classic BUGS examples
* Examples from published papers (Nadeem, Lele, Torabi, Solymos, etc.)
* LM, LMM
* GLM, GLMM
* GAM, GAMM
* ZI and problems with initial values
* PVA
* Measurement error
* Occupancy
* N-mixture
* Phyogenetic regression
* Spatial models
* Calibration
* Meta analysis
* Expert opinion
