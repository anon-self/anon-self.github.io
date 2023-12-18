---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Home
nav_order: 1
description: "Mobile Application Coverage: The 30% Curse and Ways Forward"
permalink: /
---

### Mobile Application Coverage: The 30% Curse and Ways Forward

---

Testing, security analysis, and other dynamic quality assurance approaches rely on mechanisms that invoke software under test, aiming to achieve high code coverage. A large number of invocation mechanisms proposed in the literature, in particular for Android mobile applications, employ GUI-driven application exploration. However, studies show that even the most advanced GUI exploration techniques can cover only around 30% of a real-world application. With extensive effort being invested into GUI exploration strategies, in this paper, we factored out GUI-related issues by having skilled human analysts perform a thorough manual exploration of a number of large and popular Google Play applications. To our surprise, coverage achieved by humans exceeded that of the automated tools by only a small fraction.
The main reasons preventing human analysts from covering the entire application include application dependencies on device characteristics, remote servers, and external resources. We further explore characteristics of these dependencies and discuss the applicability of dynamic techniques that extend beyond GUI exploration, i.e., that involve various forms of code alteration, to bypass these dependencies. Based on our analysis, we outline possible future research directions for improving application coverage, such as developing adaptive exploration strategies that determine when and how to bypass dependencies.
