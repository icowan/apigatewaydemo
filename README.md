### Consul 

We will use `consul` for service discovery. To install it, follow the official docs 
[here](https://www.consul.io/intro/getting-started/install.html) and then start the
agent in dev mode:


```
$consul agent -dev
.. 
...
```
### Start the web application

Our Python web application relies on `flask` and `consulate`, so you will need those installed
before you can run it and register itself with `consul`. Using a virtual environment is recommended:

```
$ virtualenv python-web-app
$ . ./python-web-app/bin/activate
$ cd webap-1
$ pip install requirements.txt
$ python app.py

### Start the gRPC service


The above services will register themselves with `consul` by speaking to the agent we
are running above.

### Start the API gateway



### Make requests

### API Gateway Features


#### Auth header missing:

```bash
$ http POST 127.0.0.1:8000/projects/ title=MyProejct Auth-Header-V:121
HTTP/1.1 400 Bad Request
Content-Length: 31
Content-Type: text/plain; charset=utf-8
Date: Tue, 15 Nov 2016 02:50:19 GMT
X-Content-Type-Options: nosniff

Decode: Auth-Header-V1 missing
```

#### Rate limiting example response:

```
$ http POST 127.0.0.1:8000/projects/ title=MyProejct Auth-Header-V1:121
HTTP/1.1 503 Service Unavailable
Content-Length: 24
Content-Type: text/plain; charset=utf-8
Date: Tue, 15 Nov 2016 02:49:39 GMT
X-Content-Type-Options: nosniff

Do: rate limit exceeded

```

### Project creation

```bash
$ http POST 127.0.0.1:8000/projects/ title=MyProejct Auth-Header-V1:121
HTTP/1.1 200 OK
Content-Length: 31
Content-Type: application/json; charset=utf-8
Date: Tue, 15 Nov 2016 02:48:52 GMT

{
    "id": 123,
    "url": "Project-123"
}
```


### Verification service:


```bash
$ http GET 127.0.0.1:8000/verify/ id:=1233 token=vasds Auth-Header-V1:121
HTTP/1.1 200 OK
Content-Length: 40
Content-Type: application/json; charset=utf-8
Date: Tue, 15 Nov 2016 02:47:21 GMT

{
    "Err": null,
    "Message": "Verified: 1233"
}

```

### Resources

- https://peter.bourgon.org/applied-go-kit/#28


