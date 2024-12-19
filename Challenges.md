# Challenges

A list of chalenges formatted as an individual api endpoints.

## 1 Pi api

An api endpoint that returns pi, peferably from an equivelent of math.random()

Request:

```json
{}
```

Response:

```json
{
  "value": "3.141592654"
}
```

### 1.1 Specify decimal places

Add an ability to specifiy number of decimal places. This should still return the previous response if noOfDecimal is not specified.

Request:

```json
{
  "noOfDecimal": 1
}
```

Response

```json
{
  "value": "3.1"
}
```

## 2 Value filter

An api that does a search through an array and removes values with the provided filter value

Request:

```json
{
  "filter": "filterValue",
  "values": [
    {
      "key": "a",
      "value": "filterValue"
    },
    {
      "key": "b",
      "value": "notFilter"
    },
    {
      "key": "d",
      "value": "notFilter"
    }
  ]
}
```

Response:

```json
[
  {
    "key": "b",
    "value": "notFilter"
  },
  {
    "key": "d",
    "value": "notFilter"
  }
]
```

### 2.1 return only or return not

Maintain the old functionality and add a mode selection where it either filters out the filterValue or returns objects only with filterValue

Request:

```json
{
  "filter": "filterValue",
  "mode": "only",
  "values": [
    {
      "key": "a",
      "value": "filterValue"
    },
    {
      "key": "b",
      "value": "notFilter"
    },
    {
      "key": "d",
      "value": "notFilter"
    }
  ]
}
```

Response:

```json
[
  {
    "key": "a",
    "value": "filterValue"
  }
]
```

### 2.2 Support regex filtering

take a regex term and apply it

```json
{
  "filter": "filterValue",
  "mode": "regex",
  "values": [
    {
      "key": "a",
      "value": "filterValue"
    },
    {
      "key": "b",
      "value": "notFilter"
    },
    {
      "key": "d",
      "value": "notFilter"
    }
  ]
}
```

Response:

```json
[
  {
    "key": "a",
    "value": "filterValue"
  }
]
```

## 3 Fizz Buzzer

An api that plays the classic fizz buzz where it counts up and where it is a multiple of 3 its fizz and a multiple of 5 it is buzz.

Request:

```json
{
  "length": 5
}
```

Response:

```json
["1", "2", "fizz", "3", "buzz"]
```

### 3.1 Start and step

Add the ability to specify start and step.

Request:

```json
{
  "length": 3,
  "start": 13,
  "step": 2
}
```

Response:

```json
["13", "fizz buzz", "17"]
```

### 3.2 custom rules

Add the ability to add custom rules to this function Multiple rules should be additive (so if there are two at modulus 3 it strings them together)

Request:

```json
{
  "length": 6,
  "customRules": [
    {
      "modulus": 2,
      "value": "yay"
    }
  ]
}
```

Response

```json
["1", "yay", "fizz", "yay", "buzz"]
```

### 3.3 Disbale defaults

just now add the ability to remove the default fizz and buzz

Request:

```json
{
  "length": 6,
  "defaults": false,
  "customRules": [
    {
      "modulus": 2,
      "value": "yay"
    }
  ]
}
```

Response

```json
["1", "yay", "3", "yay", "5"]
```
