# AndWait Matcher

[![License][License-Image]][License-Url]
[![Build][Build-Status-Image]][Build-Status-Url] 
[![Coverage][Coverage-image]][Coverage-Url] 
[![Version][Version-image]][Version-Url] 
[![Maintainable][Maintainable-image]][Maintainable-Url] 
[![Javadoc][javadoc-image]][javadoc-Url]

### Description
Hamcrest matcher which is waiting (with timeout) for the expected value 

### Usage
```java
    assertThat(this::receiveMessage, andWait(is(equalTo("Howdy"))));
```
* this matcher works with the default hamcrest "assertThat"
* first parameter receives a function that will be called until the expected value is present (Success) or timeout (Exception) is received
* you can define a custom timeout by using the second optional parameter of the "andWait" matcher 
```java
    assertThat(this::receiveMessage, andWait(is(equalTo("Howdy")), 500));
```

#### Matcher assertionError example
```text
    Expected:
         but: [Timeout]
    Expected: is "unknown message"
         but: was "other message"
```

### TODO
* Feature instead of Thread.sleep(XY)
* Only one AssertionError description instead of having two descriptions - first is timeout and second is mismatch

![andwait](andwait.jpg "andwait")

[License-Url]: https://www.apache.org/licenses/LICENSE-2.0
[License-Image]: https://img.shields.io/badge/License-Apache2-blue.svg
[github-release]: https://github.com/YunaBraska/AndWaitMatcher
[Build-Status-Url]: https://travis-ci.org/YunaBraska/AndWaitMatcher
[Build-Status-Image]: https://travis-ci.org/YunaBraska/AndWaitMatcher.svg?branch=master
[Coverage-Url]: https://codecov.io/gh/YunaBraska/AndWaitMatcher?branch=master
[Coverage-image]: https://codecov.io/gh/YunaBraska/AndWaitMatcher/branch/master/graphs/badge.svg
[Version-url]: https://github.com/YunaBraska/AndWaitMatcher
[Version-image]: https://badge.fury.io/gh/YunaBraska%2FAndWaitMatcher.svg
[Maintainable-Url]: https://codeclimate.com/github/YunaBraska/AndWaitMatcher
[Maintainable-image]: https://codeclimate.com/github/YunaBraska/AndWaitMatcher.svg
[Javadoc-url]: https://github.com/YunaBraska/AndWaitMatcher
[Javadoc-image]: http://javadoc.io/badge/github/YunaBraska/AndWaitMatcher.svg
