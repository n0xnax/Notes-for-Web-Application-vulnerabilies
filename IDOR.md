## Insecure Direct Object Reference
accessing data that ur not authorized to access by using direct references like IDs etc
~~failure of access controls~~

look for requests with :
**id, username, email, or some other id**
use other users 
example: 
`
http://site.com/changeEmail?id=1234
`
changing **id** with a diff might change the email of someone else
**note:** unpredictable id's could be simple MD5 hashes or even encodings.
in reality it could be just a **Number** like **7** 