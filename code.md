---
layout: page
title: "Code"
---
<div class="code-snippet">
{% highlight python %}
print("Hello world")
{% endhighlight %}
<button class="copy-btn">Copy to Clipboard</button>
</div>

function copyToClipboard(str) {
  const el = document.createElement('textarea');
  el.value = str;
  el.setAttribute('readonly', '');
  el.style.position = 'absolute';
  el.style.left = '-9999px';
  document.body.appendChild(el);
  const selected =
    document.getSelection().rangeCount > 0
      ? document.getSelection().getRangeAt(0)
      : false;
  el.select();
  document.execCommand('copy');
  document.body.removeChild(el);
  if (selected) {
    document.getSelection().removeAllRanges();
    document.getSelection().addRange(selected);
  }
}

// Add click event listener to copy button
const copyBtns = document.querySelectorAll('.copy-btn');
copyBtns.forEach((btn) => {
  btn.addEventListener('click', (event) => {
    const codeSnippet = event.target.parentNode.querySelector('.highlight');
    copyToClipboard(codeSnippet.innerText);
  });
});
