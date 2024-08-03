---
layout: default
title: Tools
nav_order: 4
description: "Mobile Application Coverage: The 30% Curse and Ways Forward"
permalink: /docs/tools
---

### Selected Papers and Categorization

---
We select 22 papers which go beyond UI exploration from existing work and characterize their app exploration approach along four dimensions: Invocation Strategy,  Navigation Strategy, Value Generation Strategy and Value Generation Type. For completeness, we also mark which of the selected papers perform GUI Exploration by sending GUI and/or System Events (in addition to their main exploration strategy).

<a href="../assets/images/tools.png">
    <img 
        src="../assets/images/tools.png"
        alt="Beyond-UI Exploration Tools"
    >
</a>

<b>Invocation Strategy</b>: mechanisms tools employ to launch any given activity and trigger activation locations, notably:

<ul>
    <li><i>Direct Activity Invocation</i>: sending intents to directly jump start an activity through utilies like ADB. To trigger even non exported activities, tools can modify Manifest  file to expose all activities.</li>
    <li><i>Callback Code Injection</i>: directly invoking callbacks through static or dynamic instrumentation. </li>
    <li><i>Framework Event Generation</i>: customizing the Android OS to inject events at the framework layer, i.e., invoke the same methods within the framework that are triggered by the hardware layer.</li>
    <li><i>Code Extraction</i>: generating a new application containing only one activity and none of the original application entry points, to target a given statement, e.g., startActivity.</li>
</ul>

<b>Navigation Strategy</b>: mechanisms tools employ to navigating past activation guards, given that the enclosing location is triggered. We identify four main implementation paradigms:
    
<ul>
    <li><i>Forced Branching</i>: modifying control flows of a program to steer execution towards a desired point of interest.</li>
    <li><i>Variable Manipulation</i>: manipulating code variables, to ensure execution takes the desired path, by intercepting Android framework APIs and/or arbitrary variables.</li>
    <li><i>Device Manipulation</i>: interacting with configurable and/or stateful aspects of devices without modifying code (e.g., time, location, sensor readings).</li>
    <li><i>Server Simulation</i>: monitoring network traffic to simulate server interactions accurately (in specific use cases).</li>
</ul>

<b>Value Generation Strategy </b> provides inputs necessary for invoking callbacks and activities, and for generating data to steer navigation. We identified three kinds of strategies:

<ul>
    <li><i>Fixed</i>: using random or default/manually-crafted values</li>
    <li><i>Heuristic</i>: integrating app- or domain-specific information (e.g, using natural language processing)</li>
    <li><i>Symbolic</i>: using a constraint solver to generate semantically meaningful values</li>
</ul>

<b> Value Generation Type</b> corresponds to the different types of data that can be generated for a given strategy, notably <i>Generic Primitives</i>, <i>Generic Objects</i> and <i>Specialized</i>.



### Additional Info

We provide additional tool-specific information, notably availability, targeting strategy, invasiveness and date published, in an [Excel sheet](../assets/data/ToolExtraInfo.xlsx).
