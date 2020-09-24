# nodemailer-cli-ng

[![NPM Version](https://img.shields.io/npm/v/nodemailer-cli-ng.svg?style=flat)](https://www.npmjs.org/package/nodemailer-cli-ng)
[![Build Status](https://img.shields.io/travis/vowstar/nodemailer-cli-ng/master.svg?style=flat)](https://travis-ci.org/vowstar/nodemailer-cli-ng)
[![NPM Downloads](https://img.shields.io/npm/dm/nodemailer-cli-ng.svg?style=flat)](https://www.npmjs.org/package/nodemailer-cli-ng)

**This project has been forked from the original nodemailer-cli and updated to latest NPM npackages.**
[original project](https://github.com/fardog/nodemailer-cli)

A command line interface for sending email, wrapped
around [nodemailer][nodemailer].

## Installation

Install the module globally to expose the `nodemailer` command to your
environment.

``` bash
npm install -g nodemailer-cli-latest
```

## Usage

``` bash
$ nodemailer --help

Usage: nodemailer <to> <from> [bodyText] [options]

to           Email address, or comma separated list of email addresses to send mail to.
from         Email address that the message should be from.
bodyText     The plaintext message body.

Options:
   -t, --service    The nodemailer service identifier, if any.
   -u, --username   The SMTP username to use when authenticating.  [local_user_name]
   -p, --password   The plain-text password to use when authenticating.
   -s, --server     The SMTP server that mail will be delivered to.
   -r, --port       The port to use when contacting the SMTP server.
   -n, --nossl      If set, SSL will not be used when sending mail.
   -N, --notls      If set, STARTLS will not be used when sending mail.
   -x, --proxy      If set, a http or socks5/socks4 proxy will be used when sending mail.
   -i, --ignorecert If set, The TLS certification will not be validated.
   -j, --subject    The string to be used as the email's subject.
   --cc             An email address to Carbon Copy. List multiple recipients by appending multiple --cc parameters.
   --bcc            An email address to Blind Carbon Copy. List multiple recipients by appending multiple -bcc parameters.
   --replyTo        An email address that should receive replies if a recipient replies to your message.
   --body           A file to use as the message body.
   --attachment     A path to a file that should be attached. List multiple attachments by appending multiple --attachment parameters.
   -v, --version    Print version and exit.
```

## Environment Variables

Some environment variables can be used in place of CLI options. CLI options
override these environment variables, if used, so these can be thought of as
defaults.

* **SMTP_SERVER** The hostname of the SMTP server to be used.
* **SMTP_PORT** The port on the SMTP server that should be connected to.
* **SMTP_USERNAME** The username to use when authenticating.
* **SMTP_PASSWORD** The password to use when authenticating.
* **SMTP_USE_SSL** Set this to a truth-y value to use SSL.
* **SMTP_USE_TLS** Set this to a truth-y value to use TLS (STARTTLS)
* **SMTP_SERVICE_NAME** This is one of nodemailer's service identifiers, if you

  want it to configure itself automatically.

## History

* **v3.0.0**
  * Update to nodemailer 6.4.11 and add proxy options
* **v2.2.8**
  * Fixed chalk not using `chalk.default` in `/bin/nodemailer.js`
* **v2.2.7**
  * Updated base nodemailer to 4.6.0
  * Minor changes

* **v2.2.6**
  * Updated base nodemailer to 4.4.1
  * Updated ALL dev dependencies to latest available from npm-dview

* **v2.2.4**
  * fixed README issues

* **v2.2.0**
  * Updated non-dev npm dependencies

* **v2.1.1**
  * Updates nodemailer dependency — _[@mistralol][]_
  * Moves devDependencies out of dependencies — _[@fardog][]_

* **v2.1.0**
  * Updates to support multiple `--attachment` parameters — _[@mistralol][]_

* **v2.0.1**
  * Fixes typo that would cause env vars to be ignored for useTLS —
    _[@mistralol][]_

* **v2.0.0**
  * Package Updates, fixes — _[@mistralol][]_,
    [#6](https://github.com/fardog/nodemailer-cli/pull/6)
    * Increased minimum node version to 4
    * Added option to ignore STARTTLS
    * Added option to ignore certificate
    * Fix missing server alias from the command line
    * Bring all deps up to current versions
  * Reformat README — _[@fardog][]_

* **v1.0.3**
  * Fixes `undefined` being passed for auth when no auth is specified. Thanks

      to [@mistralol][].

* **v1.0.2**
  * Removes [colors][colors] in favor of [chalk][chalk].

* **v1.0.1**
  * Updates dependencies and adds dependency badge.

* **v1.0.0**
  * Adds linter, gulp for running tests.

* **v0.3.0**
  * Adds tests, and moves to a more test-able architecture.

      Replaces [nomnom][nomnom] with [minimist][minimist], and adds a custom
      validator for CLI options.

* **v0.2.0**
  * Adds additional fields: cc, bcc, replyTo. Allows multiple emails as a

      comma-separated list in fields where it's sensible.

* **v0.1.2**
  * Adds preferGlobal to the package, to warn if installed locally.

* **v0.1.1**
  * Adds flag to print version of cli and nodemailer.

* **v0.1.0**
  * Cleans up command line switches, and adds support for attachments.

* **v0.0.1**
  * Initial Release.

[nodemailer]: https://github.com/andris9/Nodemailer
[nomnom]: https://www.npmjs.org/package/nomnom
[minimist]: https://www.npmjs.org/package/minimist
[colors]: https://www.npmjs.org/package/colors
[chalk]: https://www.npmjs.org/package/chalk
[@fardog]: https://github.com/fardog
[@mistralol]: https://github.com/mistralol

## The MIT License (MIT)

Copyright (c) 2014 Nathan Wittstock

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
