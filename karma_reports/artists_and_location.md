# music artist with location.csv

## Add Column

## Add Node/Literal
#### Node: `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#Artist/Artist1`
Uri: `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#Artist`
<br/>Id: `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#Artist1`

#### Node: `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#City/City1`
Uri: `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#City`
<br/>Id: `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#City1`


## PyTransforms
#### _uri_artist_
From column: _artist.name_
``` python
artist_name = getValue("artist.name")
lowercase_name = artist_name.lower()
tokens = lowercase_name.split()

uri = 'http://music_event_domain.org/'
for token in tokens[:-1]:
    uri +=  token + '_'
uri += tokens[-1]

return uri
```

#### _city_
From column: _location_
``` python
import re

location = getValue("location")
if location != 'Not Defined':
    entities = re.split('-|,',location)
    if len(entities) > 0:
        return entities[0]
return location
```

#### _state_
From column: _location_
``` python
location = getValue("location")
tokens = location.split(' ')
country = ''
for token in tokens[::-1]:
    if token.isupper():
        return token
return 'Not Defined'
```

#### _uri_city_
From column: _location_
``` python
import re

domain = 'http://music_event_domain.org/'
location = getValue("location")
if location != 'Not Defined':
    entities = re.split('-|,',location)
    if len(entities) > 0:
        return domain + entities[0]
return domain + location
```

#### _uri_state_
From column: _state_
``` python
domain = 'http://music_event_domain.org/'
location = getValue("location")
tokens = location.split(' ')
country = ''
for token in tokens[::-1]:
    if token.isupper():
        return domain + token
return domain + 'Not Defined'
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _artist.name_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#personalName` | `Artist1`|
| _city_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#value` | `City1`|
| _latitude_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#latitude` | `City1`|
| _longitude_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#longitude` | `City1`|
| _state_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#value` | `State1`|
| _terms_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#genre` | `Artist1`|
| _uri_artist_ | `uri` | `Artist1`|
| _uri_city_ | `uri` | `City1`|
| _uri_state_ | `uri` | `State1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `City1` | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#partOf` | `State1`|
| `Concert1` | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#performedBy` | `Artist1`|
| `Concert1` | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#takesPlaceAt` | `City1`|
