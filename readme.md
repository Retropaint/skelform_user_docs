# SkelForm User Documentation

Made with [mdBook](https://github.com/rust-lang/mdBook).

## Formatting

Formatting markdown files is done with [dprint](https://dprint.dev/), with the
following relevant config file:

````json
{
    "markdown": {
        "textWrap": "always"
    },
    "plugins": [
        "https://plugins.dprint.dev/markdown-0.18.0.wasm",
    ]
}
````
