---
layout: default
title: Reasons for Unreachability
nav_order: 4
description: "Mobile Application Coverage: The 25% Curse and Ways Forward"
permalink: /docs/analysis
---

### Categorization of Reasons for Unreachability (RQ2)


The detailed breakdown of manually extracted reasons for unreachability is also provided as an [Excel sheet](../assets/data/ManualAppAnalysis.xlsx). 

For each application under study, we grey out activities that are reached manually, and for each unreached activity, we mark the reasons leading to unreachability as described in the paper, i.e., Device (Software properties and Hardware properties), Server, Environment, External resources (Equipment and Information), Usage patterns, Alternate entry, Disabled (For app version and For all end-users), Error handling, No caller and Unknown.

### Categorization of Properties (RQ3)

We systematically study and characterize properties of conditions guarding the execution of 
unreached activities.

From a total 363 unreached activities, we exclude activities classified as <i>Unknown</i>, <i>No caller</i> or <i>Transitive</i>. We obtain a set of 152 activities, from which we extract a detailed breakdown in terms of <b>Export status</b>, <b>Activation Location</b>, <b>Activation Guards</b>, <b>Parameters</b>, and <b>Execution Dependencies</b>.
The breakdown is provided as an [excel sheet](../assets/data/ActivityProperties.xlsx) and a downloadable [pdf](../assets/images/full-properties.pdf).
<!--object data="../assets/images/full-properties.pdf" width="1000" height="1000" type='application/pdf'>
</object-->
<!--Additionally, we map the different types of properties we extract to the identified reasons for unreachability, to characterize which patterns are most common depending on the reason for unreachability. 
For example, in the table below, xx% of activities unreached due to missing software properties are activated in GUI/lifecycle callbacks.
-->