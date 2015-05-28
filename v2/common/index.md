---
layout: nav
title: Common - Yoolk REST API Documentation
---

<h1 class="page-header">Hello Developers</h1>
<p class="lead">The second version of the Yoolk API is an exciting step forward towards making it easier for users to have open access to their data.</p>
<p class="lead">Build something great.</p>

<p>In order to access the API, you need to register the api client with yoolk. Every request made to Yoolk REST API must provide `authentication` and `https`. API client must send with `access_token` parameter as query string.</p>

<div class="codehilite">
  <div class="codehilite-body">
{% highlight django%}{% raw %}
https://api.yoolk.com/v2/portals/yp.com.kh?access_token=ACCESS-TOKEN
{% endraw %}{% endhighlight %}
  </div>
</div>
