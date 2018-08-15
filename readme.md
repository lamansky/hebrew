# hebrew

A JSON file of Hebrew character names and Unicode points.

## Rationale

Programming with Hebrew can be tricky. Code editors can have difficulty working with right-to-left characters in the midst of left-to-right code, and combining characters (which pointed Hebrew uses constantly) are almost impossible to work with by themselves in a code editor without rendering them as obscure codes like `\u05b0`.

This JSON file gives you named Hebrew character variables to work with, so you can, for example, type `holam` instead of `'\u05b9'`.

## Important Notes

* There are many different ways to spell English transliterations of Hebrew character names. This library uses the same spellings as those found in [the Unicode standard](https://www.unicode.org/charts/PDF/U0590.pdf).

* In the JSON object, the characters are subdivided by seven keys corresponding to the Hebrew character category name prefixes in the Unicode standard (`letters`, `points`, `accents`, `punctuation`, `marks`, `signs`, `yiddishLigatures`).

* Those consonants which have a final form (kaf, mem, nun, pe, and tsadi) will have both forms in an array, the final form being last.

## Installation

Using [Node.js](https://nodejs.org/):

```bash
npm i hebrew
```

## Examples

```javascript
const {letters: {dalet, vav}, points: {dagesh, hiriq, qamats}} = require('hebrew')

dalet + dagesh + qamats + vav + hiriq + dalet // 'דָּוִד'
```

```javascript
const {letters: {kaf: [kaf, finalKaf]}} = require('hebrew')

kaf // 'כ'
finalKaf // 'ך'
```
