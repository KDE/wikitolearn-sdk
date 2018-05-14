# wikitolearn-sdk

This repository contains the dev kit for the WikiToLearn's microservices-oriented stack.
These tools are helpful to work with the stack in a "point and click" fashion or the nearest approximation possible.

## Setup
**Minimum requirements:**

* git
* docker
* docker-compose
* python3
* python3-argcomplete
* python3-yaml

To setup the WikiToLearn dev kit you have to:

1. setup the `kde:` prefix in git with [this](https://community.kde.org/Sysadmin/GitKdeOrgManual#Let_Git_rewrite_URL_prefixes) guide
2. clone this repository
3. (optional) create the `config/repositories.yml` file (an example is `config/repositories.example.yml`)
4. create the `config/config.yml` file (an example is `config/config.example.yml`)
5. run `$ source ./setup-env`
6. run `$ wtl-setup-test` to test if you have fulfilled the requirements and the configurations

## How to manage services

### Build
To build the services you have to run:

`$ wtl-services-build`

This command clone/pull the repositories and build all the services defined into docker-compose files.

### Run
To run the services you have to run:

`$ wtl-services-run`

This command start all the services.

### Data restore
If you need to restore a dump you can run:

`$ wtl-migration-dump-load`

N.B.: a `dump_url` must be set within `config/config.yml` file and the services have to be started.

### Stop
To stop the services you have to run:

$ wtl-services-stop`

This command stop and remove the service containers.

## A note about the repositories directory

WikiToLearn's repositories will be cloned into the `repositories/` directory. This is a non-configurable option.
It allows tools to work with the assumption of the relative location of each repository.

## LICENSE

See [LICENSE](LICENSE) file.
