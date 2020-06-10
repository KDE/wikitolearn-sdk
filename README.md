# wikitolearn-sdk

This repository contains the dev kit for the WikiToLearn's microservices-oriented stack.
These tools are helpful to work with the stack in a "point and click" fashion or the nearest approximation possible.

## Setup

**Minimum requirements:**

- git
- docker
- docker-compose
- python3

Setup these tools in the recommended ways for your system. Then to setup the WikiToLearn dev kit you have to:

1. setup the `kde:` prefix in git with [this](https://community.kde.org/Sysadmin/GitKdeOrgManual#Let_Git_rewrite_URL_prefixes) guide
2. clone this repository: `git clone kde:wikitolearn/wikitolearn-sdk`
3. (optional) create a `config/repositories.yml` file (an example is `config/repositories.example.yml`)
4. (recommended) create a `config/config.yml` file (an example is `config/config.example.yml`)
5. install python dependencies; you can do it globally or, better, in a [virtual environment](https://virtualenvwrapper.readthedocs.io/en/latest/): `pip3 install -r requirements.txt`
6. run `$ source ./setup-env`
7. run `$ wtl-setup-test` to test if you have fulfilled the requirements and the configurations

## How to manage services

If it's the first time you are here, you have to execute the steps below in this order to get something running:

1. Build
2. Run
3. (do it once) Create dummy dataset/Restore a dump
4. Run (again, to get the services up is something went wrong)
5. Open http://localhost:13000 to see the frontend

### Build

To build the services you have to run:

```sh
wtl-services-build
```

This command clone/pull the repositories of WikiToLearn's services and build all these services as defined into their docker-compose files. The first time it takes a long time.

### Run

To run the services you have to run:

```sh
wtl-services-run
```

This command start all the services.

### Data restore

If you need to restore a dump (data extracted from the official WikiToLearn website) you can run:

```sh
wtl-migration-dump-load
```

N.B.: a `dump_url` must be set within `config/config.yml` file and the services have to be started.

If you don't need (or don't have) real data, to get started you can also use a fake dataset

### Dummy dataset

To setup some initial data you have to run:

```sh
wtl-dummy-dataset
```

This command call the appropriate services to populate the databases with example data and user accounts.

N.B.: fake users and passwords are printed to the console. Take note if you want to login.

### Stop

To stop the services you have to run:

```sh
wtl-services-stop
```

This command stop and remove the service containers.

## A note about the repositories directory

WikiToLearn's repositories will be cloned into the `repositories/` directory. This is a non-configurable option.
It allows tools to work with the assumption of the relative location of each repository.

## Make changes to existing services

If you want to make changes to the services' source code, inside the `repositories` directory you will find each service repository. To see your changes live you have to re-build services and re-run them with the commands seen before.

After having changed your working directory to one of the microservices you will be able to save and share your modifications as you would usually do with `git`: each microservice's folder is itself a reference to a git repository, locally copied with `git clone`: exactly like this SDK repository.

N.B.: since the folders in `repositories` are indeed repositories themselves, this SDK repository doesn't have to (and will not) track changes applied in those folders. So be sure to be inside the correct repository affected by your changes when you want to commit them.

## LICENSE

See [LICENSE](LICENSE) file.
