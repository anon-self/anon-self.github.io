---
layout: default
title: Dataset
nav_order: 2
description: "Mobile Application Coverage: The 25% Curse and Ways Forward"
permalink: /docs/dataset
---

### Selected Google Play Applications

We select 42 top ranked free applications from the Google Play Store, sampled in 2023, covering all app categories:

<a href="../assets/images/apps-latest.png">
    <img 
        src="../assets/images/apps-latest.png"
        alt="Selected Google Play Applications"
    >
</a>

---

### Selected Benchmark Applications

We also experiment on a subset applications from the [AndroTest dataset](http://www.cc.gatech.edu/∼orso/software/androtest). From 68 applications originally present in the dataset, we exclude 7 apps which crash on startup and for which we can not reliably identify source code.

We reconstitute the dataset by selecting the latest available version for each of the 61 applications as of July 2023.
We further divide it into two datasets depending on whether the applications are also available on the Google Play Store or not, namely BenchGP and BenchNotGP:

<a href="../assets/images/benchgp.png">
    <img 
        src="../assets/images/benchgp.png"
        alt="Selected Benchmark Applications (on Google Play)"
    >
</a>

<a href="../assets/images/benchnotgp.png">
    <img 
        src="../assets/images/benchnotgp.png"
        alt="Selected Benchmark Applications (not on Google Play)"
    >
</a>

