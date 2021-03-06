# Puppet MySQL hardening

[![Puppet Forge](https://img.shields.io/puppetforge/dt/hardening/mysql_hardening.svg)][1]
[![Build Status](http://img.shields.io/travis/hardening-io/puppet-mysql-hardening.svg)][2]
[![Gitter Chat](https://badges.gitter.im/Join%20Chat.svg)][3]

## Description

This Puppet module provides hardening configuration for MySQL.

## Requirements

* Puppet
* Supported module: `puppetlabs/mysql` (v2.x.x)


## Parameters

none

## Usage

If you use `puppetlabs/mysql`:

    # Configure MySQL Server as you normally would:
    class { 'mysql::server':
      # ...
    }

    # now include hardening:
    class { 'mysql_hardening':  provider => 'puppetlabs/mysql'}

## Local Testing

For local testing you can use vagrant and Virtualbox of VMWare to run tests locally. You will have to install Virtualbox and Vagrant on your system. See [Vagrant Downloads](http://downloads.vagrantup.com/) for a vagrant package suitable for your system. For all our tests we use `test-kitchen`. If you are not familiar with `test-kitchen` please have a look at [their guide](http://kitchen.ci/docs/getting-started).

Next install test-kitchen:

```bash
# Install dependencies
gem install bundler
bundle install

# Fetch tests
bundle exec thor kitchen:fetch-remote-tests

# Do lint checks
bundle exec rake lint

# Do spec checks
bundle exec rake spec

# fast test on one machine
bundle exec kitchen test default-ubuntu-1204

# test on Debian-based machines
bundle exec kitchen test

# for development
bundle exec kitchen create default-ubuntu-1204
bundle exec kitchen converge default-ubuntu-1204
```

For more information see [test-kitchen](http://kitchen.ci/docs/getting-started)

## Contributors + Kudos

* Edmund Haselwanter [ehaselwanter](https://github.com/ehaselwanter)
* Christoph Hartmann [chris-rock](https://github.com/chris-rock)
* Matthew Haughton [3flex](https://github.com/3flex)
* Patrick Meier [atomic111](https://github.com/atomic111)

## License and Author

* Author:: Dominik Richter <dominik.richter@googlemail.com>
* Author:: Deutsche Telekom AG

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

[1]: https://forge.puppetlabs.com/hardening/mysql_hardening
[2]: http://travis-ci.org/hardening-io/puppet-mysql-hardening
[3]: https://gitter.im/hardening-io/general
