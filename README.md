# README
[![CircleCI](https://circleci.com/gh/maxkadel/my-app.svg?style=svg)](https://app.circleci.com/pipelines/github/maxkadel/my-app?branch=main&filter=all)

[![Rails Style Guide](https://img.shields.io/badge/code_style-rubocop-brightgreen.svg)](https://github.com/rubocop/rubocop-rails)

[![Maintainability](https://api.codeclimate.com/v1/badges/12bb3c8a0da3eaf90f37/maintainability)](https://codeclimate.com/github/maxkadel/my-app/maintainability)

[![Test Coverage](https://api.codeclimate.com/v1/badges/12bb3c8a0da3eaf90f37/test_coverage)](https://codeclimate.com/github/maxkadel/my-app/test_coverage)

### Dependencies
* Ruby 3.0.3
* Rails 7.0.2
* Bundler 2.2.32
* psql 14.2
* npm 8.5.2
* yarn 1.22.17

### Running in development

#### First time setup
* Clone the repository `git clone git@github.com:maxkadel/my-app.git`
* Go into application directory `cd my-app`
* Install gem bundle `bundle install`
* Database creation - ensure you have a Postgres service running
  * `bundle exec rails db:create`
  * `bundle exec rails db:migrate`
* Bring up the application - can change how this occurs in `Procfile.dev`
  * `./bin/dev`
  * Should be able to see the application at http://localhost:3000/

### Running the tests
#### RSpec tests
* All the tests - `bundle exec rspec`
* Single test - `bundle exec rspec spec/path/to/test.rb`

#### Code linter - Rubocop
* To list offenses - `bundle exec rubocop`
* To auto-correct eligible offenses `bundle exec rubocop -a`

#### Handy command line checks
* Validate CircleCI configuration without having to commit it first
```bash
circleci config validate
```
* Run CodeClimate in debug mode, without reporting
```bash
CODECLIMATE_DEBUG=1 codeclimate analyze
```
### Deployment instructions
This application deploys with Heroku. For info on relevant Heroku commands, see https://devcenter.heroku.com/articles/getting-started-with-rails7#heroku-gems

```bash
git push heroku main
heroku run rake db:migrate
```
