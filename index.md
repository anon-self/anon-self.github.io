---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Home
nav_order: 1
description: "Mobile Application Coverage: The 25% Curse and Ways Forward"
permalink: /
---

### Mobile Application Coverage: The 25% Curse and Ways Forward

---

Testing, security analysis, and other dynamic quality assurance approaches rely on mechanisms that invoke software under test, aiming to achieve high code coverage. The majority of invocation mechanisms proposed in the literature, in particular for Android mobile applications, employ GUI-driven application exploration. However, studies show that even the most advanced GUI exploration techniques can cover only around 25% of a real-world application. With extensive effort being invested into GUI exploration strategies, in this paper, we assumed an ideal GUI exploration “tool”: a skilled human analyst. To our surprise, coverage achieved by a human analyst when exploring a number of large and popular Google Play applications exceeded that of the automated tools only by a small fraction. The main reasons preventing a human GUI tester to cover the entire application include application dependencies on device characteristics, remote servers, and external resources. Inspired by this observation, we perform a systematic analysis of existing dynamic techniques that extend beyond GUI exploration. We categorize the main mechanisms that these techniques employ to trigger applications, e.g., various forms of code alteration, and the ability of each mechanism to address the identified exploration challenges. We then discuss possible future research directions for substantially improving application coverage, such as developing more sophisticated approaches that determine when and how to bypass vs. mock external application dependencies.