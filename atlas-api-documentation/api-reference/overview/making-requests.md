# Making requests

## Making requests <a href="#overview" id="overview"></a>

Here are the building blocks to set up your first request.

### Authentication <a href="#authentication" id="authentication"></a>

Atlas will provide you <mark style="color:green;">x-atlas-client-id</mark> and <mark style="color:green;">x-atlas-client-secret</mark> before you start development.

Send them in the request header.

```
x-atlas-client-id ： <Your clientid>
x-atlas-client-secret : <Your client secretid>
```

### MIME types <a href="#mime-types" id="mime-types"></a>

All request bodies sent to the API should be in JSON format. A `Content-Type` header is required whenever you're sending a request body (i.e. for `POST` and `PUT` requests):

```
Content-Type: application/json
```

### Compression <a href="#compression" id="compression"></a>

We recommend enabling compression for responses returned by the API, since they can be very large. To enable compression, send an `Accept-Encoding` header:

```
Accept-Encoding: gzip
```

You'll need to configure your HTTP client to decompress responses. Most clients will have this functionality built-in.
