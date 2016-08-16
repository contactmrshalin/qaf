---
title: Integration
sidebar: qaf_2_1_7b_sidebar
permalink: integration_with_other_tools.html
folder: qaf_2_1_7b
---


Using QAF you can integrate any Test Management Tool to update Test-Result after test execution completed.

1. Create a class which implements `TestCaseResultUpdator` interface.
2. Specify qualified class name in `result.updator` property.
3. Overide methods to implement test management tool specific web service logic


`TestCaseResultUpdator` interface defines following methods.

```java
boolean updateResult(Map<String, ? extends Object> params,TestCaseRunResult result, String details);
String getToolName();
```

Example:

```java
package com.infostretch.automation.integration.example
...

public class ExampleResultUpdator implements TestCaseResultUpdator{

	@Override
	public String getToolName() {
		return "Example";
	}

	/**
	 * @param params
	 *            tescase/scenario meta-data including method parameters if any
	 * @param result
	 *            test case result
	 * @param details
	 *            run details
	 * @return
	 */

	@Override
	public boolean updateResult(Map<String, ? extends Object> params,
			TestCaseRunResult result, String details) {

		// Implement test management tool specific implemeneation/method calls
		
		return true;
	}

}
```
Registering class for Result updator

To register result updator class set property **result.updator**

Property:

```properties
result.updator=com.infostretch.automation.integration.example.ExampleResultUpdator
```
