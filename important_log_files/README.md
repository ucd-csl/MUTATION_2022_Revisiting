# Important log files

This folder contains various information about the faults and the number of valid (useable with both Major and Pitest) triggering test suites generated for them.

## 4gte_suite_bugs
This folder contains a file for each fault in the dataset having at least 4 valid triggering test suites. Each file lists the triggering test suites generated for this fault
    
## 5gte_suite_bugs
This folder contains a file for each fault in the dataset having at least 5 valid triggering test suites. Each file lists the triggering test suites generated for this fault

## MAJOR and PIT
This folder contains information about the tests suites on which each mutation tool could be run successully.
-TOOL_all_valid_suites - lists all the valid test suites (successfully run with mutation analysis) for the tool
-TOOL_bugs_gte4_suites - lists the faults that have greater than or equal to 4 valid test suites
-TOOL_bugs_gte5_suites - lists the faults that have greater than or equal to 5 valid test suites
-TOOL_bugs_lt4_suites - lists the faults that have fewer than 4 valid test suites
-TOOL_suites_per_bug - summary of the above information

## bugs_no_triggering_suites
This file list faults for which no triggering test suite were generated

## count_bugs_triggering_suites
This file details the number of faults for which different number of triggering test suites were generated

## valid_bugs
This file lists the faults used in the experiments
