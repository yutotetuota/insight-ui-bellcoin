# Insight UI

A Bellcoin blockchain explorer web application service for [Bellcore Node](https://github.com/yutotetuota/bellcore-node) using the [Insight API](https://github.com/yutotetuota/insight-api-bellcoin).

## Quick Start

Please see the guide at [https://bellcore.io/guides/full-node](https://bellcore.io/guides/full-node) for information about getting a block explorer running. This is only the front-end component of the block explorer, and is packaged together with all of the necessary components in [Bellcore](https://github.com/yutotetuota/bellcore).

## Getting Started

To manually install all of the necessary components, you can run these commands:

```bash
npm install -g git://github.com/yutotetuota/bellcore-node.git
bellcore-node create mynode
cd mynode
bellcore-node install git://github.com/yutotetuota/insight-api-bellcoin.git
bellcore-node install git://github.com/yutotetuota/insight-ui-bellcoin.git
bellcore-node start
```

Open a web browser to `http://localhost:3001/insight/`

## Development

To build Insight UI locally:

```
$ npm run build
```

A watch task is also available:

```
$ npm run watch
```

## Changing routePrefix and apiPrefix

By default, the `insightConfig` in `package.json` is:

```json
  "insightConfig": {
    "apiPrefix": "insight-api-bellcoin",
    "routePrefix": "insight"
  }
```

To change these routes, first make your changes to `package.json`, for example:

```json
  "insightConfig": {
    "apiPrefix": "api",
    "routePrefix": ""
  }
```

Then rebuild the `insight-ui-bellcoin` service:

```
$ npm run build
```

## Multilanguage support

Insight UI uses [angular-gettext](http://angular-gettext.rocketeer.be) for multilanguage support.

To enable a text to be translated, add the ***translate*** directive to html tags. See more details [here](http://angular-gettext.rocketeer.be/dev-guide/annotate/). Then, run:

```
grunt compile
```

This action will create a template.pot file in ***po/*** folder. You can open it with some PO editor ([Poedit](http://poedit.net)). Read this [guide](http://angular-gettext.rocketeer.be/dev-guide/translate/) to learn how to edit/update/import PO files from a generated POT file. PO file will be generated inside po/ folder.

If you make new changes, simply run **grunt compile** again to generate a new .pot template and the angular javascript ***js/translations.js***. Then (if use Poedit), open .po file and choose ***update from POT File*** from **Catalog** menu.

Finally changes your default language from ***public/src/js/config***

```
gettextCatalog.currentLanguage = 'es';
```

This line will take a look at any *.po files inside ***po/*** folder, e.g.
**po/es.po**, **po/nl.po**. After any change do not forget to run ***grunt
compile***.


## Note

For more details about the [Insight API](https://github.com/yutotetuota/insight-api-bellcoin) configuration and end-points, go to [Insight API GitHub repository](https://github.com/yutotetuota/insight-api-bellcoin).

## Contribute

Contributions and suggestions are welcomed at the [Insight UI GitHub repository](https://github.com/yutotetuota/insight-ui-bellcoin).


## License
(The MIT License)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
