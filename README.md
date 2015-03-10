# Test-Milestone

###Introduction

For this milestone, we have used Jenkins Application and have configured it to work for our requirements.

Breaking down the configurations made for each of the tasks,

#####Task 1 : The ability to run unit tests, measure coverage, and report the results.
For this task, we made use of [Cobertura]. This plugin helps in measuring code coverage using different metrics like classes, packages, lines, conditions, files and methods. 

To use this plugin, 
- We installed it using the manage plugins tab in Jenkins Configurations Dashboard. 
- Configured Build Step in our project, to use maven script cobertura:cobertura -Dcobertura.report.format=xml to use Cobertura.
- Published the results into files using a post build step - **/target/site/cobertura/*.xml

In the coverage report section of the job, we observed the coverage report obtained and it is classified into different metrics like classes, packages, lines, conditions, files and methods. And the report can be drilled into each sub folder in the project and to each file.

![image1](/screenshots/SS1.jpg)
![image2](/screenshots/SS7.jpg)
![image3](/screenshots/SS8.jpg)

#####Task 2 : The ability to improve testing coverage using one of the techniques covered in class: constraint-based test generation, fuzzing, etc. You can use an existing tool or implement your own approach.

For Task 2, we used TestLink and Junit tools to improve code coverage. Steps followed were - 
- Installed plugins Junit and TestLink
- Configured Jenkins to support usage of these plugins and added both build and post build steps.
- In the build step, using the TestLink plugin we improrved test coverage by generating random automatic test cases.
- In the post build step, we reported them in a .xml file

We compared the test coverage obtained before and after addind the TestLink plugin and observed that the test coverage has increased by a considerable amount.

![image4](/screenshots/SS4.jpg)
![image5](/screenshots/SS5.jpg)

#####Task 3 : The ability to run an existing static analysis tool on the source code, process its results, and report its findings.

For Task 3, we used FindBugs to perform static analysis on source code.

Steps invovled are
- Installed FindBugs plugin and configured it as per project requirements.
- Added a build step in the job for Findbugs to work on the project
- Added a post build step to record the results in a .xml file

![image1](/screenshots/SS6.jpg)

#####Task 4 : The ability to extend an existing analysis tool with a custom rule, or implement a new analysis.

#####Task 5 : The ability to reject a commit if it fails a minimum testing criteria and analysis criteria

[Cobertura]: https://wiki.jenkins-ci.org/display/JENKINS/Cobertura+Plugin

