---
layout: page
title: "Code"
---
<div class="code-snippet">
  {% highlight {{ include.python | default: "text" }} %}
  {{ print("Hello world") }}
  {% endhighlight %}
  <button class="copy-btn">Copy to Clipboard</button>
</div>
