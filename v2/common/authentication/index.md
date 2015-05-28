---
layout: nav
title: Authentication - Yoolk REST API Documentation
---

<h1 class="page-header">Authentication</h1>

<table class="table table-bordered">
  <tr>
    <td class="request-method"><a href="#oauth_token">POST</a></td>
    <td><code>/v2/oauth/token</code></td>
    <td>Returns the access_token for api client</td>
  </tr>
  <tr>
    <td class="request-method"><a href="#token_info">GET</a></td>
    <td><code>/v2/oauth/token/info</code></td>
    <td>Returns the access_token information</td>
  </tr>
</table>

<h2 class="tags" id="oauth_token"><code>POST</code> /v2/oauth/token</h2>

Authenticate api client with `client_id` and `client_secret`. It returns `access_token` back if successful, otherwise returns `401`.

<div class="codehilite">
  <div class="codehilite-header">
    <h4>Request</h4>
  </div>
  <div class="codehilite-body">
{% highlight django%}{% raw %}
https://api.yoolk.com/v2/oauth/token
{% endraw %}{% endhighlight %}
  </div>
  <hr>
  <div class="codehilite-body">
{% highlight json%}{% raw %}
{
  "grant_type": "client_credentials",
  "client_id": "client_uid",
  "client_secret": "client_secret"
}
{% endraw %}{% endhighlight %}
  </div>
</div>

<div class="codehilite">
  <div class="codehilite-header">
    <h4>Response</h4>
  </div>
  <div class="codehilite-body">
{% highlight json%}{% raw %}
{
  "access_token": "ee0acd589332541cf47af24cac0809aa9dbc92854ee7f8af3dc817ed5c76965e",
  "token_type": "bearer",
  "refresh_token":"5374dc43d84c2ff085457abe6dc440ef14259c3ba293fbeaae810e2809f74357",
  "expires_in": 7200
}
{% endraw %}{% endhighlight %}
  </div>
</div>

<h2 class="tags" id="token_info"><code>GET</code> /v2/oauth/token/info</h2>

Return information about `access_token`, otherwise returns `401`.

<div class="codehilite">
  <div class="codehilite-header">
    <h4>Request</h4>
  </div>
  <div class="codehilite-body">
{% highlight django%}{% raw %}
https://api.yoolk.com/v2/oauth/token/info?access_token=b246007424251b119023c6b897f7a3b49f1a1168fec4a75dced6b2b2cd30d82d
{% endraw %}{% endhighlight %}
  </div>
</div>

<div class="codehilite">
  <div class="codehilite-header">
    <h4>Response</h4>
  </div>
  <div class="codehilite-body">
{% highlight json%}{% raw %}
{
  "data": {
    "id": "54414a184368613f6b010000",
    "token": "157e9e6bac8abbdf1ccaeaddf972bdfc7a18662f0abd7ec636a7b374e3daa803",
    "refresh_token": "8d80ecc3e044d008eb27511016768b298409cee26464acf81df76b97d4ee6204",
    "expires_in": 5184000,
    "expired_at": "2014-12-16T16:55:52.263Z",
    "revoked_at": null,
    "account": {
      "id": "543ff13d436861b3f82e0000",
      "email": "chamnap@yoolk.com"
    },
    "application": {
      "id": "543ff19a436861b240000000",
      "name": "Yoolk Office"
    },
    "created_at": "2014-10-17T16:55:52.263Z",
    "updated_at": "2014-10-17T16:55:52.263Z"
  }
}
{% endraw %}{% endhighlight %}
  </div>
</div>