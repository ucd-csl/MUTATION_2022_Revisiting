# defects4j_PIT

Defects4j courtesy of René Just.<br/>
This is a streamlined README with notes on changes and additional scripts only. See comprehensive README of defects4j here: https://github.com/rjust/defects4j/blob/master/README.md <br/>
<br/>
This framework has integrated the PIT mutation tool into the existing defects4j framework. It has also made changes to existing MAJOR mutation scripts to allow MAJOR mutation to operate at a test method level. A script which also identifies the triggering tests of a test suite has been created, once again this operates at a test method level opposed to the existing test class level.

# Setting up Defects4J

## Requirements

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

## Steps to set up Defects4J - PIT

1. Clone Defects4J:
    - `git clone https://github.com/SteGaff7/Mutant_Fault_Coupling.git`

2. Initialize Defects4J (download the project repositories and external libraries, which are not included in the git repository for size purposes and to avoid redundancies):
    - `cd defects4j_PIT`
    - `./init.sh`

3. Add Defects4J's executables to your PATH:
    - `export PATH=$PATH:"path2defects4j"/framework/bin`

4. Check installation:
    - `defects4j info -p Lang`

On some platforms such as Windows, you might need to use `perl "fullpath"\defects4j`
where these instructions say to use `defects4j`.


## Using defects4j_PIT

### PIT:

**run_pit.pl** - Runs PIT mutation analysis on a bug
Adapted from run_mutation.pl - some redundant lines of code and redundant command line options<br/>
<br/>
run_pit.pl [-p project] [-v version] [-t tmp_dir] [-o out_dir] [-d test_suite_dir]<br/>
`run_pit.pl -p Time -v 1f -t scratch/tmp_dir -o mutation_results -d test_suites/fixed_suties/Time/evosuite/2`<br/>
<br/>
Redundant options - [-f], [-A], [-i]

