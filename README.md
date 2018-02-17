# wikitolearn-sdk

This repository contains the dev kit for the WikiToLearn's micro-services
oriented stack.

This tools are helpful to work in the stack in a "point and click" fashion
or the nearest approximation possibile.

## Setup

To setup the WikiToLearn dev kit you have to:

1. clone this repository
3. Install `python3-argcomplete` (for `register-python-argcomplete3`)
4. Install `python3-yaml`
5. create the `config/repositories.yml` file (an example is `config/repositories.example.yml`)
6. run `source ./setup-env`
7. let's play

## repositories/ directory

In the `repositories/` directory will be cloned WikiToLearn's repositories.

This non-configurable is in a fixed place to allow tools to work with the
assumption of the relative location of every repository

## LICENSE

See [LICENSE](LICENSE) file
