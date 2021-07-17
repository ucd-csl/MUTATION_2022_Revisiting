# Merged Valid Maps

This folder contains the aggregated kill maps for each fault and each tool in the form of two archives, one per tool.

## MAJOR
Each folder corresponds to a project, and inside it each folder corresponds to a fault.<br/>
The CSV file contains the kill map with the following schema: 
- mutantID: the integer ID for the mutant
- killing_tests: a comma sepearated list of tests killing the mutant. Each killing test is described as bugId-tool-seed-testClass.testMethod for tests generated with randoop or evosuite and bugId-dev-dev-testClass::testMethod for developper written tests.
The log file contains the description of each mutant and its mutantID<br/>
    
## Pitest:
Each folder corresponds to a project, and inside each folder corresponds to a fault.<br/>
The CSV file contains the kill map with the following schema: 
- mutantID: mutatedClass-mutatedMethod-lineNumber-mutatorClass-indexNumber-blockNumber
- killing_tests: a comma sepearated list of tests killing the mutant. Each killing test is described as bugId-tool-seed-testClass.testMethod for tests generated with randoop or evosuite and bugId-dev-dev-testClass::testMethod for developper written tests.
