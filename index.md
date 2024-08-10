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

<p style='text-align: justify;'>
Testing, security analysis, and other dynamic quality assurance approaches rely on mechanisms that invoke software under test, aiming to achieve high code coverage. A large number of invocation mechanisms proposed in the literature, in particular for Android mobile applications, employ GUI-driven application exploration. However, studies show that even the most advanced GUI exploration techniques can cover only around 30% of a real-world application. This paper aims to investigate “the remaining 70%”. By conducting a large-scale experiment involving two human experts, who thoroughly explored 61 benchmark and 42 popular apps from Google Play, we show that achieving a substantially larger coverage for real-world applications is impractical even if we factor out known GUI-based exploration issues, such as the inability to provide semantic inputs and the right order of events. The main reasons preventing humans from covering the entire application include application dependencies on device configurations and external resources. Thus, future investment into GUI-based exploration strategies is unlikely to lead to substantial improvements in coverage. To chart possible ways forward and explore approaches to satisfy/bypass these dependencies, we thoroughly analyze code-level properties guarding them. Our analysis shows that a large fraction of the dependencies could actually be successfully bypassed with relatively simple beyond-GUI exploration techniques. We hope our study can inspire future work in this area and also provide a realistic benchmark for evaluating this work.
</p>