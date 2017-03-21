# Daily-Log
Log Daily

- [x] [Error]No compiler is provided in this environment. Perhaps you are running on a JRE rather than a JDK
1. window->preferences, java->Installed JREs, add JDK
2. Installed JREs, Execute Environment, check JDK
3. Maven->update project

## [Cross-domain requests](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS)

XMLHttpRequest (XHR) is an API in the form of an object whose methods transfer data between a web browser and a web server. The object is provided by the browser's JavaScript environment. Particularly, retrieval of data from XHR for the purpose of continually modifying a loaded web page is the underlying concept of Ajax design. 

- [ ] JSONP: type:script
- [ ] AJAX: type: xhr

- [x] X-Requested-With: XMLHttpRequest, no redirection*
Only the following headers are allowed cross domain:

Accept
Accept-Language
Content-Language
Last-Event-ID
Content-Type
any others cause a "pre-flight" request to be issued in CORS supported browsers. -> Server can check

Without CORS it is not possible to add X-Requested-With to a cross domain XHR request.







