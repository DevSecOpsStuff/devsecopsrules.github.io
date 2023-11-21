---
title: Objective-C
tags: 
 - objective-c
description: Objective-C Vulnerabilities
---

# Objective-C




##  XML External Entity (XXE)



##### 🐞 non-compliance


{% highlight php %}
// Noncompliant code
NSString *input = [request parameterForKey:@"input"];
NSLog(@"Processing input: %@", input);
// Process the input without any validation or sanitization
{% endhighlight %}




##### ✅ compliance 


{% highlight php %}
// Compliant code
NSString *input = [request parameterForKey:@"input"];
NSCharacterSet *allowedCharacterSet = [NSCharacterSet alphanumericCharacterSet];
NSString *sanitizedInput = [[input componentsSeparatedByCharactersInSet:[allowedCharacterSet invertedSet]] componentsJoinedByString:@""];
NSLog(@"Processing input: %@", sanitizedInput);
// Process the sanitized input
{% endhighlight %}


