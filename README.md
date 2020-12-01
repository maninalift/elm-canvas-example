# Test project for `elm-canvas`

Very simple project created with

```bash
elm init
elm install joakin/elm-canvas
```

Which resulted in the followinf elm.json

```json
{
    "type": "application",
    "source-directories": [
        "src"
    ],
    "elm-version": "0.19.1",
    "dependencies": {
        "direct": {
            "elm/browser": "1.0.2",
            "elm/core": "1.0.5",
            "elm/html": "1.0.0",
            "joakin/elm-canvas": "4.2.1"
        },
        "indirect": {
            "avh4/elm-color": "1.0.0",
            "elm/json": "1.1.3",
            "elm/time": "1.0.0",
            "elm/url": "1.0.0",
            "elm/virtual-dom": "1.0.2"
        }
    },
    "test-dependencies": {
        "direct": {},
        "indirect": {}
    }
}
```

I added just the following to my `src/Main.elm`

```elm
module Main exposing (..)

import Canvas as Canvas

main = Canvas.toHtml (500, 800) [][]
```


Then ran `elm reactor`. The HTML that resulted for the canvas element was


```html
<elm-canvas height="800" width="500"><canvas></canvas></elm-canvas>
```

The height and width attributes are set on the `<elm-canvas>` element and not the inner `<canvas>` and as a result the canvas defaults to 300 by 150.