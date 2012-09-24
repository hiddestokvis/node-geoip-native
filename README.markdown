# Node GeoIP Native

This package is a lightning-fast, native JavaScript geoip lookup built on [MaxMind](http://www.maxmind.com/)'s free country database.

It is non-blocking and operates without any IO after initially loading the data into memory.

Results are 4 - 5 times faster than geoip-lite with the caveat that it takes longer to initialize and uses 60 or 70 megabytes memory.

Benchmarks on my 2011 Macbook Air whilst running lots of software.  The test took the middle 10 results from 20 iterations of performing 1,000,000 lookups and averaged them.  The APIs are interchangeable so tests  were identical.

	geoip-native
	average: 1540.3

	geoip-lite
	average: 8375.3

## Requires

1. Comes with the [standard CSV database by MaxMind](http://www.maxmind.com/app/geolite) which may require updating.

## How to use
1. git clone https://github.com/benlowry/node-mongodb-wrapper
2. cd node-mongodb-wrapper
3. node test.js

or just ```npm install geoip-native```

## Methods

Node MongoDB Wrapper provides methods for:

1. ```lookup``` performs the lookup, takes the ip address as a parameter

## Examples

	var geoip = require("geoip-native");
	var ip = "123.123.123.123";
	geoip.lookup(ip);

	// in practice you'd want:
	// ip = request.headers["x-forwarded-for"] || request.connection.remoteAddress,

### What's missing
Be neat to expand this to include cities.

### License
Copyright [Playtomic Inc](https://playtomic.com), 2012.  Licensed under the MIT license.  Certain portions may come from 3rd parties and carry their own licensing terms and are referenced where applicable.

This product includes GeoLite data created by MaxMind, available from http://www.maxmind.com