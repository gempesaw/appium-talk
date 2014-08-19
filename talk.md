title: Teaching our Webdriver Framework new Appium tricks
author:
  name: Daniel Gempesaw
  twitter: dgempesaw
  url: http://danielgempesaw.com/appium-talk
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
<!-- a few weeks ago. Also, if there are any Emacs users in the room, -->
<!-- I maintain a couple emacs packages, including -->
<!-- ido-vertical-mode. Any bugs in that are completely my fault :D-->

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

* mobile is the new focus! so, how do we test it?

<!-- Earlier this year, Sharecare decided to prioritize mobile - both -->
<!-- for our website and also in the form of new mobile apps. move -->
<!-- fast without breaking things! For me, this meant we needed to -->
<!-- assess the mobile testing frameworks and come up with a workable -->
<!-- solution. -->

* Need to test Android and iOS apps; QA engineers on OS X & Windows

<!-- Like everyone else, we looked at a number of different -->
<!-- options. We looked briefly into KiF, and we surveyed our options -->
<!-- as well. Appium fit us pretty well for a few reasons  -->

* Webdriver investment and cross-platform requirements? Appium!

<!-- In the QA group, we had been keeping tabs on Appium since a few -->
<!-- months before the 2013 SeConf, but our devs hadn't heard of -->
<!-- it. We looked into KiF and surveyed our other options, but Appium -->
<!-- seemed like the obvious choice the whole time. -->

<!-- Since it'd be the QA engineers in charge of testing, we'd need to -->
<!-- be the ones familiar with the test framework - while we might not -->
<!-- be developers by name, our QA engineers all possess the analytic -->
<!-- capabilities to . Working with one tool for both iOS and -->
<!-- Android would hopefully make troubleshooting much easier. -->

--

### installation and set up

<!-- So, if you're just getting started with installing Appium, there -->
<!-- are definitely a lot of moving parts. If you use the -->
<!-- Appium.app at first, a lot of those issues are taken care of, but -->
<!-- if you're building out your framework, you'll need to address -->
<!-- them. The `appium-doctor` tool is super useful and helps you get -->
<!-- everything installed, similar to homebrew's `brew doctor`. There -->
<!-- are a lot of steps to get through, but most of them are pretty -->
<!-- simple, like pasting bash commands. Google and thickheaded -->
<!-- persistence is definitely key here!  -->

* Setup can be little involved. `appium-doctor` & some deep breathing!
* Read up on the [desired capabilities][caps]

[caps]: http://appium.io/slate/en/master/#appium-server-capabilities

```
my $android = {
    app                 => '/path/to.apk',
    appActivity         => '.application.MainActivity',
    appPackage          => 'com.your.android.app',
    deviceName          => 'Android Emulator',
    platformName        => 'Android',
    platformVersion     => '4.4'
};
```

```
my $ios = {
    app             => 'http://remote.path/to.app',
    deviceName      => 'iPhone Simulator',
    platformName    => 'iOS',
    platformVersion => '7.1'
};
```

<!-- First things first - we can't start an appium session without -->
<!-- desired capabilities, so we'll start here too. If your bindings -->
<!-- have a Capabilities class, it's a very good idea to take -->
<!-- advantage of it, or roll your own class if you'd like. A lot of -->
<!-- our early issues were just problems sorting out the caps. With -->
<!-- the recent Appium milestones, the caps have gotten a lot more -->
<!-- reliable, but managing them by hand can definitely be error -->
<!-- prone. -->

--

### check out them docs

* I'm really excited about the appium docs these days

- slate
- language toggler
- fancy
- looks good!
- (better than webdriver???)

--

### use the right tool for the job

* UserAgent spoofing ? because some of our users are on Windows, but
also because it may be significantly easier to set up.

* webdriver browser size

--

### play with Appium.app & `appium`

--

### expect to get familiar with arc! or the inspector

* or both!

--

### don't check options you don't understand

* TODO: add image here

<!-- In one of the older releases of the appium inspector, I was just -->
<!-- clicking around and saw these two options up here. I thought to -->
<!-- myself, "oh, I'm pretty advanced at Appium, I'm a power user, -->
<!-- they wouldn't put something here that would be too -->
<!-- detrimental. Give me all the information, I'll figure out what to -->
<!-- do it with," and idly checked these boxes and promptly forgot -->
<!-- about it. A week later I came back to Appium and the inspector-->

--

### online resources

* appium-discuss
* slackchat

--

### one script to rule them all?

* can we use the same script for iOS and android?

* probably delete this slide
