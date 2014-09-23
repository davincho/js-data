<img src="https://raw.githubusercontent.com/js-data/js-data/master/js-data.png" alt="js-data logo" title="js-data" align="right" width="64" height="64" />

## js-data  [![Stories in Backlog](https://badge.waffle.io/js-data/js-data.svg?label=backlog&title=Backlog)](http://waffle.io/js-data/js-data) [![Stories in Ready](https://badge.waffle.io/js-data/js-data.svg?label=ready&title=Ready)](http://waffle.io/js-data/js-data) [![Stories in progress](https://badge.waffle.io/js-data/js-data.svg?label=in%20progress&title=In%20Progress)](http://waffle.io/js-data/js-data)

Inspired by [Ember Data](https://github.com/emberjs/data), js-data is the model layer you've been craving. It consists of a convenient framework-agnostic, in-memory cache for managing your data, which users adapters to communicate with various persistence layers.

You can use the [http adapter](http://www.js-data.io/js-data-http), which is perfect for communicating with your RESTful backend. You could also use the [localStorage adapter](http://www.js-data.io/js-data-localstorage). More adapters are coming, and you're free to implement your own.

Unlike Backbone and Ember Models, js-data does not require the use of getters and setters, and doesn't wrap your data with custom classes if you don't want it to. js-data's internal dirty-checking (via [observe-js](https://github.com/Polymer/observe-js) or `Object.observe` in supporting browsers) allows for powerful use cases and an easy avenue for implementing your own [3-way data-binding](https://www.firebase.com/blog/2013-10-04-firebase-angular-data-binding.html).

Supporting relations, computed properties, model lifecycle control and a slew of other features, js-data is the tool for giving your data the respect it deserves.

__Latest Release:__ [0.3.1](https://github.com/js-data/js-data/releases/tag/0.3.1)

js-data is pre-alpha. The API is subject to change, though the current api is well tested.

If you want to use js-data, keep a close eye on the changelog. 1.0.0 will introduce strict semver (until then, minor number is bumped for breaking changes).

## Quick Start
`bower install --save js-data js-data-http` or `npm install --save js-data js-data-http`.

Load `js-data-http.js` after `js-data.js`.

```js
var dataStore = new JSData.DS();

dataStore.adapters.DSHttpAdapter = new DSHttpAdapter();

// use http by default for async operations
dataStore.defaults.defaultAdapter = 'DSHttpAdapter';

// simplest model definition
var User = dataStore.defineResource('user');

User.find(1).then(function (user) {
  user; // { id: 1, name: 'John' }
});
```

All your data are belong to you...

## API
- [DS](DS)
- [DSHttpAdapter](DSHttpAdapter)
- [DSLocalStorageAdapter](DSLocalStorageAdapter)
- [DSFirebaseAdapter](DSFirebaseAdapter)
- [Schemator](Schemator)

## Changelog
[CHANGELOG.md](https://github.com/js-data/js-data/blob/master/CHANGELOG.md)

## Version Migration
[TRANSITION.md](https://github.com/js-data/js-data/blob/master/TRANSITION.md)

## Community
- [Mailing List](https://groups.io/org/groupsio/jsdata) - Ask your questions!
- [Issues](https://github.com/js-data/js-data/issues) - Found a bug? Feature request? Submit an issue!
- [GitHub](https://github.com/js-data/js-data) - View the source code for js-data.
- [Contributing Guide](https://github.com/js-data/js-data/blob/master/CONTRIBUTING.md)

## Contributing

First, feel free to contact me with questions. [Mailing List](https://groups.io/org/groupsio/jsdata). [Issues](https://github.com/js-data/js-data/issues).

1. Contribute to the issue that is the reason you'll be developing in the first place
1. Fork js-data
1. `git clone https://github.com/<you>/js-data.git`
1. `cd js-data; npm install; bower install;`
1. `grunt go` (builds and starts a watch)
1. (in another terminal) `grunt karma:dev` (runs the tests)
1. Write your code, including relevant documentation and tests
1. Submit a PR and we'll review

## License

Copyright (C) 2014 Jason Dobry

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
