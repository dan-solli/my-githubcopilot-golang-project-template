---
mode: agent
model: GPT-4.1
tools: ['codebase', 'editFiles', 'findTestFiles', 'githubRepo', 'runCommands', 'runTasks', 'runTests', 'search', 'searchResults', 'terminalLastCommand', 'testFailure', 'usages', 'context7', 'get-library-docs']
description: 'Generate tests for current file'
---
## Context
* Your mission is to create table based tests using stretchr/testify for the current file
## Requirements
* Test coverage for the file should reach at least 80%
## Validation
* No problems should be reported. No compiler errors, no linter errors
* All tests must pass
* Code coverage is verified with the command **go tool cover -func=cover.out | grep squad.go | column -t**
## Finalize
* Report code coverage of the newly implemented tests
