# &beta;etamax [![Build Status](https://secure.travis-ci.org/robfletcher/betamax.png?branch=master)](http://travis-ci.org/robfletcher/betamax)

Betamax is a tool for mocking external HTTP resources such as web services and REST APIs in your tests. The project was inspired by the [VCR](http://relishapp.com/myronmarston/vcr) library for Ruby.

Betamax is written in [Groovy](http://groovy.codehaus.org/) but is compatible with tests written using [JUnit](http://junit.org/) or [Spock][spock] for applications written in any JVM language.

## Usage

### Record

Add a `@Rule Recorder` property to your test and annotate test methods with `@Betamax`. The first time the test runs any HTTP traffic is recorded to _tape_.

### Playback

Future test runs replay responses from _tape_ without traffic going to the real target. No more 3rd party downtime or rate limits breaking your tests. You can even run your tests offline! Insert different _tapes_ to stub different responses.

### Customize
_Tapes_ are just [YAML](http://www.yaml.org/) files so you can edit them with a text editor, commit to source control, share with your team & use on continuous integration.

## Full documentation

Full documentation can be found on [Betamax's home page][home].

## Project status

The current stable version of Betamax is 1.1 which is available from [Maven Central][maven].

Add `'co.freeside:betamax:1.1'` as a test dependency to your [Gradle](http://gradle.org/), [Ivy](http://ant.apache.org/ivy/), [Grails](http://grails.org/) or [Maven](http://maven.apache.org/) project (or anything that can use Maven repositories).

Development versions are available from [Sonatype][sonatype].

Please get in touch if you have any  feedback. You can raise defects and feature requests via [GitHub issues][issues].

[home]:http://freeside.co/betamax
[issues]:http://github.com/robfletcher/betamax/issues
[maven]:http://repo1.maven.org/maven2/com/github/robfletcher/betamax/
[sonatype]:https://oss.sonatype.org/content/groups/public/com/github/robfletcher/betamax/
[spock]:http://spockframework.org/
[tape]:https://github.com/robfletcher/betamax/blob/master/src/test/resources/betamax/tapes/smoke_spec.yaml
[vcr]:http://relishapp.com/myronmarston/vcr
[yaml]:http://yaml.org/

## Notes on running tests from inside IntelliJ IDEA

Go to _Settings -> Compiler_ and ensure that `*.keystore` appears in the _Resource patterns_ otherwise IDEA will not
make the SSL keystore available on the classpath when tests run.