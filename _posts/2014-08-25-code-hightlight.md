---
layout: default
title: 代码高亮extensions
---

一个比较好玩的代码高亮插件liquid-extensions，其效果如下： 
[More details](https://github.com/mojombo/jekyll/wiki/liquid-extensions)


This is regular text


<pre class="prettyprint" id="bash">
#!/bin/bash
# Fibonacci numbers
# Writes an infinite series to stdout, one entry per line
function fib() {
  local a=1
  local b=1
  while true ; do
    echo $a
    local tmp=$a
    a=$(( $a + $b ))
    b=$tmp
  done
}

# output the 10th element of the series and halt
fib | head -10 | tail -1
</pre>



