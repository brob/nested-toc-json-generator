# Gets a nested ToC data structure from heading data 

This is currently tested against Hygraph data, but should work for most data if you follow the following structure:

```js
[
  {
    "type": "heading-one", // or h1
    "id": "some-id-here" // ID for jumplink
    // ...additionalData
  },
  {
    "type": "heading-two", // or h2
    "id": "some-other-id-here" // ID for jumplink
    // ...additionalData
  }
]
```
Given that structure, it will return a nested structure for frontend loops and nested lists.

```js
[
    {
        "type": "heading-one",
        "id": "some-id-here"
        // ...additionalData,
        "tocChildren": [
            {
                "type": "heading-two",
                "id": "some-other-id-here",
                "children": [ [Object] ],
                "tocChildren": [],
            }
        ]
    }
]
```

## Installation
```bash
npm i nested-toc-json-generator
```

## Usage

```js
const generateJSON = require("nested-toc-json-generator")

const data = [
  {
    "type": "heading-one", // or h1
    "id": "some-id-here" // ID for jumplink
    // ...additionalData
  },
  {
    "type": "heading-two", // or h2
    "id": "some-other-id-here" // ID for jumplink
    // ...additionalData
  }
]

const headerJson = generateJSON(headerJson)

```