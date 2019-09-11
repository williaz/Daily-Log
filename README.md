# Daily-Log
*Log Daily*
*Eye Friendly: Hex: #dfc7b2, RGB: (223,199,178)*
- [x] [Error]No compiler is provided in this environment. Perhaps you are running on a JRE rather than a JDK

1. window->preferences, java->Installed JREs, add JDK
2. Installed JREs, Execute Environment, check JDK
3. Maven->update project

## [Cross-domain requests](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS)

- XMLHttpRequest (XHR) is an API in the form of an object whose methods transfer data between a web browser and a web server. The object is provided by the browser's JavaScript environment. Particularly, retrieval of data from XHR for the purpose of continually modifying a loaded web page is the underlying concept of Ajax design. 

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

- Without CORS it is not possible to add X-Requested-With to a cross domain XHR request.

- [ ] localhost VS real ip

- When you access localhost, your /etc/hosts file will tell your computer not to look any further and redirects you to your own computer. When you access the local IP adress, your computer will ask the router to fetch the data, and your router will then point back to your computer.

- [x] JS new line
- \<br> VS \n

- [x] specify the order of execution of test methods. JUnit 4.11

- @FixMethodOrder(MethodSorters.NAME_ASCENDING)

- [x] [Aggregating tests in suites](https://github.com/junit-team/junit4/wiki/aggregating-tests-in-suites)

- @RunWith(Suite.class)
- @Suite.SuiteClasses({..class, ..})

- [x] [deserialize an array of objects in JSON](http://stackoverflow.com/questions/6349421/how-to-use-jackson-to-deserialise-an-array-of-objects)
```java
import com.fasterxml.jackson.databind.ObjectMapper;

ObjectMapper mapper = new ObjectMapper();
MyClass[] myObjects = mapper.readValue(json, MyClass[].class);
```
- [x] too deep nesting of component structure causes cellediting doesn't work properly -> override?
- forms, trees, tab panels and grids all extend from Panel,

- [x] Uncaught Error: [Ext.createByAlias] Unrecognized alias: plugin.ux-progressbarpager
- change the "requires" config to class level

- [x] render icon in cell
- as renderer returns HTML string, may need escape \\": 
```javascript
return '<i class="fa fa-compass"></i>';
```
- [x] check oracle DB version
```sql
SELECT * FROM v$version; -- DB component info
```
- [x] check DB size
```sql
SELECT sum(bytes)/1024/1024/1024 size_gb FROM SYS.DBA_DATA_FILES;
```
- [x] loop Map in JS
- for of (not support)
```javascript
//#1. for of, if support
var myMap = new Map();
myMap.set('0', 'foo');
myMap.set(1, 'bar');
myMap.set({}, 'baz');

for(var [key, value] of myMap) {
    console.log("key: " + key + " value: " + value); 
}

//#2. using entries()
var myMap = new Map();
myMap.set('0', 'foo');
myMap.set(1, 'bar');
myMap.set({}, 'baz');

var mapIter = myMap.entries();
var temp = mapIter.next();

while (temp.value != null) {
    console.log("key: " + temp.value[0] + " value: " + temp.value[1]); 
    temp = mapIter.next();
}

//#3. keys()
var myMap = new Map();
myMap.set('0', 'foo');
myMap.set(1, 'bar');
myMap.set({}, 'baz');

var mapIter = myMap.keys();
var temp = mapIter.next();

while (temp.value != null) {
    console.log("key: " + temp.value + " value: " + myMap.get(temp.value)); 
    temp = mapIter.next();
}
```
- [x] ExtJs6 Layout helper
```javascript
    border: 2,
    style: {
       borderColor: 'black',
       borderStyle: 'solid'
    },
```
- [x] ExtJs6 Store helper
```javascript
    store.each(function (record) {
        console.log(record.data);
    });
```
- [x] JS object prop inspector
```js
  //var obj = 
  var result = '';
  for (var i in obj) {   
    if (obj.hasOwnProperty(i)) {
      result += 'obj.' + i + ' = ' + obj[i] + '\n';
    }
  }
  console.log('Obj props:\n' + result);
```

- [x] JS check type to avoid === doesn't work
```js
typeof 37 === 'number';
typeof NaN === 'number'; 
typeof '' === 'string';
typeof false === 'boolean';
typeof [1, 2, 4] === 'object'; //use Array.isArray
typeof undefined === 'undefined';
typeof null === 'object';
```

## [Analyze Data with Graphs](http://blog.plot.ly/post/118355223592/how-to-analyze-data-eight-useful-ways-you-can)
### 1. Bar Chart
- Bar charts compare values between discrete categories(countable)
- If the data has more than one value per category, a stacked or grouped bar chart lets you see individual values and compare across categories.
- Grouped bar for clear individual values; Stacked bar for comparing the sum of each group

### 2. Line Chart
- x-axis display continuous data
- emphaisze the overall trend or pattern of the data
- break down into certain group
- Line charts excel over bar when the changes are more subtle or vary a lot over time.

### 3. Area Chart
- an effective way of drawing attention to the magnitude of difference between traces, or the cumulative value over a period of time. 
- However, it can be confusing if there are many overlapping traces. 
- A stacked area graph adds each trace on top of the last one, such that the areas will never overlap. 

### 4. Scatter Plot
- show the relationship between two variables.
- x-axis: independent; y: dependent
- the line of best fit, R^2 [0, 1] measuress how closely the line fits the data. 1 for perfect correlation

### 5. Bubble Chart
- A bubble chart is a scatter plot that includes a third variable. This third variable is represented as the size of the data point, creating the bubble.

### 6. Histogram
- It is visually similar to a bar chart, but with a histogram the bars touch to emphasize that the ranges are continuous data. 
- A histogram really shines when there is either very little or a lot of variation in the data. It will clearly show multimodal or uniform distribution.

### 7. Box plot
- A box plot indicates distribution by dividing data into quartiles. 
- A box plot is ideal for comparing the distribution of a series of datasets
- It is often used to track different trials of an experiment that is run many times.

### 8. Combination Chart

### *[How to select the best Excel charts for data analysis and reporting](https://www.optimizesmart.com/how-to-select-best-excel-charts-for-your-data-analysis-reporting/)*

- [x] [Multi-fields Filter](http://existdissolve.com/2011/11/extjs-4-filtering-on-multiple-fields/)
```javascript
var searchfilter = new Ext.util.Filter({
     filterFn: function(record){
         var searchtest,fnmatch,mnmatch,lnmatch;
         var escapere = Ext.String.escapeRegex;        //Escapes the passed string for use in a regular expression.
         searchtest = new RegExp(escapere(text), 'i');  //text as the input, The "i" flag indicates that case should be ignored while attempting a match in a string.
         
         fnmatch = searchtest.test(record.data.firstname);
         mnmatch = searchtest.test(record.data.middlename);
         lnmatch = searchtest.test(record.data.lastname);
         // if any of the fields matched, return true, which will include  record in filtered set
         if(fnmatch || mnmatch || lnmatch) return true;
         // otherwise, return false, which will exclude record from filtered set
         else return false;
    }
})
```
- [ ] [CSS Selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)

- [x] deploy WAR on Tomcat
```bash
$ bash
$ cd app/tomcat/bin
(servers/tomcat/bin)$ ./shutdown.sh
(servers/tomcat/bin)$ cd ../webapps
(servers/tomcat/webapps)$ rm -rf app(folder)
(servers/tomcat/webapps)$ mv /fd/*.war .
(servers/tomcat/webapps)$ cd ../bin
(servers/tomcat/bin)$ ./startup.sh
```
- [x] SVN tag
- A tag is just a “snapshot” like any repo revision after each commit.
- tag VS branch: tag-a snapshot for certain time, no continuous commit; branch get committing
- ```Team -> Branch/Tag...```

- [ ] Extjs 6, form.submit(), backend server enabled CORS, still get below response from failure calback, even though server sent back a success response
```json
{success:false,message:"Blocked a frame with origin "http://localhost:8080" from accessing a cross-origin frame."}
```
- It seems ExtJs uses different iframes, and brower throw the CO errer. 
- Possible solution: document.domain = document.domain;(not sure)

- [x][oracle- difference bw " and '](https://community.oracle.com/thread/978489)
- do not use "" in DB
- Single-quotes are used to enclose string literals, DATE literals.
- Double-quotes are used to enclose identifiers (like table and column names) . They are optional (and therefore almost never used) when the name conforms to certain rules for names (starts with a letter, no spaces or special symbols, no lower-case letters, ...).

- [x] [ORACLE - SEQUENCE gaps](https://asktom.oracle.com/pls/apex/f?p=100:11:0::::P11_QUESTION_ID:369390500346406705)
- because of cache
- SEQUENCE is for generating unique number only, gaps are normal and fine

- [x] Linux - Kill the process
```bash
ss -ltnp | grep [port]
kill [PID]
```
- [x] Spring Boot - [add application level endpoint](https://stackoverflow.com/questions/28006501/how-to-specify-prefix-for-all-controllers-in-spring-boot)
- 1. ServletRegistrationBean 
- 2. set server.contextPath in application.properties

- [x] [Compiling Vs Transpiling](https://www.stevefenton.co.uk/2012/11/compiling-vs-transpiling/)
- Compiling: transforming into different level abstraction lang; Transpiling: similar level

- [x] log handshake, Oauth
- ``` -Djavax.net.debug=ssl ``` in VM argument

- [x] JS - Sort Array
- The default sort order is according to string Unicode code points.
```js
var numbers = [4, 2, 5, 1, 3];
numbers.sort(function(a, b) {
  return a - b;
});
```

- [x] Spring boot - [Multipart file max size](https://stackoverflow.com/questions/37807460/multipart-exception-maxpostsize-error-in-spring-boot)
- multipart.maxFileSize: 500MB
- multipart.maxRequestSize: 500MB

- [x] Eclipse - [Configure Proxy](https://www.mkyong.com/web-development/how-to-configure-proxy-settings-in-eclipse/)
- Window –> Preferences -> Network Connections -> Manual -> Edit

- [x] Eclipse - [set JAVA for open](https://stackoverflow.com/questions/35881210/setting-the-correct-path-for-eclipse)
```
-vm
C:\Java\JDK\1.8\bin\javaw.exe
//before
--launcher.appendVmargs
-vmargs
```
- [x] Bash - [create symlink](https://stackoverflow.com/questions/1951742/how-to-symlink-a-file-in-linux)
```
To create a new symlink (will fail if symlink exists already):

ln -s /path/to/file /path/to/symlink
To create or update a symlink:

ln -sf /path/to/file /path/to/symlink
```

- [x] Bash -[resize window](https://unix.stackexchange.com/questions/61584/how-to-solve-the-issue-that-a-terminal-screen-is-messed-up-usually-after-a-res)
```
If you are using bash, check if "checkwinsize" option is activated in your session using

shopt | grep checkwinsize
If you don't get

checkwinsize    on
then activate it with

shopt -s checkwinsize
```

- [x] bash - [print last char in file](https://superuser.com/questions/252692/how-to-print-last-character-of-a-file)
```
tail -c 2 file
```

- [x] Bash - [Compress/Extract](https://www.howtogeek.com/248780/how-to-compress-and-extract-files-using-the-tar-command-on-linux/) 
```
tar -czvf name-of-archive.tar.gz /path/to/directory-or-file
tar -xzvf archive.tar.gz
```

- [x] Java [memory](https://stackoverflow.com/questions/14763079/what-are-the-xms-and-xmx-parameters-when-starting-jvms)
- The flag Xmx specifies the maximum memory allocation pool for a Java virtual machine (JVM), while  Xms specifies the initial memory allocation pool.
```
-Xmx1024k
-Xmx512m
-Xmx8g
```
- Tomcat, bin/catalina.sh

- [x] Bash [split a large text file](https://stackoverflow.com/questions/2016894/how-to-split-a-large-text-file-into-smaller-files-with-equal-number-of-lines)
```
1. By line
split -l 200000 filename
2. By size
split -C 20m --numeric-suffixes input_filename output_prefix
```
- [x] https web can't access iframe with http url
- httpd for https proxy
```bash
# .conf 
ProxyPass /path http://192.168.0.101/path
ProxyPassReverse /path http://192.168.0.101/path
```
- [x] Load Balancer, Source IP
- Persistence Method to stick with session
- take the source and destination IP address of the client and server to generate a unique hash key
- use the key to allocate the client to a particular server to ensure it is directed to the same server that it was using previously.

- [x] Spring - cannot find the declaration of element 'beans'
- in config XML: update to schemaLocation to classpath from http
```xml
xsi:schemaLocation=
"http://www.springframework.org/schema/beans 
             classpath:org/springframework/beans/factory/xml/spring-beans-4.3.xsd
http://www.springframework.org/schema/context 
             classpath:org/springframework/beans/factory/xml/spring-context-4.3.xsd"
```

- [x] Maven - build jar-with-dependencies 
```xml
<plugin>
  <artifactId>maven-assembly-plugin</artifactId>
  <configuration>
    <archive>
      <manifest>
        <mainClass>fully.qualified.MainClass</mainClass>
      </manifest>
    </archive>
    <descriptorRefs>
      <descriptorRef>jar-with-dependencies</descriptorRef>
    </descriptorRefs>
  </configuration>
  <executions>
    <execution>
      <id>make-assembly</id> <!-- this is used for inheritance merges -->
      <phase>package</phase> <!-- bind to the packaging phase -->
      <goals>
        <goal>single</goal>
      </goals>
    </execution>
  </executions>
</plugin>
```

- [x] http - [url-encoding-of-the-double-quote](https://stackoverflow.com/questions/23037129/url-encoding-of-the-double-quote)
- double quote %22
- the Apache 2.4 servers responds with 403 Forbidden. It seems they recognize it as attempt of SQL-injection and suppress it immediately.

- [x] bash - check system memory
```bash
$ cat /proc/meminfo
```
- [x] Requirement ambiguity - bottom 5%
- 1. get records from bottom 5% of total values
    - by which level
    - souce gathering from bottom adding to 5%, or skipping the top 95%
- 2. get max record, which level?
- 3. display order

- [x] Maven, update dependency
```bash
mvn clean install -U
```
- [x] Bash - sort
```bash
# sort by second column
sort -k2 -n file
# -n, numerical val
```
- [x] Spring: search class by Annotation
```java
ClassPathScanningCandidateComponenetProvider scanner = new ClassPathScanningCandidateComponenetProvider(false);  // noe need add @Component by default
scanner.addIncludeFilter(new AnnotationTypeFilter(javax.persistence.Entity.class));
for (BeanDefinition bd : scanner.findCandidateComponents("com.app.pacakge.name")) {
    // print fully quailified class names 
}
```
- [x] 502 Bad Gateway
- Architectue: tomcat behind apache as proxy
- issue: get 502 for long time consuming file upload
- fix: increase tomcat connection timeout without proxytimeout change

- [x] SQL - Delete duplicate records
- ROWID and GROUP BY
```sql
delete from TABLE where condition
and rowid not in 
(select max(rowid) from TABLE where same condition group by columns for primary keys)
```









