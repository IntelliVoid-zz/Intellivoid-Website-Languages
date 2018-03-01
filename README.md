# Intellivoid Website Languages
This repository contains the language files used to display text on Intellivoid's official website in different languages

## How it works
`configuration.json` contains information about the language and the language code, this is used by the page delivery system to provide the proper headers and HTML format that the browser needs to know to display the text properly

```
"en": <-- ref #1
{
    "C-CODE": "en", <-- Needs to be the same as #1
    "CODE": "en", <-- The language code (en, es, jp and so on)
    "HEADER": "en-US", <-- The language code w/ the country (en-US, en-CA, zh-Hans-CN, ...)
    "DIR": "en" <-- The directory containing the language files
}
```

## Language Files
Each directory such as `en` should contain only `.json` files with the appropriate format; `"BUTTON_TEXT": "Hello"`

The `key` indicates the property to assign the text to, **this should not be modified**.

The `value` indicates the text the property should display, which would be the value that should be modified

`%s` is a prefix indicating where text would be applied, for example:

```json
{
    "WELCOME": "Hello, %s!"
}
```

Output:
```
Hello, John!
```

**%s Should not be removed, or replaced.** this is designed for languages that moves words around to make it easier for the page delivery system to output the proper text

## Examples
Below are an example of how to create a language file followed by how the configuration.json file should look like

English Example (`src/en/home.json`)
```json
{
    "BUTTON_WELCOME": "Welcome User",
    "BUTTON_CLOSE": "Close this window"
}
```

Spanish Example (`src/es/home.json`)
```json
{
    "BUTTON_WELCOME": "Bienvenido Usuario",
    "BUTTON_CLOSE": "Cierra esta ventana"
}
```

`configuration.json`
```json
{
    "en":{
        "C-CODE": "en",
        "CODE": "en",
        "HEADER": "en-US",
        "DIR": "en"
    },
    "es":{
        "C-CODE": "es",
        "CODE": "es",
        "HEADER": "es-ESP",
        "DIR": "es"
    }
}
```
---
## License
GNU GENERAL PUBLIC LICENSE
