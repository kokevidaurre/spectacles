<img src="https://github.com/spectacles-ci/spectacles/raw/master/docs/img/logo.png" width="600">

[![CircleCI](https://circleci.com/gh/spectacles-ci/spectacles.svg?style=svg)](https://circleci.com/gh/spectacles-ci/spectacles)
[![codecov](https://codecov.io/gh/spectacles-ci/spectacles/branch/master/graph/badge.svg)](https://codecov.io/gh/spectacles-ci/spectacles)
[![downloads](https://img.shields.io/pypi/dm/spectacles)](https://img.shields.io/pypi/dm/spectacles)

## What is Spectacles?

**Spectacles is a command-line, continuous integration tool for Looker and LookML.** Spectacles runs **validators** which perform a range of tests on your Looker instance and your LookML. Each validator interacts with the Looker API to run tests that ensure your Looker instance is running smoothly. You can run Spectacles locally during LookML and content development, or you can run it in production as a continuous integration pipeline.

You can run the following validators as subcommands (e.g. `spectacles sql`):

- [**SQL** validation](https://docs.spectacles.dev/tutorials/validators#the-sql-validator) - tests for database errors or invalid SQL
- [**Assert** validation](https://docs.spectacles.dev/tutorials/validators#the-assert-validator) - runs [LookML/data tests](https://docs.looker.com/reference/model-params/test)
- **Content** validation _(coming soon)_
- **Linting** _(coming soon)_

## Documentation

You can find detailed documentation on our website: [docs.spectacles.dev](https://docs.spectacles.dev).

## Installation

Spectacles is distributed on PyPi and is easy to install with pip:

```shell
pip install spectacles
```

## Why we built this

Occasionally, when we make changes to LookML or our data warehouse, we break downstream experiences in Looker. For example:

* We change the name of a database column without changing the corresponding `sql` field in our Looker view, leaving our users with a database error when using that field.
* We add an invalid join to an explore that fans out our data, inflating a key metric that drives our business without realising.
* We make changes to LookML without remembering to check the Content Validator for errors, disrupting Dashboards and Looks that our users rely on
* We give a new dimension a confusing name, causing other developers in our team to spend extra time trying to figure out how it should be used.

We believe in the power of continuous integration for analytics. We believe that automated testing should catch these errors before they are ever pushed to production. Automated testing allows developers to maintain their speed of development high, without compromising on the quality of their code or the quality data they produce.

We wanted a single tool to perform these checks for us and establish baseline performance expectations for our Looker instances. We built Spectacles to enhance the business intelligence layer of analytics CI pipelines.

## Community

Have a question or just want to chat Spectacles and Looker? [Join us in Slack.](https://join.slack.com/t/spectacles-ci/shared_invite/zt-akmm4mo6-XnPcUUaG3Z5~giRc_5JaUQ)
