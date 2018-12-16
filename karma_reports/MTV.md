# MTV

## Add Column

## Add Node/Literal
#### Node: `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#Artist/Artist1`
Uri: `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#Artist`
<br/>Id: `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#Artist1`


## PyTransforms
#### _uri_artist_
From column: _name_
``` python
artist_name = getValue("name")
lowercase_name = artist_name.lower()
tokens = lowercase_name.split()
tokens.sort()

uri = 'music_event_domain'
for token in tokens:
    uri += '_' + token

return uri
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _name_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#personalName` | `Artist1`|
| _uri_artist_ | `uri` | `Artist1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
