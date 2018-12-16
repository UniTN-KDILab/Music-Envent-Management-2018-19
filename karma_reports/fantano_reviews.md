# fantano_reviews

## Add Column

## Add Node/Literal

## PyTransforms
#### _uri_artist_
From column: _artist_
``` python
artist_name = getValue("artist")
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
| _artist_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#personalName` | `Artist1`|
| _link_ | `uri` | `Review1`|
| _score_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#score` | `Review1`|
| _uri_artist_ | `uri` | `Artist1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `Artist1` | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#hasReview` | `Review1`|
