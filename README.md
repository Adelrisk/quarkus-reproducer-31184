
# Reproducer for [31184](https://github.com/quarkusio/quarkus/issues/31184)

1. Run service with `quarkus dev`
2. Run command `curl 'http://localhost:8080/hello' -H 'Accept: application/json' -H 'x-requested-with: JavaScript' -v`

The current results:

```
*   Trying 127.0.0.1:8080...
* Connected to localhost (127.0.0.1) port 8080 (#0)
> GET /hello HTTP/1.1
> Host: localhost:8080
> User-Agent: curl/7.87.0
> Accept: application/json
> x-requested-with: JavaScript
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 499 Client Error (499)
< Content-Type: application/json
< WWW-Authenticate: OIDC
< content-length: 0
< 
* Connection #0 to host localhost left intact
```
