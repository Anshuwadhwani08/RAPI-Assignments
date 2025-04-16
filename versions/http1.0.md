**http 1.0**

After the original version was released, the functionality was extended in HTTP/1.0
  * Versioning information was sent within each request. This is required to inform the server as to what version of the protocol will be used for the transmission.  
  * the methods were expanded to include HEAD and POST. POST allowed clients to send data to the server, enabling two-way communication, while GET was used for one-way data retrieval.
  *  HTTP status codes were sent at the beginning of a response to indicate success and failure.
  *  Documents other than plain HTML files could be transmitted using content-type header.
  *  The concept of HTTP headers was introduced for both requests and responses. Metadata could be transmitted and the protocol became extremely flexible and extensible.
  

**Initial request**

    GET /index.html HTTP/1.0
    User-Agent: NCSA_Mosaic/2.0 (Windows 3.1)

**Response**

    200 OK
    Date: Sun, 01 Jan 1995 12:01:00 GMT
    Server: CERN/3.0 libwww/2.17
    Content-Type: text/html

    <html>
    Welcome to the <img src="/logo.gif"> example.re homepage!
    </html>

**Second connection request (to fetch the image)**

    GET /logo.gif HTTP/1.0
    User-Agent: NCSA_Mosaic/2.0 (Windows 3.1)

**Response**

    200 OK
    Date: Sun, 01 Jan 1995 12:01:01 GMT
    Server: CERN/3.0 libwww/2.17
    Content-Type: text/gif

<Encoded data of logo.gif>


**Key Charachteristics**



| Feature          | Description                                                |
|------------------|------------------------------------------------------------|
| **Methods**      | GET, POST (added)                                          |
| **Protocol Version** | HTTP/1.0                                               |
| **Headers**      | Support for headers like `Content-Type`, `Content-Length`   |
| **Status Codes** | Introduced (e.g., 200 OK, 404 Not Found)                   |
| **Request Format** | `GET /path/to/resource HTTP/1.0`                          |
| **Response Format** | Includes status codes and headers like `Content-Type`    |
| **Connection**   | Close after each request/response cycle                    |
| **Content Types**| More than just plain HTML (text, images, etc.)             |


**Limitations**

 * **Connection Handling**: A new connection is created for each request/response cycle, leading to higher latency and resource usage.
 * **No Persistent Connections**: Even with multiple requests from the same client to the same server, each request would need a new connection. leading to slow performance and inefficient use of resources.
 * **Limited Efficiency**: No support for multiplexing multiple requests on a single connection.

**Evolution to HTTP/1.1**
 * **Persistent Connections**: This was introduced in HTTP/1.1 to allow multiple requests and responses over a single connection.
 * **Additional Headers**: HTTP/1.0 laid the foundation for more complex headers, but HTTP/1.1 further improved its flexibility.

