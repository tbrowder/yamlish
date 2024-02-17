[![Build Status](https://travis-ci.org/tbrowder/yamlish.svg?branch=master)](https://travis-ci.org/tbrowder/yamlish)

NAME
====

YAMLish - a YAML parser/emitter written in pure raku

DESCRIPTION
===========

This is a YAML parser written in pure-raku. It aims at being feature complete (though there still a few features left to implement). Patches are welcome.

INSTALLATION
============

```console
$ zef install YAMLish
```

EXPORTED SUBS
=============

  * `load-yaml(Str $input, ::Grammar:U :$schema = ::Schema::Core, :%tags)`

  * `load-yamls(Str $input, ::Grammar:U :$schema = ::Schema::Core, :%tags)`

  * `save-yaml($document, :$sorted = True)`

  * `save-yamls(**@documents, :$sorted = True)`

Example use for a configuration file
====================================

The file uses simple key/value lines:

    # key: value
    lang: en
    lat: 46.12345
    lon: -82.6231

In your code:

    use YAMLish;
    my $str = "config.yml".IO.slurp:
    my %conf = load-yaml $str;
    say %conf<lang>; # OUTPUT: en
    say %conf<lat>;  # OUTPUT: 46.12345
    say %conf<lon>;  # OUTPUT: -82.6231

TODO
====

Please have a look at [./TODO.md](./TODO.md)

AUTHOR
======

Leon Timmermans

LICENSE
=======

Artistic License 2.0

