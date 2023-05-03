---
layout: page
title: "Code"
---
<script src="{{ '/assets/copy_snippet.js' | relative_url }}"></script>

#<div class="code-snippet">
 # {% highlight {{ include.python | default: "text" }} %}
 # {{ print("Hello world") }}
 # {% endhighlight %}
 # <button class="copy-btn">Copy to Clipboard</button>
#</div>

{% include code_snippet.html code="print("Hello world")" language="python" %}
