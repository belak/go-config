# go-config

A simple, no frills config system providing a sane interface over defaults,
config files environment variables, and pflags.

## Goals

Allow for seamlessly integrating config in a go project, without having to jump
through a ton of hoops each time.

This project aims to integrate the [pflag](https://github.com/spf13/pflag) and
[toml](https://github.com/BurntSushi/toml) packages, as well as supporting
built-in config formats such as json.

### Optional Goals

If possible, anything (other than pflags) which requires an external dependency
should be optional. There should be interfaces for everything (config formats,
flags) if at all possible.

It would also be nice to be able to extend this system to support reading into
different variable types, perhaps with `encoding.TextUnmarshaler` or something
similar.

## Interface

The interface will be very similar to the `flag` package, as explicit makes this
simpler, instead of focusing on reflection and other black magic.

## Config preference

Each of the following has a higher precidence over the tier below it:

* Command line flags
* Environment variables
* Config files
* Default
