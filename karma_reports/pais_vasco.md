# PaisVasco2017Filtered.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _uri_municipio_
From column: _Municipio (Nombre)_
``` python
value = getValue("Municipio (Nombre)")
lowercase_name = value.lower()
tokens = lowercase_name.split()

uri = 'http://music_event_domain.org/'
for token in tokens[:-1]:
    uri +=  token + '_'
uri += tokens[-1]

return uri
```

#### _uri_city_
From column: _Nombre lugar_
``` python
value = getValue("Nombre lugar")
lowercase_name = value.lower()
tokens = lowercase_name.split()

uri = 'http://music_event_domain.org/'
for token in tokens[:-1]:
    uri +=  token + '_'
uri += tokens[-1]

return uri
```

#### _uri_pais_
From column: _Pais (Nombre)_
``` python
value = getValue("Pais (Nombre)")
lowercase_name = value.lower()
tokens = lowercase_name.split()

uri = 'http://music_event_domain.org/'
for token in tokens[:-1]:
    uri +=  token + '_'
uri += tokens[-1]

return uri
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Fecha inicio evento_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#StartDate` | `Concert1`|
| _LATWGS84_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#latitude` | `City1`|
| _LONWGS84_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#longitude` | `City1`|
| _Municipio (Nombre)_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#value` | `State1`|
| _Nombre lugar_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#value` | `City1`|
| _País (Nombre)_ | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#value` | `Country1`|
| _uri_city_ | `uri` | `City1`|
| _uri_municipio_ | `uri` | `State1`|
| _uri_pais_ | `uri` | `Country1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `City1` | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#partOf` | `State1`|
| `Concert1` | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#takesPlaceAt` | `City1`|
| `State1` | `http://www.semanticweb.org/ric/ontologies/2018/9/musicEvent#partOf` | `Country1`|
