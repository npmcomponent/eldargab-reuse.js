*This repository is a mirror of the [component](http://component.io) module [eldargab/reuse.js](http://github.com/eldargab/reuse.js). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/eldargab-reuse.js`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# reuse.js

Funky way to extend your objects

## usage

``` javascript
obj.use = require('reuse')

// mix some properties
obj.use({
  root: 'public'
})

// or
function root (that, dir) {
  that.root = dir
}
obj.use(root, 'public')

// in both cases
obj.should.have.property('root').equal('public')
```

There is also a weird thing. Passing in a function with enumerable properties on
prototype is the same as `.use(fn.protototype)`

``` javascript
function Klass () {
  this.a = 'a'
}

Klass.prototype.foo = 'foo'

obj.use(Klass)

obj.should.have.property('foo').equal('foo')
obj.should.not.have.property('a')
```

## Installation

Via npm

```
npm install reuse
```

To run tests install dev dependecies and run `npm test` command

```
npm install -d
npm test
```

## License

MIT
