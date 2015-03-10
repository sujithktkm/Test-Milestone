# Test-Milestone

###Introduction

For this milestone, we have used Jenkins Application and have configured it to work for our requirements.

Breaking down the configurations made for each of the tasks,

#####Task 1 : The ability to run unit tests, measure coverage, and report the results.
For this task, we made use of [Cobertura] to measure coverage. This plugin helps in measuring code coverage using different metrics like classes, packages, lines, conditions, files and methods. 

To use this plugin, 
- We installed it using the manage plugins tab in Jenkins Configurations Dashboard. 
- Configured Build Step in our project, to use maven script cobertura:cobertura -Dcobertura.report.format=xml to use Cobertura.
- Published the results into files using a post build step - **/target/site/cobertura/*.xml

In the coverage report section of the job, we observed the coverage report obtained and it is classified into different metrics like classes, packages, lines, conditions, files and methods. And the report can be drilled into each sub folder in the project and to each file.

![image1](/screenshots/SS1.jpg)
![image2](/screenshots/SS2.jpg)
![image3](/screenshots/SS3.jpg)
![image4](/screenshots/SS4.jpg)
![image10](/screenshots/SS10.jpg)
![image11](/screenshots/SS11.jpg)

To run the test cases, we used [JUnit] plugin and made use of maven scrpits. We installed JUnit plugin from the Jenkins dashboard, configured it in the job configurations and it helps to run the test cases on the given project. Using maven command mvn test we ran the unit tests.

To report the results, in the post build step, we configured cobertura and JUnit to obtain the reports as .xml files.

#####Task 2 : The ability to improve testing coverage using one of the techniques covered in class: constraint-based test generation, fuzzing, etc. You can use an existing tool or implement your own approach.

For Task 2, we used TestLink and Junit tools to improve code coverage. Steps followed were - 
- Installed plugins Junit and TestLink
- Configured Jenkins to support usage of these plugins and added both build and post build steps.
- In the build step, using the TestLink plugin we improrved test coverage by generating random automatic test cases.
- In the post build step, we reported them in a .xml file

We compared the test coverage obtained before and after addind the TestLink plugin and observed that the test coverage has increased by a considerable amount.

![image9](/screenshots/SS9.jpg)

#####Task 3 : The ability to run an existing static analysis tool on the source code, process its results, and report its findings.

For Task 3, we used [FindBugs] to perform static analysis on source code.

Steps invovled are
- Installed FindBugs plugin and configured it as per project requirements.
- Added a build step in the job for Findbugs to work on the project
- Added a post build step to record the results in a .xml file

![image5](/screenshots/SS5.jpg)
![image6](/screenshots/SS6.jpg)
![image7](/screenshots/SS7.jpg)
![image8](/screenshots/SS8.jpg)

#####Task 4 : The ability to extend an existing analysis tool with a custom rule, or implement a new analysis.

#####Task 5 : The ability to reject a commit if it fails a minimum testing criteria and analysis criteria

We have added threshold limits to Jenkins findbugs and cobertura plugins to reject a commit if it doesn't par the given thresholds and to accept the commit if they are above the same.

![image12](/screenshots/SS12.jpg)
![image13](/screenshots/SS13.jpg)
![image14](/screenshots/SS14.jpg)

[Cobertura]: https://wiki.jenkins-ci.org/display/JENKINS/Cobertura+Plugin
[JUnit]: https://wiki.jenkins-ci.org/display/JENKINS/JUnit+Plugin
[Findbugs] : https://wiki.jenkins-ci.org/display/JENKINS/FindBugs+Plugin
