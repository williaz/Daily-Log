- [x] [upload timeout](https://tomcat.apache.org/tomcat-8.5-doc/config/http.html)
- server.xml
  - connectionUploadTimeout
  - disableUploadTimeout="false"

- [x] redirect

- ```<Valve className="org.apache.catalina.valves.rewrite.RewriteValve" />```
  - global: context.xml
  - host: server.xml
- conf/Catalina/localhost/rewrite.config
```
RewriteRule ^/pathNode/(\/*)(.*) newUrl/$2 [R,L]
```

- [x] tomcat default dir listing
- web.xml: listings

