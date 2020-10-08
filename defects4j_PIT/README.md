Setting up Defects4J
================

Requirements
----------------
 - Java 1.8 (version 1.5.0 and older requires Java 1.7)
 - Git >= 1.9
 - SVN >= 1.8
 - Perl >= 5.0.12

#### Java version
All bugs have been reproduced and triggering tests verified, using the latest
version of Java 1.8.
Note that using Java 1.9+ might result in unexpected failing tests on a fixed
program version. 

#### Perl dependencies
All required Perl modules are listed in `cpanfile`. On many Unix platforms,
these required Perl modules are installed by default. If this is not the case,
you can use cpan (or a cpan wrapper) to install them. For example, if you have
cpanm installed, you can automatically install all modules by running:
`cpanm --installdeps .`

#### Timezone
Defects4J generates and executes tests in the timezone `America/Los_Angeles`.
If you are using the bugs outside of the Defects4J framework, set the `TZ`
environment variable to `America/Los_Angeles` and export it.

Steps to set up Defects4J
----------------

1. Clone Defects4J:
    - `git clone https://github.com/rjust/defects4j`

2. Initialize Defects4J (download the project repositories and external libraries, which are not included in the git repository for size purposes and to avoid redundancies):
    - `cd defects4j`
    - `./init.sh`

3. Add Defects4J's executables to your PATH:
    - `export PATH=$PATH:"path2defects4j"/framework/bin`

4. Check installation:
    - `defects4j info -p Lang`

On some platforms such as Windows, you might need to use `perl "fullpath"\defects4j`
where these instructions say to use `defects4j`.


Using Defects4J
================

#### Example commands
1. Get information for a specific project (commons lang):
    - `defects4j info -p Lang`

2. Get information for a specific bug (commons lang, bug 1):
    - `defects4j info -p Lang -b 1`

3. Checkout a buggy source code version (commons lang, bug 1, buggy version):
    - `defects4j checkout -p Lang -v 1b -w /tmp/lang_1_buggy`

4. Change to the working directory, compile sources and tests, and run tests:
    - `cd /tmp/lang_1_buggy`
    - `defects4j compile`
    - `defects4j test`

5. The scripts in [`framework/test/`](framework/test/)
are examples of how to use Defects4J, which you might find useful
as inspiration when you are writing your own scripts that use Defects4J.

Command-line interface: defects4j command
-----------------------
Use [`framework/bin/defects4j`](http://defects4j.org/html_doc/defects4j.html) to execute any of the following commands:

| Command        | Description                                                                                       |
|----------------|---------------------------------------------------------------------------------------------------|
| [info](http://defects4j.org/html_doc/d4j/d4j-info.html)                   | View configuration of a specific project or summary of a specific bug                             |
| [checkout](http://defects4j.org/html_doc/d4j/d4j-checkout.html)           | Checkout a buggy or a fixed project version                                                       |
| [compile](http://defects4j.org/html_doc/d4j/d4j-compile.html)             | Compile sources and developer-written tests of a buggy or a fixed project version                 |
| [test](http://defects4j.org/html_doc/d4j/d4j-test.html)                   | Run a single test method or a test suite on a buggy or a fixed project version                    |
| [mutation](http://defects4j.org/html_doc/d4j/d4j-mutation.html)           | Run mutation analysis on a buggy or a fixed project version                                       |
| [coverage](http://defects4j.org/html_doc/d4j/d4j-coverage.html)           | Run code coverage analysis on a buggy or a fixed project version                                  |
| [monitor.test](http://defects4j.org/html_doc/d4j/d4j-monitor.test.html)   | Monitor the class loader during the execution of a single test or a test suite                    |
| [bids](http://defects4j.org/html_doc/d4j/d4j-bids.html)                   | Print the list of active or deprecated bug IDs for a specific project                                           |
| [pids](http://defects4j.org/html_doc/d4j/d4j-pids.html)                   | Print a list of available project IDs                                                             |
| [export](http://defects4j.org/html_doc/d4j/d4j-export.html)               | Export version-specific properties such as classpaths, directories, or lists of tests             |
| [query](http://defects4j.org/html_doc/d4j/d4j-query.html)                 | Query the metadata to generate a CSV file of requested information for a specific project         |
