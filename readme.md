# Intro

This package makes it easy to download tables from HTML pages as CSV files.

# Installation

For use in Node or in the browser:

```bash
npm install --save https://github.com/jrc03c/download-tables
```

For use at the command line:

```bash
npm install -g https://github.com/jrc03c/download-tables
```

# Usage

In the browser:

```html
<script src="path/to/dist/download-tables.js"></script>
<script>
  downloadTables()
</script>
```

In Node:

```js
const { JSDOM } = require("jsdom")
const fs = require("fs")

const raw = fs.readFileSync("some_file.html", "utf8")
const dom = new JSDOM(raw)

downloadTables(dom.window.document)
```

At the command line:

```bash
# using an individual file
download-tables some_file.html

# using a glob of files
download-tables *.html
```

In the browser, CSV files will be downloaded the same way all other files are. When using the Node or command line versions, CSV files will be saved in the current working directory and numbered, like "table01.csv", "table02.csv", etc.