---
title: 'Current Research'
date: 2019-02-11T19:30:08+10:00
draft: false
weight: 2
summary: TMB and R-INLA, Cancer Mapping in the EU, Spatial model assessment
---

## TMB and R-INLA

While I was working to develop methods and code to handle very large geostatistical models, we started studying Tempalte Model Builder (TMB) as a viable alternative to Integrated Nested Laplace Approximations (R-INLA).

In addition to being quite fast and resource efficient, TMB can also be applied to a wider class of problems than R-INLA.

I've taken the time to really dig into the TMB algorithm and have compared it against the methods used in R-INLA. I also ran many many geostatistical simulations to compare the two in a variety of settings.

You can check out a working version of a paper that digs into this on [arXiv](https://arxiv.org/abs/2103.09929).

A bit of code to get you started modeling the same continuous spatial models in both R-INLA and TMB is available in my [Docs](/docs/inla-tmb/).

## EU Cancer Mortality and Incidence Estimation

Across the European Union, different country members have different
systems for recording the cancer mortality and incidence of their
populations. Some record only national-level mortality data, while
some record ssubnational cancer mortality and incidence occurence via
registry systems, and many others have a system that falls in
between. To complicate matters even further, most coountries have
changed their data collection methods sometime in the last few
decades.

Cancer incidence, the occurence of new cases, is generally more useful
for planning and resource allocation when compared mortality records,
which record deaths. On the other hand, mortality data is more quickly
and more frequently available.

In this project I am jointly model cancer incidence and mortality,
using the mortality-incidence ratio, across age-space-time. Then, we
use more recently available mortality data to predict the recent
incidence that is not yet available.

More notes on this project will soon be available in my [Docs](/docs/eu-cancer/).

## Cross-validation for spatial model assessment

Assessing the quality of random effects (REs) estimates can be tricky
because (assuming the correct model) expected qualities of the REs,
such as coverage, are true when averaged across the distribution of
the predicted REs. As the magnitude of one aprticular true random
effect varies around the mean of the REs, the expected coverage for a
particular confidence or credible level is [known to vary the nominal
target level](https://academic.oup.com/biomet/article/105/2/319/4967742). This
begs the question about what may be expected in leave-one-out (or
other) cross-validation schemes for model assessment in spatial
effects models.

In this project I'm studying the expected behavior of goodness-of-fit
statistics from various cross-validation approaches for spatial
models.