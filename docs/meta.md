# Meta Schema

To produce this JSON data :
```
{
  "make": "Honda",
  "model": "333",
  "year": 2008,
  "safety": 0
}
```

We need this JSON schema :
```
{
  type: "object",
  title: "Car",
  properties: {
    make: {
      type: "string"
    },
    model: {
      type: "string"
    },
    year: {
      type: "integer"
    },
    safety: {
      type: "integer"
    }
  }
}
```

Since a JSON schema is abviously also JSON data.
Which JSON schema could generate via json-editor this JSON schema ?

# Naive approach

JSON data :

```
{
  type: "object",
  title: "Car",
  properties: {
    make: {
      type: "string"
    },
    model: {
      type: "string"
    },
    year: {
      type: "integer"
    },
    safety: {
      type: "integer"
    }
  }
}
```

JSON schema :
```
{
  type: "object",
  title: "Car schema",
  properties: {
    type: {
      type: "string",
      default: "object",
      readonly: true
    },
    title: {
      type: "string"
    },
    properties: {
      type: "object",
      title: "Properties",
      properties: {
        type: {
          type: "string"
        },
        title: {
          type: "string"
        },
        properties: {
          type: "string"
        }
      }

    }
  }
}
```


## other schema

Schema from basic.html example :
```
{
  type: "object",
  title: "Car",
  properties: {
    make: {
      type: "string",
      enum: [
        "Toyota",
        "BMW",
        "Honda",
        "Ford",
        "Chevy",
        "VW"
      ]
    },
    model: {
      type: "string"
    },
    year: {
      type: "integer",
      enum: [
        1995,1996,1997,1998,1999,
        2000,2001,2002,2003,2004,
        2005,2006,2007,2008,2009,
        2010,2011,2012,2013,2014
      ],
      default: 2008
    },
    safety: {
      type: "integer",
      format: "rating",
      maximum: "5",
      exclusiveMaximum: false,
      readonly: false
    }
  }
}
```
