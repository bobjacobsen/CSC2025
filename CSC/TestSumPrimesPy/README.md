## Testing SumPrimes in Python

Reminder: If there's been a correction to this exercise posted, update your local copy via [these instructions](https://docs.google.com/document/d/1g3b2e7wf3mWaIZ4U6MkNR5B4fQuO71y6Q341LGs45HQ/edit?usp=sharing) before proceeding.

Goal: Gain familiarity with a typical test framework

First, set up the local environment:

```shell
  cd TestSumPrimesPy
  source setup.sh
```

You'll find our sum-of-primes example in the file `SumPrimes.py`. It's been recast as a Python function. To run it, hopefully printing the sum of primes in the 1st 7 integers, do:

```python
  % python3
  >>> from SumPrimes import sumPrimes
```

and then invoke it interactively

```python
  >>> sumPrimes(2)
```

(As we discussed in class, the original code doesn't work correctly.)

The file `test_SumPrimes.py` contains the code for a single test.
Take a look at it, and see if you understand what it contains.
You can run it with

```shell
  pytest
```

`pytest` will automatically look for python files starting with `test_` or end with `_test.py`. In our case, the test file is called `test_SumPrimes.py`.

In its initial form, the test just invokes `sumPrimes(1)` and makes sure it returns 0. This passes and gives the "PASSED" response.

There are commented-out tests that will check specific test cases, and therefore fail in the manner we discussed in lecture. Remove the leading `#` that comments out those lines, and watch the test fail when you run it:

```shell
  (edit the test_SumPrimes.py file)
  pytest
```

Isn't that "FAILURES" message ugly? Now fix the bug(s) (See below for hints),
and see the lovely "PASSED" again.

Would it have been easier to fix your code if you got the results of all the asserts each time you ran the tests?  How can you make it do that?

Finally, add a couple more tests to check other ranges. (The sum of primes from 1 to 20 inclusive is 77, for example)

### Hints

 - It's OK for a prime number to be divisible by 1.
 - If you try to divide a prime number by itself, you'll find that the remainder is zero.
 - For more information on Python math routines like `floor(...)`, `round(...)`, `sqrt(...)`, etc please see the
[math package doc page](https://www.w3schools.com/python/ref_math_sqrt.asp)
