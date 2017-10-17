# React

Event-driven, non-blocking I/O with PHP.

[![Build Status](https://secure.travis-ci.org/reactphp/react.png?branch=master)](http://travis-ci.org/reactphp/react)

### Notice - (May 25th, 2014)

As of 2014-05-25 we have reversed roles of this and the component repositories. 
Instead of reactphp/react being the master code repository it is now the sum of React's components. 
All PRs should be made against their corresponding repository found in [/reactphp](https://github.com/reactphp). 

## What is it?

React is a low-level library for event-driven programming in PHP. At its core
is an event loop, on top of which it  provides low-level utilities, such as:
Streams abstraction, async dns resolver, network client/server, http
client/server, interaction with processes. Third-party libraries can use these
components to create async network clients/servers and more.

The event loop is based on the reactor pattern (hence the name) and strongly
inspired by libraries such as EventMachine (Ruby), Twisted (Python) and
Node.js (V8).

## Design goals

* Usable with a bare minimum of PHP extensions, add more extensions to get better performance.
* Provide a standalone event-loop component that can be re-used by other libraries.
* Decouple parts so they can be replaced by alternate implementations.

React is non-blocking by default. Use workers for blocking I/O.

## High-level abstractions

There are two main abstractions that make dealing with control flow a lot more
manageable.

* **Stream:** A stream represents an I/O source (ReadableStream) or
  destination (WritableStream). These can be used to model pipes, similar
  to a unix pipe that is composed of processes. Streams represent very large
  values as chunks.

* **Promise:** A promise represents an eventual return value. Promises can be
  composed and are a lot easier to deal with than traditional CPS callback
  spaghetti and allow for almost sane error handling. Promises represent the
  computation for producing single values.

You should use these abstractions whenever you can.

## Getting started

React consists of individual components.
This means that instead of installing something like a "React framework", you actually
pick only the components that you need.

The recommended way to install these components is [through Composer](http://getcomposer.org).
[New to Composer?](http://getcomposer.org/doc/00-intro.md)

For example, this may look something like this:

```bash
$ composer require react/event-loop react/http
```

For more details, check out [React's homepage](http://reactphp.org) for
quickstart examples and usage details.

## Documentation

Superficial documentation can be found in the README files of the individual
components. See `vendor/react/*/src/README.md`.

## Community

Check out #reactphp on irc.freenode.net. Also follow
[@reactphp](https://twitter.com/reactphp) on twitter.

## Tests

To run the test suite, you first need to clone this repo and then install all
dependencies [through Composer](https://getcomposer.org):

```bash
$ composer install
```

To run the test suite, go to the project root and run:

```bash
$ php vendor/bin/phpunit
```

## License

MIT, see LICENSE.
