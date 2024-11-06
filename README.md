# HTTP Status Codes

This document provides a full list of HTTP status codes. Each code includes an explanation and a use case for better understanding.

---

## Table of Contents
1. [Informational Responses (100–199)](#informational-responses-100-199)
2. [Successful Responses (200–299)](#successful-responses-200-299)
3. [Redirection Messages (300–399)](#redirection-messages-300-399)
4. [Client Error Responses (400–499)](#client-error-responses-400-499)
5. [Server Error Responses (500–599)](#server-error-responses-500-599)

---

## 1. Informational Responses (100–199)

### 100 Continue
- **Description**: Indicates that the initial part of a request has been received and the client can continue.
- **Example**: Client uploads a large file and receives `100 Continue`, signaling it to send the remaining data.

### 101 Switching Protocols
- **Description**: Server is switching protocols as requested by the client.
- **Example**: A client requests an upgrade from HTTP to WebSocket for real-time communication.

### 102 Processing (WebDAV)
- **Description**: Server is processing a WebDAV request but has not completed it.
- **Example**: Complex WebDAV request for a file search receives `102 Processing` to avoid timeouts.

### 103 Early Hints
- **Description**: Used to pre-load resources before the final response is ready.
- **Example**: Server sends `103 Early Hints` to preload CSS and images for a page.

---

## 2. Successful Responses (200–299)

### 200 OK
- **Description**: Request was successful, and the response contains the requested data.
- **Example**: A browser loads a webpage or an API fetch request returns successfully.

### 201 Created
- **Description**: Resource was successfully created.
- **Example**: A new user account created after form submission.

### 202 Accepted
- **Description**: Request accepted for processing, but not yet completed.
- **Example**: Report generation request in a system that processes it in the background.

### 203 Non-Authoritative Information
- **Description**: Request successful, but response is from a cached or third-party source.
- **Example**: Proxy server returns cached content without directly fetching the latest data.

### 204 No Content
- **Description**: Request was successful but there is no content to return.
- **Example**: User updates profile settings, and the server acknowledges without additional data.

### 205 Reset Content
- **Description**: Client should reset the view.
- **Example**: After submitting data, a form resets for new entries.

### 206 Partial Content
- **Description**: Partial response for a range request.
- **Example**: Resuming a paused video or file download from a specific byte range.

### 207 Multi-Status (WebDAV)
- **Description**: Conveys multiple status codes for multiple independent operations.
- **Example**: WebDAV requests return multiple statuses for each sub-operation on files.

### 208 Already Reported (WebDAV)
- **Description**: Used to avoid reporting the same resource multiple times.
- **Example**: WebDAV responses that include previously processed elements.

### 226 IM Used
- **Description**: Server fulfilled a GET request with the instance manipulations applied.
- **Example**: A response indicating a resource has been manipulated (e.g., compressed) before delivery.

---

## 3. Redirection Messages (300–399)

### 300 Multiple Choices
- **Description**: Indicates multiple options for the resource.
- **Example**: User can choose between multiple file formats or language versions.

### 301 Moved Permanently
- **Description**: Resource has a new permanent URL.
- **Example**: Permanently moved page, updating search engines and bookmarks.

### 302 Found
- **Description**: Temporary redirect to another resource.
- **Example**: Redirect to a login page from a protected resource.

### 303 See Other
- **Description**: Redirects to a different resource using GET.
- **Example**: Redirect to a receipt page after submitting a purchase order.

### 304 Not Modified
- **Description**: Indicates cached content is up to date.
- **Example**: Browser cache check for an image returns `304` if unchanged.

### 305 Use Proxy (Deprecated)
- **Description**: Requested resource must be accessed through a proxy.
- **Example**: Deprecated in HTTP/1.1 due to security concerns.

### 306 (Unused)
- **Description**: Previously reserved, but not used.

### 307 Temporary Redirect
- **Description**: Similar to `302` but method remains the same.
- **Example**: Temporarily redirects a POST request without changing method.

### 308 Permanent Redirect
- **Description**: Similar to `301` but method remains the same.
- **Example**: API endpoint moved permanently; clients should update the URI.

---

## 4. Client Error Responses (400–499)

### 400 Bad Request
- **Description**: The server could not understand the request.
- **Example**: Malformed JSON payload in an API request.

### 401 Unauthorized
- **Description**: Authentication is required but missing or invalid.
- **Example**: API request without a valid authentication token.

### 402 Payment Required (Experimental)
- **Description**: Reserved for future use regarding digital payment.
- **Example**: Possible future status for subscription services.

### 403 Forbidden
- **Description**: Client has no access rights to the content.
- **Example**: Unauthorized user attempts access to an admin-only page.

### 404 Not Found
- **Description**: Server cannot find the requested resource.
- **Example**: Request for a non-existent webpage.

### 405 Method Not Allowed
- **Description**: HTTP method is not allowed for the requested resource.
- **Example**: DELETE request to a read-only endpoint.

### 406 Not Acceptable
- **Description**: Content does not match client’s Accept headers.
- **Example**: Client requests XML, but only JSON is available.

### 407 Proxy Authentication Required
- **Description**: Proxy authentication required.
- **Example**: Request through a corporate proxy without credentials.

### 408 Request Timeout
- **Description**: Server timed out waiting for the request.
- **Example**: Slow internet connection causes a timeout.

### 409 Conflict
- **Description**: Request conflicts with server state.
- **Example**: Concurrent updates to a document in a collaborative app.

### 410 Gone
- **Description**: Resource permanently removed.
- **Example**: Deprecated API endpoint.

### 411 Length Required
- **Description**: Content-Length header is missing.
- **Example**: POST request without specifying content length.

### 412 Precondition Failed
- **Description**: Preconditions in headers not met.
- **Example**: Conditional update request fails due to modified data.

### 413 Payload Too Large
- **Description**: Payload exceeds server limits.
- **Example**: File upload exceeds max upload size.

### 414 URI Too Long
- **Description**: URI is too long for the server to process.
- **Example**: Too many parameters in a GET request.

### 415 Unsupported Media Type
- **Description**: Unsupported content format.
- **Example**: Server receives an unsupported media type, such as `.exe` for an image upload.

### 416 Range Not Satisfiable
- **Description**: Requested range not available.
- **Example**: Requesting a range beyond file length.

### 417 Expectation Failed
- **Description**: Expectation in headers cannot be met.
- **Example**: Server fails to meet `Expect: 100-continue` header.

### 418 I'm a Teapot (RFC 2324)
- **Description**: April Fools' joke status code.
- **Example**: For fun, returned by a teapot API as a joke.

### 421 Misdirected Request
- **Description**: Request was directed to a server that cannot respond.
- **Example**: Server configuration issue causing requests to be misdirected.

### 422 Unprocessable Entity (WebDAV)
- **Description**: Request is well-formed but has semantic errors.
- **Example**: Valid JSON payload with invalid data.

### 423 Locked (WebDAV)
- **Description**: Resource is locked.
- **Example**: Editing a locked document returns `423 Locked`.

### 424 Failed Dependency (WebDAV)
- **Description**: Failed due to dependency on another action.
- **Example**: Chained requests where one fails, causing others to fail.

### 425 Too Early
- **Description**: Indicates request might be replayed.
- **Example**: When using `Early Data` in HTTP/2 connections.

### 426 Upgrade Required
- **Description**: Client should upgrade to a different protocol.
- **Example**: Server requires client to upgrade to HTTP/2.

### 428 Precondition Required
- **Description**: Requires conditions to prevent conflicts.
- **Example**: PUT request that includes conditional headers.

### 429 Too Many Requests
- **Description**: Rate limit exceeded.
- **Example**: Frequent API calls triggering rate limits.

### 431 Request Header Fields Too Large
- **Description**: Headers too large for the server.
- **Example**: Long headers like cookies exceeding limits.

### 451 Unavailable For Legal

 Reasons
- **Description**: Resource restricted for legal reasons.
- **Example**: Content blocked due to a court order.

---

## 5. Server Error Responses (500–599)

### 500 Internal Server Error
- **Description**: General server error.
- **Example**: Server fails unexpectedly due to a misconfiguration.

### 501 Not Implemented
- **Description**: Request method not supported.
- **Example**: Server doesn’t support PATCH requests.

### 502 Bad Gateway
- **Description**: Server received invalid response from upstream.
- **Example**: Proxy server cannot reach backend server.

### 503 Service Unavailable
- **Description**: Server is overloaded or under maintenance.
- **Example**: Site under maintenance returns `503`.

### 504 Gateway Timeout
- **Description**: Gateway timed out waiting for a response.
- **Example**: Proxy fails due to slow backend.

### 505 HTTP Version Not Supported
- **Description**: HTTP version is not supported by the server.
- **Example**: Server rejects requests using outdated HTTP versions.

### 506 Variant Also Negotiates
- **Description**: Circular content negotiation detected.
- **Example**: Negotiation logic loop.

### 507 Insufficient Storage (WebDAV)
- **Description**: Not enough storage for request.
- **Example**: Server unable to upload file due to storage limits.

### 508 Loop Detected (WebDAV)
- **Description**: Infinite loop detected during processing.
- **Example**: Server detects recursion in resource.

### 510 Not Extended
- **Description**: Further extensions required.
- **Example**: Client needs to extend request with additional requirements.

### 511 Network Authentication Required
- **Description**: Client must authenticate to access the network.
- **Example**: Hotel Wi-Fi redirecting to login page.

---

Each status code is essential for efficient HTTP communication. By understanding these codes, developers can better handle responses and errors, enhancing application robustness and reliability.
