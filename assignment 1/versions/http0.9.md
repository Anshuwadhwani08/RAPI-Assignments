**http 0.9**

    It was extremely simple, supporting only the HTTP GET method. Only HTML files were included in HTTP responses, there were no HTTP headers, and there were no HTTP status codes.

    Requests consisted of a single line and started with the only possible method GET followed by the path to the resource.
    ex : GET /my-page.html
    
    Response : 
    <html>
      An text-only web page
   </html>
   

 **Key Characteristics**


| Feature           | Description                                           |
|-------------------|-------------------------------------------------------|
| **Method**        | Only **GET** supported                                |
| **Protocol Version** | No versioning (no HTTP/1.1, etc.)                  |
| **Headers**       | Not supported                                         |
| **Request Format**| `GET /path/to/resource`                               |
| **Response**      | Plain HTML content (no metadata, status codes)        | 
| **Connection**    | Closed after the response is sent                     |
| **Content Types** | Only plain text/HTML (no images, CSS, etc.)          |
	

**Limitations**

* **Only Supports GET Method** : HTTP/0.9 allowed only the GET method to retrieve documents. No support for other methods like POST, PUT, or DELETE.
* **No HTTP Headers** : Requests and responses did not include headers. This made it impossible to specify things like content type, caching rules, or client capabilities.
* **Only Plain HTML Documents** :  Could only fetch plain HTML files. No support for other media types like images, CSS, JavaScript, or videos.
* **No Status Codes** : The server did not return any status code (e.g., 404, 200 OK). The client had no way to know if the request failed or succeeded, except by the content.
* **No Persistent Connections** : A new connection had to be opened for each request. This led to inefficiencies and increased latency.
* **No Support for Hostnames** : HTTP/0.9 could not handle virtual hosting (multiple websites on the same IP address). This became a limitation as websites started sharing servers.