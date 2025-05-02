**http 1.1**

HTTP/1.1  introduced numerous improvements:
 * The introduction of persistent connections, which allowed multiple requests and responses to be sent over a single connection. This approach reduced the overhead of establishing a new connection for each request and improved the overall performance of HTTP.
 * Pipelining was added. This allowed a second request to be sent before the answer to the first one was fully transmitted. This lowered the latency of the communication.
 * Chunked responses were also supported.
 * Additional cache control mechanisms were introduced.
 * Content negotiation, including language, encoding, and type, was introduced. A client and a server could now agree on which content to exchange.
 * Due to the Host header, the ability to host different domains from the same IP address enable virtual hosting.

**Request**

    GET /about HTTP/1.1
    Host: www.mywebsite.com
    User-Agent: Chrome/120.0 (Windows 10)
    Accept: text/html
    Accept-Language: en-US
    Accept-Encoding: gzip
    Connection: keep-alive

**Response**

    HTTP/1.1 200 OK
    Date: Tue, 15 Apr 2025 10:00:00 GMT
    Server: Apache/2.4
    Content-Type: text/html; charset=UTF-8
    Content-Encoding: gzip
    Content-Length: 1536
    Connection: keep-alive
    Keep-Alive: timeout=5, max=100
    Cache-Control: no-cache
    Transfer-Encoding: chunked

    (compressed HTML page content)

**Key Characteristics**

| Feature               | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Methods**            | GET, POST, HEAD, PUT, DELETE, OPTIONS, TRACE                                |
| **Persistent Connections** | Default behavior using `Connection: keep-alive` to reuse TCP connections     |
| **Pipelining**         | Allows sending multiple requests before receiving responses (not widely used due to head-of-line blocking) |
| **Host Header**        | Required to support multiple domains on one IP (virtual hosting)             |
| **Chunked Transfer**   | Enables dynamic content delivery without knowing content length              |
| **Caching**            | Improved control with headers like `Cache-Control`, `ETag`, and `If-Modified-Since` |
| **Content Negotiation**| Client and server can negotiate language, encoding, type (`Accept-*` headers)|
| **Status Codes**       | More detailed, including `100 Continue`, `409 Conflict`, `410 Gone`, etc.    |


**Limitations**

 * Head-of-Line Blocking: Even though pipelining is supported, one slow request blocks all following responses on the same connection.
 * Multiple Connections Needed: Browsers open multiple TCP connections (usually 6 per domain) to improve performance, leading  to network congestion.
 * No Built-in Multiplexing: Can’t send multiple responses at once over the same connection — only one at a time.
 * Latency Issues: Repeated TCP and TLS handshakes increase delay, especially on slow networks.
 * Inefficient Use of Network: Overhead due to repetitive headers sent in each request.
 * Limited Compression: Header compression is not built-in, resulting in larger request/response sizes.
