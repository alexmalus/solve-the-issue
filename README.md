## What is SolveIT?

Open source issue tracking system.

README structure inspired by https://github.com/thepracticaldev/dev.to/blob/master/README.md
Strongly encourage to check them out!

## Table of Contents

- [Codebase](#codebase)
  - [The stack](#the-stack)
  - [Engineering standards](#engineering-standards)
    - [Style guide](#style-guide)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Standard Installation](#standard-installation)
  - [Docker Installation](#docker-installation)
  - [Starting the application](#starting-the-application)
- [Product Roadmap](#product-roadmap)
- [Core Team Members](#core-team)
- [License](#license)

## Codebase

### The stack

We run on a Rails backend with mostly vanilla JavaScript on the front end. 

### Engineering standards

#### Style guide

This project follows [thoughtbot's Ruby Style Guide](https://github.com/thoughtbot/guides/blob/master/style/ruby/.rubocop.yml), using [Rubocop](https://github.com/bbatsov/rubocop) along with [Rubocop-Rspec](https://github.com/backus/rubocop-rspec) as the code analyzer. If you have Rubocop installed with your text editor of choice, you should be up and running.

## Getting Started

This section provides a high-level requirement & quick start guide.

### Prerequisites

- [Ruby](https://www.ruby-lang.org/en/): we recommend using [rvm](https://rvm.io/) to install the Ruby version listed on the badge.
- [PostgreSQL](https://www.postgresql.org/) 9.4 or higher.
- [Webpacker](https://github.com/rails/webpacker)
  - [YARN](https://yarnpkg.com/en/)
  - [NodeJS](https://nodejs.org/en/)

### Standard Installation

0.  Make sure all the prerequisites are installed.
1.  Fork solve_it repository, ie. https://github.com/alexmalus/solve_it/fork
2.  Clone your forked repository, ie. `git clone https://github.com/<your-username>/solve_it.git`
3.0.  `gem install foreman`
3.1.  `bundle exec rails webpacker:install`
4.  Setup your database
    - Create `config/database.yml` by copying from the provided template (i.e. `cp config/database.yml.sample config/database.yml`)
    - Update the `config/database.yml` file if needed.
5.  Set up your environment variables/secrets
    - Take a look at `.env.example`. This file lists all the `ENV` variables we use and provides a fake default for any missing keys.
    - You do not need "real" keys for basic development. Some features require certain keys, so you may be able to add them as you go.
6.  Run `bin/setup`
7.  That's it! Run `bin/rails server` to start the application and head to `http://localhost:3000/`

### Docker Installation

TODO

#### Starting the application

We're mostly a Rails app, with a bit of Webpack sprinkled in. **For most cases, simply running `bin/rails server` will do.** If you're working with Webpack though, you'll need to run the following:

- Run **`bin/startup`** to start the server, Webpack, and our job runner `delayed_job`. `bin/startup` runs `foreman start -f Procfile.dev` under the hood.
- `alias start="bin/startup"` makes this even faster. 😊
- If you're using **`pry`** for debugging in Rails, note that using `foreman` and `pry` together works, but it's not as clean as `bin/rails server`.

Here are some singleton commands you may need, usually in a separate instance/tab of your shell.

- Running the job server (if using `bin/rails server`) -- this is mostly for notifications and emails: **`bin/rails jobs:work`**
- Clearing jobs (in case you don't want to wait for the backlog of jobs): **`bin/rails jobs:clear`**

## Product Roadmap

TODO

## Core team

- [@alexmalus](https://github.com/alexmalus)

## License

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. Please see the [LICENSE](./LICENSE.md) file in our repository for the full text.

Like many open source projects, we require that contributors provide us with a Contributor License Agreement (CLA). By submitting code to the DEV project, you are granting us a right to use that code under the terms of the CLA.

Our version of the CLA was adapted from the Microsoft Contributor License Agreement, which they generously made available to the public domain under Creative Commons CC0 1.0 Universal.