# github-lang-css

dynamically generated css package for github language colors, updated every time when `npm run build` is executed.

## cdn

```html
<!-- text color -->
<link rel="stylesheet" href="https://unpkg.com/github-lang-css/index.css">

<!-- background color; attach "-bg" to the end of reformatted classes -->
<link rel="stylesheet" href="https://unpkg.com/github-lang-css/background.css">

<!-- {"reformatted-lang": color, ...} -->
<link rel="stylesheet" href="https://unpkg.com/github-lang-css/langs.json">

<!-- {"raw lang": color, ...} -->
<link rel="stylesheet" href="https://unpkg.com/github-lang-css/raw_langs.json">
```

## usage

because github language names aren't compatable with css, some replacement must be done:

```js

const digitToWord = [
  "zero",
  "one",
  "two",
  "three",
  "four",
  "five",
  "six",
  "seven",
  "eight",
  "nine",
];

const langFromGithub = "...";

const cssClass = langFromGithub
    .replace("+", "p")
    .replace("#", "-Sharp")
    .replace(/\s/g, "-")
    .replace(".", "-")
    .replace(/["'()]/g, "")
    .replace(/^\d/, (match) => digitToWord[match]);

```
