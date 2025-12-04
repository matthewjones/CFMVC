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

FW/1 is setup to run tests using [GitHub Actions] see .github/workflows/ using using Java 11 for (lucee@6, lucee@5, adobe@2023, adobe@2021, adobe@2018), and Java 21 for (lucee@6, lucee@7, adobe@2025, boxlang) workflow files.

Tests were run with TestBox 6.4.0; current stable versions under openjdk11 (Lucee@5.4.8.2, Lucee@6.2.3+35, Adobe@2018.0.19+330149, Adobe@2021.0.22+330451, Adobe@2023.0.16+330828); current stable versions under openjdk21 (Lucee@6.2.3+35, Lucee@7.0.0+395, Adobe@2025.0.04+331512, Boxlang@1.7.0+43 *1.8.0-snapshot+3925 required to pass route tests)

To run tests locally, you'll need [CommandBox](https://www.ortussolutions.com/products/commandbox) installed.

Then run `box install` once to install the dependencies (TestBox is the only one currently).

Then start a server on port 8500 with your choice of CFML engine ( javaVersion=openjdk11 ), e.g.,

    box server start cfengine={{engine}} port=8500

    box server start cfengine={{engine}} port=8500 javaVersion=openjdk21

This will open a browser, running the FW/1 "Introduction" app.

You can then run the tests:

    box testbox run verbose=false

If you get any failures, you can run this with more verbose, but still compact output:

    box testbox run reporter=mintext

# Copyright and License

Copyright (c) 2009-2025, Sean Corfield (and others -- see individual files for additional copyright holders). All rights reserved.
The use and distribution terms for this software are covered by the Apache Software License 2.0 (http://www.apache.org/licenses/LICENSE-2.0) which can also be found in the file LICENSE at the root of this distribution and in individual licensed files.
By using this software in any fashion, you are agreeing to be bound by the terms of this license. You must not remove this notice, or any other, from this software.
