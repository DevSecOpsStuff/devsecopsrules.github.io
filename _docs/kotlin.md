---
title: Kotlin
tags: 
 - kotlin
description: Kotlin Vulnerabilities
---

# Kotlin




###  XML External Entity (XXE)


<button class="btn btn-danger"></button>




##### 🐞 non-compliance


{% highlight php %}
// Noncompliant code
fun processInput(input: String) {
    println("Processing input: $input")
    // Process the input without any validation or sanitization
}
{% endhighlight %}




##### ✅ compliance


{% highlight php %}
// Compliant code
fun processInput(input: String) {
    val sanitizedInput = input.filter { it.isLetterOrDigit() }
    println("Processing input: $sanitizedInput")
    // Process the sanitized input
}
{% endhighlight %}
