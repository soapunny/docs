# HTML, HTTP API, CSR, SSR
<hr/><br/>

### Static Resource(정적 리소스)
+ Provides fixed HTML files, CSS, JS, images, videos, etc.
+ The files are already created and no complex business logic is needed.
<pre><code>
            request(/hello.html)
Web Browser -------------------> Web Server
            <------------------
            response(
            ~/hello.html,
            ~/hello.css,
            ~/hello.js
            ~/img/hello.jpg)
</code></pre>
<br/>

### Dynamic Resource(동적 리소스)
+ WAS(WebSphere Application Server) dynamically generates the required HTML file and responds.
+ Requested data is dynamically retrieved from the DB, Business logic is needed.

<pre><code>
            request(/orders.html)    SELECT DATA
Web Browser -------------------> WAS -------------------> DB
            <------------------      <------------------
            response(newly created HTML)
</code></pre>
<br/>

### HTTP API
+ Responds with data instead of the HTML page.
+ Usually being used for JSON0 format communication.
+ Called from many different systems(Web client -> Server, App client -> Server, Server -> Server)

<pre><code>
            request(/orders.html)    SELECT DATA
Web Browser -------------------> WAS -------------------> DB
            <------------------      <------------------
            response(DATA, JSON{"order_no":100, "price":50})
</code></pre>
<br/>

### SSR(Server Side Rendering)
+ Server create the final results and response.
+ Usually being used for the static response.
+ JSP, Timeleaf
<br/>

### CSR(Client Side Rendering)
+ Web browser dynamically create the final results using the HTML results.
+ Usually being used for the dynamic response.
+ You can partially change the page.
+ React, Vue.js
<br/>
