---
title: "APIs - with 'kubectl proxy'"
permalink: /course/chapter-7/apis-with-kubectl-proxy
---
When `kubectl proxy` is running, we can send requests to the API over the `localhost` on the proxy port 8001 (from another terminal, since the proxy locks the first terminal):

```shell
$ curl http://localhost:8001/
{
 "paths": [
   "/api",
   "/api/v1",
   "/apis",
   "/apis/apps",
   ......
   ......
   "/logs",
   "/metrics",
   "/openapi/v2",
   "/version"
 ]
}
```

With the above `curl` request, we requested all the API endpoints from the API server. Clicking on the link above (in the curl command), it will open the same listing output in a browser tab.

We can explore every single path combination with `curl` or in a browser, such as:

`http://localhost:8001/api/v1`

`http://localhost:8001/apis/apps/v1`

`http://localhost:8001/healthz`

`http://localhost:8001/metrics`