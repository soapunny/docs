<h4>Calculate lines</h4>

<pre><code>$ git ls-files | grep "\(.html\|.css\|.js\|.java\)$" | xargs wc -l
</code></pre>