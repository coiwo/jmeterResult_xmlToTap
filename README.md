# jmeterResult_xmlToTap
This is change JMeter Result file from xml format to Tap format. This is for the integration purpose of JMeter/Jenkins/TestLink

Basically I followed the instruction from https://wiki.jenkins-ci.org/display/JENKINS/Integrating+TestLink++Jenkins++JMeter to configure the testLink, JMeter, and Jenkins. Just with one problem: 
I first tried to use the script from , but it seems always returned the wrong result, so I decided to write a java script to transform JMeter XML test result file to TAP format. So I wrote this simple script for transforming JMeter XML test result file to TAP format. 
To use:
1. Put Result xml file in 'input' folder
2. Result will be saved in 'target' folder.

For ingetration with JMeter/Jenkins/TestLink
So from Jenkins:
1. install TestLink plugin
https://wiki.jenkins-ci.org/display/JENKINS/TestLink+Plugin
2. Configure TestLink from Jenkins > Configuration
3. Create a project > Configure:
3.1 Invoke TestLink:
Put the TestLink Version/Test Project Name/Test Plan Name/Build Name/Custom Fields/Test Plan Custom Fields according to the settings from the TestLink.
3.2 Add build action to run the java function/shell script
3.3 Result Seeking Strategy:
Add the tap directory in 'Include Pattern'
Add JMeterTestCase to Key Custom Field.

From TestLink:
1. Create custom Fields,
2. Add the JMeterTestCase custom field to test specs. And set the test specs to 'Automated'
3. Assign the test specs/cases to the according test plan.

From JMeter:
1. Make sure the test result listener generates xml format result.

Please follow link https://wiki.jenkins-ci.org/display/JENKINS/Integrating+TestLink++Jenkins++JMeter for more detail instruction.


