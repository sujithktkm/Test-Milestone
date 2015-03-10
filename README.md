# Test-Milestone

###Introduction

For this milestone, we have used Jenkins Application and have configured it to work for our requirements.

Breaking down the configurations made for each of the tasks,

####Task 1 : The ability to run unit tests, measure coverage, and report the results.
For this task, we made use of [Cobertura]. This plugin helps in measuring code coverage using different metrics like classes, packages, lines, conditions, files and methods. 

To use this plugin, 
- We installed it using the manage plugins tab in Jenkins Configurations Dashboard. 
- Configured Build Step in our project, to use maven script cobertura:cobertura -Dcobertura.report.format=xml to use Cobertura.
- Published the results into files using a post build step - **/target/site/cobertura/*.xml

####Task 2 : The ability to improve testing coverage using one of the techniques covered in class: constraint-based test generation, fuzzing, etc. You can use an existing tool or implement your own approach.


####Task 3 : The ability to run an existing static analysis tool on the source code, process its results, and report its findings.


####Task 4 : The ability to extend an existing analysis tool with a custom rule, or implement a new analysis.

####Task 5 : The ability to reject a commit if it fails a minimum testing criteria and analysis criteria

[Cobertura]: https://wiki.jenkins-ci.org/display/JENKINS/Cobertura+Plugin

