<!-- omit in toc -->
# Introduction
Take note of errors or exceptions

<br />

<!-- omit in toc -->
# Table of Contents


# [Error Handling](https://stackoverflow.com/questions/651619/what-is-the-advantage-of-using-try-catch-versus-if-else)
||when to use|example|
|:---:|:---|:---|
|try-catch|1. truly exceptional conditions happen and do not want to break down the whole system <br /> 2. exceptions not related to code itself <br /> 3. not for everything|server being down, database disconnection|
|if-else|1. handle all cases you expect||


# [Try catch vs context manager](https://stackoverflow.com/questions/26096435/is-python-with-statement-exactly-equivalent-to-a-try-except-finally-bloc)

related to StopIteration, it is required to write try
https://bugs.python.org/issue21379

# Exceptions
## StopIteration
* To prevent the iteration to go on forever
* raised by the method next() or __next__() to stop the iterations or to show that no more items are left to be iterated upon


