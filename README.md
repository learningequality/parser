# The vuedoc parser
Generate a JSON documentation for a Vue file component

[![Build Status](https://travis-ci.org/vuedoc/vuedoc-parser.svg?branch=master)](https://travis-ci.org/vuedoc/vuedoc-parser)
[![bitHound Dependencies](https://www.bithound.io/github/vuedoc/vuedoc-parser/badges/dependencies.svg)](https://www.bithound.io/github/vuedoc/vuedoc-parser/master/dependencies/npm)

## Install
```sh
npm install --save @vuedoc/parser
```

## Usage
```js
const parser = require('vuedoc-parser')
const options = {
  filename: 'test/fixtures/checkbox.vue'
}

parser.parse(options)
  .then((component) => console.log(component))
  .catch((err) => console.error(err))
```

This will print this JSON output:

```js
{
  "header": [
    {
      "entry": {
        "name": "checkbox" // The component name
      },
      
      // The component description
      "comments": [
        "A simple checkbox component"
      ]
    }
  ],
  "props": [
    {
      "entry": {
        "model": {
          "type": "Array",
          "required": true,
          "twoWay": true
        }
      },
      "comments": [
        "The checbox model"
      ]
    },
    {
      "entry": {
        "disabled": "Boolean"
      },
      "comments": [
        "Initial checbox state"
      ]
    },
    {
      "entry": {
        "checked": {
          "type": "Boolean",
          "default": true
        }
      },
      "comments": [
        "Initial checbox value"
      ]
    }
  ],
  "slots": [
    {
      "name": "label",
      "comments": [
        "Use this slot to set the checbox label"
      ]
    }
  ],
  "events": [
    {
      "name": "loaded",
      "comments": [
        "Emited when the component has been loaded"
      ]
    }
  ],
  "methods": [
    {
      "entry": {
        "check": {
          "type": "FunctionExpression"
        }
      },
      "comments": [
        "Check the checbox"
      ]
    }
  ]
}
```

## Related projects
- [vuedoc.md](https://github.com/vuedoc/vuedoc.md) - A Markdown Documentation Generator for View Files

## License

Under the MIT license. See [LICENSE](https://github.com/vuedoc/vuedoc-parser/blob/master/LICENSE) file for more details.