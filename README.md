<div align="center">
    <a href="https://reactphp.org"><img src="https://rawgit.com/reactphp/branding/master/reactphp-logo.svg" alt="ReactPHP Logo" width="160"></a>
</div>
    
<br>
    
<div align="center">
    <strong>Event-driven, non-blocking I/O with PHP.</strong>
</div>

<br>

<div align="center">
    <a href="https://travis-ci.org/reactphp/react"><img src="https://travis-ci.org/reactphp/react.svg?branch=master" alt="Build Status"></a>
</div>

<br>

ReactPHP is a low-level library for event-driven programming in PHP. At its core
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

ReactPHP is non-blocking by default. Use workers for blocking I/O.

## Core Components

* **EventLoop**
  ReactPHP's core reactor event-loop.
  [Read the documentation](https://github.com/reactphp/event-loop)

* **Stream**
  Event-driven readable and writable streams for non-blocking I/O in ReactPHP.
  [Read the documentation](https://github.com/reactphp/stream)

* **Promise**
  Promises/A implementation for PHP.
  [Read the documentation](https://github.com/reactphp/promise)


## Network Components

* **Socket**
  Async, streaming plaintext TCP/IP and secure TLS socket server and client connections for ReactPHP.
  [Read the documentation](https://github.com/reactphp/socket)

* **Datagram**
  Event-driven UDP client and server sockets for ReactPHP.
  [Read the documentation](https://github.com/reactphp/datagram)

## Protocol Components

* **HTTP**
  Event-driven, streaming plaintext HTTP and secure HTTPS server for ReactPHP.
  [Read the documentation](https://github.com/reactphp/http)

* **HTTPClient**
  Event-driven, streaming HTTP client for ReactPHP.
  [Read the documentation](https://github.com/reactphp/http-client)

* **DNS**
  Async DNS resolver for ReactPHP.
  [Read the documentation](https://github.com/reactphp/dns)

## Utility Components

* **Cache**
  Async caching for ReactPHP.
  [Read the documentation](https://github.com/reactphp/cache)

* **ChildProcess**
  Library for executing child processes.
  [Read the documentation](https://github.com/reactphp/child-process)

* **PromiseTimer**
  Trivial timeout implementation for ReactPHP's Promise lib.
  [Read the documentation](https://github.com/reactphp/promise-timer)

* **PromiseStream**
  The missing link between Promise-land and Stream-land, built on top of ReactPHP.
  [Read the documentation](https://github.com/reactphp/promise-stream)


## Built with ReactPHP

* **Thruway**
  PHP Client and Router Library for Autobahn and WAMP (Web Application Messaging
  Protocol) for Real-Time Application Messaging
  [voryx/Thruway](https://github.com/voryx/Thruway)

* **PPM - PHP Process Manager**
  PPM is a process manager, supercharger and load balancer for modern PHP
  applications.
  [php-pm/php-pm](https://github.com/php-pm/php-pm)

* **php-ar-drone**
  🚁 Port of node-ar-drone which allows user to control a Parrot AR Drone over
  PHP
  [jolicode/php-ar-drone](https://github.com/jolicode/php-ar-drone)

* **Ratchet**
  Asynchronous WebSocket server
  [ratchetphp/Ratchet](https://github.com/ratchetphp/Ratchet)

* **Predis\Async**
  Asynchronous PHP client library for Redis built on top of ReactPHP
  [nrk/predis-async](https://github.com/nrk/predis-async)

* **clue/redis-server**
  A Redis server implementation in pure PHP
  [clue/redis-server](https://github.com/clue/php-redis-server)

[And many more on our wiki page »](https://github.com/reactphp/react/wiki/Users)

## Articles

* **Sergey Zhuk**
  A series of articles covering ReactPHP: from the basics to the real
  application examples.
  [sergeyzhuk.me](http://sergeyzhuk.me/reactphp-series)

* **Cees-Jan Kiewiet**
  Blog series about several ReactPHP components and how they work.
  [blog.wyrihaximus.net](http://blog.wyrihaximus.net/categories/reactphp-series/)

* **Loïc Faugeron**
  Super Speed Symfony - ReactPHP.
  [gnugat.github.io](https://gnugat.github.io/2016/04/13/super-speed-sf-react-php.html)

* **Marc J. Schmidt**
  Bring High Performance Into Your PHP App (with ReactPHP).
  [marcjschmidt.de](http://marcjschmidt.de/blog/2014/02/08/php-high-performance.html)

## Talks

* **Christian Lück**
  [Pushing the limits with ReactPHP](https://www.youtube.com/watch?v=-5ZdGUvOqx4)

* **Jeremy Mikola**
  [Async PHP With React](https://www.youtube.com/watch?v=s6xrnYae1FU)

* **Igor Wiedler**
  [Event-driven PHP](https://www.youtube.com/watch?v=MWNcItWuKpI)

## Getting started

ReactPHP consists of individual components.
This means that instead of installing something like a "ReactPHP framework", you actually
pick only the components that you need.

The recommended way to install these components is [through Composer](http://getcomposer.org).
[New to Composer?](http://getcomposer.org/doc/00-intro.md)

For example, this may look something like this:

```bash
$ composer require react/event-loop react/http
```

For more details, check out [ReactPHP's homepage](https://reactphp.org) for
quickstart examples and usage details.

See also the combined [changelog for all ReactPHP components](https://reactphp.org/changelog.html)
for details about version upgrades.

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

The test suite also contains a number of functional integration tests that rely
on a stable internet connection. Due to the vast number of integration tests,
these are skipped by default on Travis CI. If you also do not want to run these,
they can simply be skipped like this:

```bash
$ php vendor/bin/phpunit --exclude-group internet
```

## License

MIT, see LICENSE.
