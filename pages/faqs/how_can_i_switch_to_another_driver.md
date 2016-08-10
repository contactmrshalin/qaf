---
title: How can I switch to another driver during same testcase execution.
sidebar: faq_sidebar
permalink: how_can_i_switch_to_another_driver.html
folder: qaf_2_1_7b
---

In some exceptional changes, it may be required to change the driver.

To change the desired capabilities during test execution, you need to call the setup method of WebDriverTestBase class as below.

**For example** if you want to switch to appiumDriver while executing on any other driver, call the following steps.

```java
String[] desiredCaps =
            STBArgs.base_url.set( "http://localhost:4723/wd/hub",
                            STBArgs.port.set("4723",STBArgs.browser_str.set("appiumDriver")));
new WebDriverTestBase().setUp(null, desiredCaps);
```			

 
