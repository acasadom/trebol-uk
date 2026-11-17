# trebol-uk

The rules of a form for [Trebol](https://github.com/acasadom/trebol): postcodes and National Insurance numbers.

```sh
npm install trebol-uk
```

A program that imports the package writes the rules after its fields, as it writes `email`:

```trebol
import 'trebol-uk

view [
    form [
        field post "Postcode" required postcode
        field ni "National Insurance number" ni-number
        submit "Save" [toast "Saved"]
    ]
]
```

| Rule        | Function     | What it takes |
| ----------- | ------------ | --- |
| `postcode`  | `postcode?`  | a postcode: `SW1A 1AA`, `M1 1AE`, `GIR 0AA` |
| `ni-number` | `ni-number?` | a National Insurance number: `AB 12 34 56 C` |

Spaces and small letters are fine: `sw1a1aa` is a postcode. The rules check that the value is well made:
the letters each place of a postcode may have, the prefixes HMRC never gives. They do not check that it exists. Each message is in English and Spanish, and an app may change it in `i18n/ui`, as any other.

The functions work without forms too: `postcode? "SW1A 1AA"` is true.

## Tests

```sh
npm test
```
