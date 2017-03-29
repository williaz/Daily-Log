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

- [ ] localhost VS real ip

When you access localhost, your /etc/hosts file will tell your computer not to look any further and redirects you to your own computer. When you access the local IP adress, your computer will ask the router to fetch the data, and your router will then point back to your computer.

- [x] JS new line
\<br> VS \n

- [x] specify the order of execution of test methods. JUnit 4.11
@FixMethodOrder(MethodSorters.NAME_ASCENDING)

- [x] [Aggregating tests in suites](https://github.com/junit-team/junit4/wiki/aggregating-tests-in-suites)
@RunWith(Suite.class)
@Suite.SuiteClasses({..class, ..})








