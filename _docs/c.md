---
title: C
tags: 
 - c
description: C Vulnerabilities
---

# C

###  Buffer Overflow

<button class="btn btn-danger"></button>




##### 🐞 non-compliance

{% highlight php %}
void copy_string(char* dest, char* src) {
  int i = 0;
  while(src[i] != '\0') {
    dest[i] = src[i];
    i++;
  }
  dest[i] = '\0';
}

int main() {
  char str1[6];
  char str2[10] = "example";
  copy_string(str1, str2);
  printf("%s", str1);
  return 0;
}
{% endhighlight %}



##### ✅ compliance 


{% highlight php %}
void copy_string(char* dest, char* src, size_t dest_size) {
  int i = 0;
  while(src[i] != '\0' && i < dest_size - 1) {
    dest[i] = src[i];
    i++;
  }
  dest[i] = '\0';
}

int main() {
  char str1[6];
  char str2[10] = "example";
  copy_string(str1, str2, sizeof(str1));
  printf("%s", str1);
  return 0;
}
{% endhighlight %}




مطالعه بیشتر:
<a href="#"></a>



