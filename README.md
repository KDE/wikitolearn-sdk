# wikitolearn-sdk

This repository contains the dev kit for the WikiToLearn's microservices-oriented stack.

This tools are helpful to work with the stack in a "point and click" fashion
or the nearest approximation possibile.

## Setup

To setup the WikiToLearn dev kit you have to:

1. clone this repository
3. Install `python3-argcomplete` (for `register-python-argcomplete3`)
4. Install `python3-yaml`
5. create the `config/repositories.yml` file (an example is `config/repositories.example.yml`)
6. create the `config/config.yml` file (an example is `config/config.example.yml`)
7. run `source ./setup-env`

## Build, run and manage services

To build the services you have to run:

``` ./bin/wtl-services-build ```

This command clone/pull the repositories and build all the services defined into docker-compose files.

To run the services you have to run:

``` ./bin/wtl-services-run ```

This command start all the services.

If you need to restore a dump you can run:

``` ./bin/wtl-dump-load ```

N.B.: a `dump_url` must be set within `config/config.yml` file and the services have to be started.

To stop the services you have to run:

``` ./bin/wtl-services-stop ```

This command stop and remove the service containers.

## A note aboyt the repositories directory

In the `repositories/` directory will be cloned the WikiToLearn's repositories.

This non-configurable is in a fixed place to allow tools to work with the
assumption of the relative location of every repository

## LICENSE

See [LICENSE](LICENSE) file.
