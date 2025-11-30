# CFMVC (ColdFusion Model View Controller Framework)

This directory is a complete web application and expects to live in its own
webroot if you plan to run the applications within it. To use CFMVC in a separate
webroot you can either copy the `framework` directory to that webroot or add a mapping
for `/framework` to the `framework` folder inside this FW/1 directory. Note that since
your `Application.cfc` needs to extend `framework.one`, you have to add the mapping
in your admin - you can't just use a per-application mapping.

# Resources

**Project home:** https://github.com/framework-one/fw1

**Documentation / Wiki:** http://framework-one.github.io/documentation/ / http://github.com/framework-one/fw1/wiki

**Blog:** http://framework-one.github.io

**Support:** http://groups.google.com/group/framework-one/

**Chat:** The [CFML team Slack](http://cfml-slack.herokuapp.com) has a [dedicated #fw1 channel](https://cfml.slack.com/messages/fw1/).

# Running the Tests

FW/1 is setup to run tests using [GitHub Actions](https://github.com/framework-one/fw1/actions/workflows/fw1_java11.yml) using the `fw1_java11.yml` and `fw1_boxlang.yml` workflow files.

To run tests locally, you'll need [CommandBox](https://www.ortussolutions.com/products/commandbox) installed.

Then run `box install` once to install the dependencies (TestBox is the only one currently).

Then start a server on port 8500 with your choice of CFML engine ( javaVersion=openjdk11 ), e.g.,

    box server start cfengine=lucee@6 port=8500

    box server start cfengine=lucee@5 port=8500

    box server start cfengine=adobe@2018 port=8500

    box server start cfengine=adobe@2021 port=8500

    box server start cfengine=adobe@2023 port=8500

    box server start cfengine=adobe@2025 port=8500 javaVersion=openjdk21_jdk

This will open a browser, running the FW/1 "Introduction" app.

You can then run the tests:

    box testbox run verbose=false

If you get any failures, you can run this with more verbose, but still compact output:

    box testbox run reporter=mintext

# Copyright and License

Copyright (c) 2009-2024, Sean Corfield (and others -- see individual files for additional copyright holders). All rights reserved.
The use and distribution terms for this software are covered by the Apache Software License 2.0 (http://www.apache.org/licenses/LICENSE-2.0) which can also be found in the file LICENSE at the root of this distribution and in individual licensed files.
By using this software in any fashion, you are agreeing to be bound by the terms of this license. You must not remove this notice, or any other, from this software.
