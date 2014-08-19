title: Teaching our Webdriver Framework new Appium tricks
author:
  name: Daniel Gempesaw
  twitter: dgempesaw
  url: http://blog.danielgempesaw.com
output: index.html
controls: true

--

# The road to Appium
## Teaching our Webdriver Framework new Appium tricks

--

### about

* I work for Sharecare.com

<!-- I work for Sharecare.com, which is a health and wellness -->
<!-- platform. We aim to provide our users with information and -->
<!-- resources to help improve their health.  We've got a social media -->
<!-- aspect of our site so that our users can interact with each -->
<!-- other, and then a CMS portion where we're presenting curated -->
<!-- content like question/answer documents for our users, so our -->
<!-- testing spans a wide range of responsibilities.-->

* as their Software Testing Architect

<!-- My title is Software Testing Architect, which basically means I'm -->
<!-- in charge of all of the in-house tooling that our QA group uses -->
<!-- for testing. Any time we've got a new challenge or set up to -->
<!-- test, I'll either adapt an existing tool to fit the challenge or -->
<!-- create something new as approriate. -->

* [Selenium::Remote::Driver][srd], [Appium][]

<!-- I also moved into the maintainer role for the Perl Webdriver -->
<!-- bindings, and I just started working on the perl Appium bindings -->
<!-- a few weeks ago. -->

[srd]: https://metacpan.org/pod/Selenium::Remote::Driver
[Appium]: https://metacpan.org/pod/Appium

--

### our (pre-mobile) process

* QA group is in charge of e2e tests

<!-- To set the scene a little bit, our process at the beginning of -->
<!-- the year relied heavily on our in-house Webdriver framework. Our -->
<!-- devs worked on features and bugfixes and generate builds for us -->
<!-- to test. We'd use a combination of automated tests for -->
<!-- functionality along with manual verification of the newest -->
<!-- features, right, and each sprint our automated test suite would -->
<!-- grow a little bit. -->

* Established in-house Webdriver framework: Honeydew

<!-- Our in-webdriver framework is named Honeydew, as an amazingly -->
<!-- clever pun off of Cucumber. A couple years ago we had decided to -->
<!-- make our own framework in Perl to give us a bit more flexibility, -->
<!-- and it kept us internally consistent, since many of our other -->
<!-- internal tools were written in perl. Other than being in Perl, -->
<!-- the basics are pretty similar- it accepts Gherkin-style -->
<!-- Given-When-Then feature files and parses them into Webdriver -->
<!-- instructions. We use the feature files not only as tests but also -->
<!-- as readable documentation, and as part of our onboarding for new -->
<!-- hires to help them get familiarized with the site. -->

* Dashboards, nightly monitoring, custom JIRA integrations, email
  reporting, ...

<!-- We were pretty heavily invested in Webdriver - we've got a custom -->
<!-- IDE for authoring our features, similar to Cucumber Pro's -->
<!-- offerings, dashboards, email reporting, nightly monitoring, -->
<!-- integrations with JIRA, our bug tracker, tie-ins with our -->
<!-- TeamCity CI servers, and a substantial adoption of the Gherkin -->
<!-- syntax. -->

--

### huh? what's appium

* mobile is the new focus!

<!-- Earlier this year, Sharecare decided to prioritize mobile - both -->
<!-- for our website and also in the form of new mobile apps. move -->
<!-- fast without breaking things! For me, this meant we needed to -->
<!-- assess the mobile testing frameworks and come up with a workable -->
<!-- solution. -->

* Alternatives vs Webdriver investment

<!-- Like everyone else, we looked at a number of different options, -->
<!-- and Appium came out as the clear choice.  -->