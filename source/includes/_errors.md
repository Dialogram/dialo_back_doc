# Errors

<aside class="notice">
This error section describes the most common error codes you may face while working with the Dialogram API. In a sense of normalization, we used the quite same error codes from routes to routes, despite this back work, you may face error codes that are not in the list. In this case, please refer to the standard http error codes according the RFC 2616.
</aside>

The Dialogram API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- The informations/structure of your request does not permit you to use this route.
403 | Forbidden -- You don't have enough permissions to perform this request.
404 | Not Found -- The specified resource could not be found.
405 | Method Not Allowed -- You tried to perform a request with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The resource requested has been removed from our servers.
418 | I'm a teapot.
429 | Too Many Requests -- You're performing too many requests! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
