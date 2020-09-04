# Backend Development

This is a template to get you started with the basics in backend development for Datahike. Please take a look at the source code and the tests to get you running.

## Status
<p align="center">
<a href="https://clojurians.slack.com/archives/CB7GJAN0L"><img src="https://img.shields.io/badge/clojurians%20slack-join%20channel-blueviolet"/></a>
<a href="https://clojars.org/io.replikativ/datahike"> <img src="https://img.shields.io/clojars/v/io.replikativ/datahike.svg" /></a>
<a href="https://circleci.com/gh/replikativ/datahike"><img src="https://circleci.com/gh/replikativ/datahike.svg?style=shield"/></a>
<a href="https://github.com/replikativ/datahike/tree/development"><img src="https://img.shields.io/github/last-commit/replikativ/datahike/development"/></a>
<a href="https://versions.deps.co/replikativ/datahike-backend-template" title="Dependencies Status"><img src="https://versions.deps.co/replikativ/datahike-backend-template/status.svg" /></a>
</p>

## Prerequisites
Please read the [official docs for backend development in the Datahike repository](https://github.com/replikativ/datahike/blob/master/doc/backend-development.md).

## Testing
This document tries to provide guardrails for consistency for datahike backends. We want to achieve that by giving advice on how to do testing so that everyone is able to test your backend with a new release of Datahike. Ideally there is a CI implemented so it can be run with updated dependencies and shows the current status as a badge on the front page like the one for CircleCI on top.

It would be very beneficial if you could introduce working integration testing locally and via CI on the basis of the provided templates. That makes it easier for everybody to check if a new release of Datahike is breaking your backend. Of course you can use technologies you prefer.

We are currently running our integration tests with a script at `./bin/run-integrationtests`. This script could start containers to test against. Does your project need an API account for testing? Then please describe a way to obtain test capabilities in this README. Additional unit tests are of course very welcome. Run your tests with `lein test` if you don't need any dependencies to start. Using the `bin/run-integrationtests` script is easiest and you could just enter your way of running the test in there.

## Releasing
It is best to make your backend available via [Clojars](https://clojars.org/) so everybody finds it where it is expected. We recommend to release a new version automatically when merging or committing into master. Please have a look at the file `./circleci/config.yaml` to understand how that can be achieved. We propose CircleCI because we are using that but you are of course welcome to use whatever you prefer. Deploy to Clojars with `lein deploy` or use the CI-step we provide with the step `lein/deploy-snapshot` and `lein/deploy-release`. You need to add your Clojars token and username as environment variable in your CircleCI project in case you are using the provided CI-configuration.

## Licensing
Datahike is licensed under [Eclipse Public License - v 1.0](https://github.com/replikativ/datahike/blob/master/LICENSE). Your backend should have a permissive license to be beneficial to all possible users.
