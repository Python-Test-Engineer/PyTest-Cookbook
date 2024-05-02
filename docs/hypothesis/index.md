Best examle: [Pytest-with-Eric](https://pytest-with-eric.com/pytest-advanced/hypothesis-testing-python/){:target="_blank"} is  a very good resource. It is included in PyTest_06_HYPOTHESIS.


When writing unit tests, it’s hard to consider all possible edge cases and validate that your code works correctly.

This is sometimes caught in production and a quick and speedy patch needs to be deployed. Only for a new bug to emerge later.

There will always be cases you didn’t consider, making this an ongoing maintenance job. Unit testing solves only some of these issues.

Property-based testing is a complementary approach to traditional unit testing, where test cases are generated based on properties or constriants that the code should satisfy.

Hypothesis addresses this limitation by automatically generating test data based on specified strategies.

This allows developers to test a much broader range of inputs and outputs than traditional unit tests, increasing the likelihood of catching edge cases and unexpected behaviour.

https://github.com/elena/example-tests-django-hypothesis

https://www.drmaciver.com/2015/06/hypothesis-for-django/

https://www.agiliq.com/blog/2019/01/hypothesis-in-drf/

https://www.youtube.com/watch?v=7It3sIrTAVo

https://www.slideshare.net/slideshow/hypothesis-randomised-testing-for-django/58357011

https://github.com/HypothesisWorks/hypothesis/blob/master/hypothesis-python/examples/test_basic.py

[Hypothesis PyPi](https://pypi.org/project/hypothesis/){:target="_blank"}



