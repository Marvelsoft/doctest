<h3>The fastest feature-rich C++98/C++11 single-header testing framework for unit tests and TDD</h3>

<b>
<table>
    <tr>
        <td>
            master branch
        </td>
        <td>
            Linux/OSX <a href="https://travis-ci.org/onqtam/doctest"><img src="https://travis-ci.org/onqtam/doctest.svg?branch=master"></a>
        </td>
        <td>
            Windows <a href="https://ci.appveyor.com/project/onqtam/doctest/branch/master"><img src="https://ci.appveyor.com/api/projects/status/j89qxtahyw1dp4gd/branch/master?svg=true"></a>
        </td>
        <td>
            <a href="https://coveralls.io/github/onqtam/doctest?branch=master"><img src="https://coveralls.io/repos/github/onqtam/doctest/badge.svg?branch=master"></a>
        </td>
        <td>
            <a href="https://scan.coverity.com/projects/onqtam-doctest"><img src="https://scan.coverity.com/projects/7865/badge.svg"></a>
        </td>
    </tr>
    <tr>
        <td>
            dev branch
        </td>
        <td>
            Linux/OSX <a href="https://travis-ci.org/onqtam/doctest"><img src="https://travis-ci.org/onqtam/doctest.svg?branch=dev"></a>
        </td>
        <td>
            Windows <a href="https://ci.appveyor.com/project/onqtam/doctest/branch/dev"><img src="https://ci.appveyor.com/api/projects/status/j89qxtahyw1dp4gd/branch/dev?svg=true"></a>
        </td>
        <td>
            <a href="https://coveralls.io/github/onqtam/doctest?branch=dev"><img src="https://coveralls.io/repos/github/onqtam/doctest/badge.svg?branch=dev"></a>
        </td>
        <td>
        </td>
    </tr>
</table>
</b>

**doctest** is a new C++ testing framework but is by far the fastest both in compile times (by [**orders of magnitude**](doc/markdown/benchmarks.md)) and runtime compared to other feature-rich alternatives. It brings the ability of compiled languages such as [**D**](https://dlang.org/spec/unittest.html) / [**Rust**](https://doc.rust-lang.org/book/testing.html) / [**Nim**](https://nim-lang.org/docs/unittest.html) to have tests written directly in the production code by providing a fast, transparent and flexible test runner with a clean interface.

[<img src="https://cloud.githubusercontent.com/assets/8225057/5990484/70413560-a9ab-11e4-8942-1a63607c0b00.png" align="right">](http://www.patreon.com/onqtam)

The framework is and will stay free but needs your support to sustain its development. There are lots of <a href="doc/markdown/roadmap.md"><b>new features</b></a> and maintenance to do. If you work for a company using **doctest** or have the means to do so, please consider financial support. Monthly donations via Patreon and one-offs via PayPal.

[<img src="https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif" align="right">](https://www.paypal.me/onqtam/10)

A complete example with a self-registering test that compiles to an executable looks like this:

![cover-example](scripts/data/using_doctest_888px_wide.gif)

There are many C++ testing frameworks - [Catch](https://github.com/philsquared/Catch), [Boost.Test](http://www.boost.org/doc/libs/1_64_0/libs/test/doc/html/index.html), [UnitTest++](https://github.com/unittest-cpp/unittest-cpp), [cpputest](https://github.com/cpputest/cpputest), [googletest](https://github.com/google/googletest) and many [other](https://en.wikipedia.org/wiki/List_of_unit_testing_frameworks#C.2B.2B).

The **key** differences between it and other testing frameworks are that it is light and unintrusive:
- Ultra light on compile times both in terms of [**including the header**](doc/markdown/benchmarks.md#cost-of-including-the-header) and writing [**thousands of asserts**](doc/markdown/benchmarks.md#cost-of-an-assertion-macro)
- Doesn't produce any warnings even on the [**most aggressive**](scripts/cmake/common.cmake#L84) warning levels for **MSVC**/**GCC**/**Clang**
- Offers a way to remove **everything** testing-related from the binary with the [**```DOCTEST_CONFIG_DISABLE```**](doc/markdown/configuration.md#doctest_config_disable) identifier
- Doesn't pollute the global namespace (everything is in namespace ```doctest```) and doesn't drag **any** headers with it
- Very [**portable**](doc/markdown/features.md#extremely-portable) C++98 - per commit tested on CI with over 330 different builds (static analysis, sanitizers...)

![cost-of-including-the-framework-header](scripts/data/benchmarks/header.png)

This allows the framework to be used in more ways than any other - tests can be written directly in the production code!

Mantra: *Tests can be considered a form of documentation and should be able to reside near the production code which they test.*

- This makes the barrier for writing tests **much lower** - you don't have to: **1)** make a separate source file **2)** include a bunch of stuff in it **3)** add it to the build system and **4)** add it to source control - You can just write the tests for a class or a piece of functionality at the bottom of its source file - or even header file!
- Tests in the production code can be thought of as documentation or up-to-date comments - showing how an API is used
- Testing internals that are not exposed through the public API and headers is no longer a mind-bending exercise
- [**Test-driven development**](https://en.wikipedia.org/wiki/Test-driven_development) in C++ has never been easier!

The framework can be used like any other if you don't want/need to mix production code and tests - check out the [**features**](doc/markdown/features.md).

**doctest** is modeled after [**Catch**](https://github.com/philsquared/Catch) and some parts of the code have been taken directly - check out [**the differences**](doc/markdown/faq.md#how-is-doctest-different-from-catch).

[This table](https://github.com/martinmoene/catch-lest-other-comparison) compares **doctest** / [**Catch**](https://github.com/philsquared/Catch) / [**lest**](https://github.com/martinmoene/lest) which are all very similar.

[![Standard](https://img.shields.io/badge/c%2B%2B-98/11/14/17-blue.svg)](https://en.wikipedia.org/wiki/C%2B%2B#Standardization)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://badge.fury.io/gh/onqtam%2Fdoctest.svg)](https://github.com/onqtam/doctest/releases)
[![download](https://img.shields.io/badge/download%20%20-latest-blue.svg)](https://raw.githubusercontent.com/onqtam/doctest/master/doctest/doctest.h)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/503/badge)](https://bestpractices.coreinfrastructure.org/projects/503)
[![Join the chat at https://gitter.im/onqtam/doctest](https://badges.gitter.im/onqtam/doctest.svg)](https://gitter.im/onqtam/doctest?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Try it online](https://img.shields.io/badge/try%20it-online-orange.svg)](https://wandbox.org/permlink/oD4eD9NgDDs7qO0d)
<!--
[![Language](https://img.shields.io/badge/language-C++-blue.svg)](https://isocpp.org/)
[![documentation](https://img.shields.io/badge/documentation%20%20-online-blue.svg)](https://github.com/onqtam/doctest/blob/master/doc/markdown/readme.md#reference)
-->

Checkout the [**CppCon 2017 talk**](https://cppcon2017.sched.com/event/BgsI/mix-tests-and-production-code-with-doctest-implementing-and-using-the-fastest-modern-c-testing-framework) on [**YouTube**](https://www.youtube.com/watch?v=eH1CxEC29l8) to get a better understanding of how the framework works and read about how to use it in [**the article**](https://accu.org/var/uploads/journals/Overload137.pdf) of the february edition of ACCU Overload 2017!

[![CppCon 2017 talk about doctest on youtube](scripts/data/youtube-cppcon-talk-thumbnail.png)](https://www.youtube.com/watch?v=eH1CxEC29l8)

Documentation
-------------

Project:

- [Features and design goals](doc/markdown/features.md) - the complete list of features
- [Roadmap](doc/markdown/roadmap.md) - upcoming features
- [Benchmarks](doc/markdown/benchmarks.md) - compile-time and runtime supremacy
- [Contributing](CONTRIBUTING.md) - how to make a proper pull request
- [Changelog](CHANGELOG.md) - generated changelog based on closed issues/PRs

Usage:

- [Tutorial](doc/markdown/tutorial.md) - make sure you have read it before the other parts of the documentation
- [Assertion macros](doc/markdown/assertions.md)
- [Test cases, subcases and test fixtures](doc/markdown/testcases.md)
- [Parameterized test cases](doc/markdown/parameterized-tests.md)
- [Command line](doc/markdown/commandline.md)
- [Logging macros](doc/markdown/logging.md)
- [```main()``` entry point](doc/markdown/main.md)
- [Configuration](doc/markdown/configuration.md)
- [String conversions](doc/markdown/stringification.md)
- [FAQ](doc/markdown/faq.md)
- [Build systems](doc/markdown/build-systems.md)
- [Examples](examples)

Contributing
------------

[<img src="https://cloud.githubusercontent.com/assets/8225057/5990484/70413560-a9ab-11e4-8942-1a63607c0b00.png" align="right">](http://www.patreon.com/onqtam)

Support the development of the project with donations! There is a list of planned features which are all important and big - see the [**roadmap**](doc/markdown/roadmap.md). I took a break from working in the industry to make open source software so every cent is a big deal.

[<img src="https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif" align="right">](https://www.paypal.me/onqtam/10)

If you work for a company using **doctest** or have the means to do so, please consider financial support.

Contributions in the form of issues and pull requests are welcome as well - check out the [**Contributing**](CONTRIBUTING.md) page.


Sponsors
--------

Want to see your name or the name of your company here? Consider donating!

### :zap: Rockstar sponsors :zap:

### :gem: Gold sponsors :gem:

- Pascal Thomet
- Mario Kostadinov

### :cake: Silver sponsors :cake:

- Aras Pranckevicius
- Dan Nissenbaum
- Dean Bodenham

### :hamburger: Bronze sponsors :hamburger:

- Sebastien Feldis
- Zahari Karadzhov







FakeIt
======
 
[![Join the chat at https://gitter.im/eranpeer/FakeIt](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/eranpeer/FakeIt?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

GCC: [![Build Status GCC](https://travis-ci.org/eranpeer/FakeIt.svg?branch=master)](https://travis-ci.org/eranpeer/FakeIt)
[![Coverage Status](https://coveralls.io/repos/eranpeer/FakeIt/badge.svg?branch=master&service=github)](https://coveralls.io/github/eranpeer/FakeIt?branch=master)

MSC: [![Build status MSC](https://ci.appveyor.com/api/projects/status/sy2dk8se2yoxaqve)](https://ci.appveyor.com/project/eranpeer/fakeit)

FakeIt is a simple mocking framework for C++. It supports GCC, Clang and MS Visual C++.

FakeIt is written in C++11 and can be used for testing both C++11 and C++ projects.

```cpp
struct SomeInterface {
	virtual int foo(int) = 0;
	virtual int bar(string) = 0;
};
```
```cpp
// Instantiate a mock object.
Mock<SomeInterface> mock;

// Setup mock behavior.
When(Method(mock,foo)).Return(1); // Method mock.foo will return 1 once.

// Fetch the mock instance.
SomeInterface &i = mock.get();

// Will print "1". 
cout << i.foo(0);


```
Verify method invocation
```cpp
Mock<SomeInterface> mock;
		
When(Method(mock,foo)).Return(0);

SomeInterface &i = mock.get();

// Production code
i.foo(1);

// Verify method mock.foo was invoked.
Verify(Method(mock,foo));

// Verify method mock.foo was invoked with specific arguments.
Verify(Method(mock,foo).Using(1));
```

Checkout the [Quickstart](https://github.com/eranpeer/FakeIt/wiki/Quickstart) for many more examples!

Download the [Latest Release](https://github.com/eranpeer/FakeIt/releases/latest) and start using FakeIt now!

## Features
* Packaged as a **single header file**.
* Very simple API based on the expressiveness of C++11.
* Supports all major compilers: GCC, Clang and MSC++.
* Easily integrated with [**GTest**](https://code.google.com/p/googletest/), [**MS Test**](http://en.wikipedia.org/wiki/Visual_Studio_Unit_Testing_Framework) and [**Boost Test**](http://www.boost.org/doc/libs/1_56_0/libs/test/doc/html/index.html).
* Expressive [Arrange-Act-Assert](http://xp123.com/articles/3a-arrange-act-assert/) syntax.
* Create mock classes or **spy existing objects** instantly in one simple line.
* No limitation on number of method arguments.
* Supports dynamic casting.

## Installation
FakeIt is a header only framework. It does not require any installation. For extra simplicity fakeit is packaged as a single header file.

FakeIt is pre-configured to work with some of the major unit testing frameworks. A pre-configured version will use the assertions mechanism of the unit testing framework to integrate the generated error messages into the unit testing framework output.

If you don't find your unit testing framework on the list, simply use the *standalone* configuration.

### Using a pre-packaged single header file
Pre-packaged single header versions of FakeIt are located under the *single_header* folder.
Depending on the unit testing framework you use, simply add one of the pre-packaged versions to the include path of your test project:
* <fakeit_folder>/single_header/[gtest](https://github.com/google/googletest)
* <fakeit_folder>/single_header/mstest
* <fakeit_folder>/single_header/boost
* <fakeit_folder>/single_header/[catch](https://github.com/philsquared/Catch) (Tested with Catch 2.0.1)
* <fakeit_folder>/single_header/[tpunit](https://github.com/tpounds/tpunitpp)
* <fakeit_folder>/single_header/[mettle](https://github.com/jimporter/mettle)
* <fakeit_folder>/single_header/qtest
* <fakeit_folder>/single_header/standalone

For example, to use fakeit with **Google Test** simply add the *single_header/gtest* folder to the include path of your test project:
```
-I"<fakeit_folder>/single_header/gtest"
```
### Using the source header files
Fakeit source code header files are located under the *include* foler. To use FakeIt directly from the source code all you need to do is to download the source files and add the *include* folder and the configuration folder of your choice to the include path of your project.
For example:
* To use fakeit with **Google Test** add the *include* folder and the *config/gtest* folder to the include path of your test project:
```
-I"<fakeit_folder>/include" -I"<fakeit_folder>/config/gtest"
```
* To use fakeit with **MS Test** add the *include* folder and the *config/mstest* folder to the include path of your test project:
```
-I"<fakeit_folder>/include" -I"<fakeit_folder>/config/mstest"
```
* To use fakeit with **Boost Test** add the *include* folder and the *config/boost* folder to the include path of your test project:
```
-I"<fakeit_folder>/include" -I"<fakeit_folder>/config/boost"
```
* To use fakeit with **Catch** add the *include* folder and the *config/catch* folder to the include path of your test project:
```
-I"<fakeit_folder>/include" -I"<fakeit_folder>/config/catch"
```
* To use fakeit with **tpunit** add the *include* folder and the *config/tpunit* folder to the include path of your test project:
```
-I"<fakeit_folder>/include" -I"<fakeit_folder>/config/tpunit"
```
* To use fakeit with **Mettle** add the *include* folder and the *config/mettle* folder to the include path of your test project:
```
-I"<fakeit_folder>/include" -I"<fakeit_folder>/config/mettle"
```
* To use fakeit with **QTest** add the *include* folder and the *config/qtest* folder to the include path of your test project:
```
-I"<fakeit_folder>/include" -I"<fakeit_folder>/config/qtest"
```
* To use fakeit without any testing framework integration (**standalone**) add the *include* folder and the *config/standalone* folder to the include path of your test project:
```
-I"<fakeit_folder>/include" -I"<fakeit_folder>/config/standalone"
```
It is recommended to build and run the unit tests to make sure FakeIt fits your environment.
#### Building and Running the Unit Tests with GCC
```
cd build
make all
```
run the tests by typing
```
./fakeit_tests.exe
```
#### Building and Running the Unit Tests with Clang
```
cd build
make -f clang_makefile all
```
run the tests by typing
```
./fakeit_tests.exe
```
#### Building and Running the Unit Tests with Visual Studio 
Open the tests/all_tests.vcxproj project file with Visual Studio 2013. Build and run the project and check the test results. 
## Limitations
* Currently only GCC, Clang and MSC++ are supported.
* Can't mock classes with multiple inheritance.
* Can't mock classes with virtual inheritance.
* Currently mocks are not thread safe. 
