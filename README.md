# Data-Forge

Fork of the Data-Forge project.

See the [official repository](https://github.com/data-forge/data-forge-ts) for the original data forge project source code.

See the [official registry](https://www.npmjs.com/package/data-forge) for the original data forge npm package.

Please [support](https://www.codecapers.com.au/about#support-my-work) the original authors work!


The JavaScript data transformation and analysis toolkit inspired by Pandas and LINQ.

*Implemented* in TypeScript.<br>
*Used* in JavaScript ES5+ or TypeScript.

[![Build Status](https://github.com/madnetter/data-forge-ts/actions/workflows/npm-publish.yml/badge.svg)](https://github.com/madnetter/data-forge-ts)
[![npm version](https://badge.fury.io/js/data-forge.svg)](https://badge.fury.io/js/@madnetter%2Fdata-forge.svg)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)

## Install

To install for Node.js and the browser:

    npm install --save data-forge

If working in Node.js and you want the functions to read and write data files:

    npm install --save data-forge-fs

## Quick start

Data-Forge can load CSV, JSON or arbitrary data sets. 

Parse the data, filter it, transform it, aggregate it, sort it and much more.

Use the data however you want or export it to CSV or JSON.

Here's an example:

```JavaScript
const dataForge = require('data-forge');
require('data-forge-fs'); // For readFile/writeFile.

dataForge.readFileSync('./input-data-file.csv') // Read CSV file (or JSON!)
    .parseCSV()
    .parseDates(["Column B"]) // Parse date columns.
    .parseInts(["Column B", "Column C"]) // Parse integer columns.
    .parseFloats(["Column D", "Column E"]) // Parse float columns.
    .dropSeries(["Column F"]) // Drop certain columns.
    .where(row => predicate(row)) // Filter rows.
    .select(row => transform(row)) // Transform the data.
    .asCSV() 
    .writeFileSync("./output-data-file.csv"); // Write to output CSV file (or JSON!)
```

## From the browser

Data-Forge has been tested with Browserify and Webpack. Please see links to examples below.

If you aren't using Browserify or Webpack, the npm package includes a pre-packed browser distribution that you can install and included in your HTML as follows:

```html
<script language="javascript" type="text/javascript" src="node_modules/data-forge/dist/web/index.js"></script>
```

This gives you the data-forge package mounted under the global variable `dataForge`.

Please remember that you can't use data-forge-fs or the file system functions in the browser.

## Features

- Import and export CSV and JSON data and text files (when using [Data-Forge FS](https://github.com/data-forge/data-forge-fs)).
- Or work with arbitrary JavaScript data.
- Many options for working with your data:
    - Filtering
    - Transformation
    - Extracting subsets
    - Grouping, aggregation and summarization
    - Sorting
    - And much more
- Great for slicing and dicing tabular data:
    - Add, remove, transform and generate named columns (series) of data.
- Great for working with time series data.
- Your data is indexed so you have the ability to merge and aggregate.
- Your data is immutable! Transformations and modifications produce a new dataset.
- Build data pipeline that are evaluated lazily.
- Inspired by Pandas and LINQ, so it might feel familiar!

## Platforms

- Node.js (npm install --save data-forge data-forge-fs) ([see example here](https://github.com/madnetter/data-forge-examples-and-tests/tree/master/package-test/npm))
- Browser
    - Via bower (bower install --save data-forge) ([see example here](https://github.com/madnetter/data-forge-examples-and-tests/tree/master/package-test/bower))
    - Via Browserify ([see example here](https://github.com/madnetter/data-forge-examples-and-tests/tree/master/examples/2.%20plot%20-%20in%20browser))
    - Via Webpack ([see example here](https://github.com/madnetter/data-forge-examples-and-tests/tree/master/examples/3.%20plot%20-%20in%20browser%20-%20with%20dates))

## Documentation

- [Changes](docs/changes.md)
- [The guide](docs/guide.md)
- [Key concepts](docs/concepts.md)
- [API docs](https://data-forge.github.io/data-forge-ts/)
- [FS API docs](https://data-forge.github.io/data-forge-fs/index.html)
- [Data-Forge FS](https://github.com/data-forge/data-forge-fs/)
- [Data-Forge Plot](https://github.com/data-forge/data-forge-plot/)

## Resources

- [The Data Wrangler](http://www.the-data-wrangler.com/)
- [Data Wrangling with JavaScript](http://bit.ly/2t2cJu2)
- [Data-Forge Notebook](http://www.data-forge-notebook.com/)