---
layout: default
title: Properties
nav_order: 3
description: "Mobile Application Coverage: The 25% Curse and Ways Forward"
permalink: /docs/properties
---

### Selected Activities and Categorization

We systematically study and characterize properties of conditions guarding the execution of 
unreached activities.

From a total 363 unreached activities, we exclude activities classified as <i>Unknown</i>, <i>No caller</i> or <i>Transitive</i>. We obtain a set of 152 activities, over which we extract the detailed breakdown, in terms of <b>Export status</b>, <b>Activation Location</b>, <b>Activation Guards</b>, <b>Parameters</b>, and <b>Execution Dependencies</b>, shown below.
The breakdown is also provided as a downloadable [pdf](../assets/images/full-properties.pdf).



<object data="../assets/images/full-properties.pdf" width="1000" height="1000" type='application/pdf'>
</object>


Additionally, we map the different types of properties we extract to the identified reasons for unreachability, to characterize which patterns are most common depending on the reason for unreachability. 

For example, in the table below, xx% of activities unreached due to missing software properties are activated in GUI/lifecycle callbacks.
