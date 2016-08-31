---
title: BDD Custom Step Definition
sidebar: qaf_2_1_8_sidebar
permalink: qaf-2.1.8/BDD_Custom_Step_Definition.html
folder: qaf_2_1_8
tags: [bdd,scenario]
---

Steps can be defined in bdl

The Basic Step definition is following. 
 
```
STEP-DEF:<meaningfull step description>
 
    [Keyword] <first step description with parameters>
 
    …
 
    [Keyword] <nth step description>
 
END
```

While execution make sure required bdl files are mentioned in step.provider.pkg property as below

```properties
step.provider.pkg=com.test;scenarios
```
