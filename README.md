# bittorrent-peerid [![travis][travis-image]][travis-url] [![npm][npm-image]][npm-url] [![downloads][downloads-image]][downloads-url] [![javascript style guide][standard-image]][standard-url] [![Greenkeeper badge][greenkeeper-image]][greenkeeper-url]

[travis-image]: https://img.shields.io/travis/webtorrent/bittorrent-peerid/master.svg
[travis-url]: https://travis-ci.org/webtorrent/bittorrent-peerid
[npm-image]: https://img.shields.io/npm/v/bittorrent-peerid.svg
[npm-url]: https://npmjs.org/package/bittorrent-peerid
[downloads-image]: https://img.shields.io/npm/dm/bittorrent-peerid.svg
[downloads-url]: https://npmjs.org/package/bittorrent-peerid
[standard-image]: https://img.shields.io/badge/code_style-standard-brightgreen.svg
[standard-url]: https://standardjs.com
[greenkeeper-image]: https://badges.greenkeeper.io/webtorrent/bittorrent-peerid.svg
[greenkeeper-url]: https://greenkeeper.io/

### Map a BitTorrent peer ID to a human-readable client name and version

Also works in the browser with [browserify](http://browserify.org/)!

This module is used by [WebTorrent](https://webtorrent.io).

## install

```
npm install bittorrent-peerid
```

## usage

```js
var peerid = require('bittorrent-peerid')
var parsed = peerid('-AZ2200-6wfG2wk6wWLc')

console.log(parsed.client, parsed.version)
```

The `parsed` peerid object looks like this:

```js
{
  client: 'Vuze',
  version: '2.2.0.0'
}
```

bittorrent-peerid can parse peer ids encoded in the following formats:
* a 20-byte Buffer
* a 40-character hex string
* an arbitrarily-sized human-readable utf8 string (must decode to a 20-byte Buffer)

If an unknown peer id is passed in, the returned client will be `unknown`.

## todo

* ~~Support known Azureus-style clients.~~
* ~~Support known Shadow-style clients.~~
* ~~Support known Mainline-style clients.~~
* ~~Support known Custom-style clients.~~
* ~~Recognize BitComet/Lord/Spirit spoofing.~~
* Full support for client version parsing.
* Full support for customized client version schemes.
* Support unknown clients that conform to either the Azureus or Shadow-style conventions.

## credit

This module is based heavily on the BTPeerIDByteDecoderDefinitions class from [Azureus](http://sourceforge.net/projects/azureus/) (Vuze). Related resources include:
* [BitTorrent Specification](http://wiki.theory.org/BitTorrentSpecification)
* [Transmission](http://transmission.m0k.org/trac/browser/trunk/libtransmission/clients.c)
* [g3peerid](http://rufus.cvs.sourceforge.net/rufus/Rufus/g3peerid.py?view=log)
* [Shareaza](http://shareaza.svn.sourceforge.net/viewvc/shareaza/trunk/shareaza/BTClient.cpp?view=markup)
* [libtorrent](http://libtorrent.rakshasa.no/browser/trunk/libtorrent/src/torrent/peer/client_list.cc)

## license

MIT. Copyright (c) Travis Fischer and [WebTorrent, LLC](https://webtorrent.io).
