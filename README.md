# Simple Scala Set Up for Robocode

This is a Scala project in which you can write and compile Robocode robots.

To then be able to run them in Robocode itself, there are two things to do:

1. Add the Scala library as a dependency to the robotcode shell script; and

2. Add your _target/classes_ path to the "Developer Options" in Robocode itself.

Details below.

Once you've done that you can `sbt` and `compile` away.  You can restart a battle in Robocode and it appears to pick up changes.

This repository contains a _sample.ScalaMyFirstRobot_ which is the same as _MyFirstRobot_ but syntactically ported to Scala.

## Scala library

In my installation of _robocode_, I coped  _robocode.sh_ and added in the path to Scala std lib:

    robocode$ cat scalarobocode.sh
    #!/bin/sh
    #
    # Copyright (c) 2001-2014 Mathew A. Nelson and Robocode contributors
    # All rights reserved. This program and the accompanying materials
    # are made available under the terms of the Eclipse Public License v1.0
    # which accompanies this distribution, and is available at
    # http://robocode.sourceforge.net/license/epl-v10.html
    #

    export SCALA_LIB=$HOME/.ivy2/cache/org.scala-lang/scala-library/jars/scala-library-2.11.7.jar
    pwd=`pwd`
    cd "${0%/*}"
    java -Xmx512M -cp libs/robocode.jar:$SCALA_LIB robocode.Robocode $*
    cd "${pwd}"

## Robocode Developer Options

After launching Robocode, select _Options_ > _Preferences_, and in _Developer Options_, hit _Add_ and pick the path to your compiled robots:

![prefs](https://api.monosnap.com/rpc/file/download?id=3UmtafwiylYHVBqwObVYbUlGJH1N5B)
