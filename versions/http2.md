**http/2**

* It's a binary protocol rather than a text protocol. It can't be read and created manually. Despite this hurdle, it allows for the implementation of improved optimization techniques.
* It's a multiplexed protocol. Parallel requests can be made over the same connection, removing the constraints of the HTTP/1.x protocol.
* It compresses headers. As these are often similar among a set of requests, this removes the duplication and overhead of data transmitted.

**key Characteristics**

| Feature               | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| Binary Protocol     | Uses binary framing instead of text, improving performance and reducing errors. |
| Multiplexing        | Multiple requests and responses can be sent over a single TCP connection, eliminating the need for multiple connections. |
| Header Compression| HTTP headers are compressed, reducing overhead and improving performance. |
| Stream Prioritization| Allows the client to prioritize which resources should be fetched first. |
| Server Push       | The server can send resources to the client before they are requested (e.g., CSS files, images). |
| Flow Control        | Manages the speed of data transmission between client and server to avoid congestion. |
| Improved Security   | Built on top of TLS, improving security by default. |
| Less Latency        | Faster page loads due to reduced handshake and multiplexing of requests. |


**Improvements Over HTTP/1.1**


| HTTP/1.1                     | HTTP/2                                              |
|-----------------------------|-----------------------------------------------------|
| Text-based protocol          | Binary-based protocol                               |
| One request per connection   | Multiplexed requests over a single connection       |
| Headers sent uncompressed    | Headers are compressed (HPACK)                      |
| No server push               | Server push enables proactive resource delivery     |
| No prioritization            | Prioritization of resources supported               |


**Limitations**

* The implementation of HTTP/2 is more complex because of the addition of new features like multiplexing, header compression, and stream prioritization.
* TLS introduces additional latency in HTTP/2.
* HTTP/2 also suffers from the Head of Line Blocking problem.
* TCP dependency and strict network situations may lead to interoperability issues.
