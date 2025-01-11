## API hacking

#### REST api
most api's are rest api's 
- look for JSON data 
- look for MIME type json in responses (burpsuite)
- uses http methods 
each request is a resource
#### RPC remote procedure call
either **xmlrpc** or **jsonrpc**
maps requests to methods adnexecute them remotely
methodcall
    method name
        system.listMethods in xmlrpc

#### SOAP simple object access protocol
its like xmlrpc but not methods

`<soapenv:Enevelope>`
    indicator

example:

```html
<soapenv:Body>
<web:GetCitiesByCountry>
<!--type: string-->
<web:CountryName>gero et</web:CountryName>
</web:GetCitiesByCountry>
<soapenv:Body>

```
#### GraphQL
requests arent mapped each to a resource instead uses a Query
-- one request can return anything

in directory brute forcing try: 
● /graphql
● /graphiql
● /graphql.php
● /graphql/console

**use introspection** 
```javascript
query {
  __schema {
    types {
      name
    }
  }
}
```
[documentation for it ](https://graphql.org/learn/introspection/)