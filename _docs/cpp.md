---
title: C++
tags: 
 - cpp
description: C++ Vulnerabilities
---

# C++


###  Null Pointer Dereference


<button class="btn btn-danger"></button>




##### 🐞 non-compliance

{% highlight php %}
void foo(int* ptr) {
    if (ptr != nullptr) {
        *ptr = 42;
    } else {
        // handle error
    }
}

int main() {
    int* ptr = nullptr;
    foo(ptr);
    return 0;
}
{% endhighlight %}



##### ✅ compliance

{% highlight php %}
void foo(int* ptr) {
    if (ptr != nullptr) {
        *ptr = 42;
    } else {
        // handle error
    }
}

int main() {
    int i = 0;
    int* ptr = &i;
    foo(ptr);
    return 0;
}
{% endhighlight %}




مطالعه بیشتر:
<a href="#"></a>

