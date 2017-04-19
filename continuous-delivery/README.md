==========================================
Source code management: Credentials Select
==========================================
This script will help to Change the credentials for GIT Source code management. To change the credentials pass the value to the credentialsId variable within the script Ex: String credentialsId="4ff4a55b-1313-45da-8cbf-b2e100b1accd"


=======================================================
Source code management :Wipe out workspace & force clone
=======================================================
This script will help to add an additional behavior for source code management by adding wipeout workspace & force clone option within the project configuration


======================================
Build Environment: MaskPassword plugin
======================================
This script will help to tick off the mask password checkbox for the projects. Running this script on script console will ensure that the option[1] is checked.

[1]Mask passwords (and enable global passwords)


====================================
Build Environment:Maven ReleaseBuild
====================================
This script will help to tick off the Maven release related option for the projects. Running this script on script console will ensure that the option[1] is checked. 

[1]Maven release build


Note:To change the parameters for Release goals and options[2] and DryRun goals and options[3] update the below two parameters

[2]DEFAULT_RELEASE_GOALS
[3]DEFAULT_DRYRUN_GOALS

=================
Post Build Actions
=================
This script will help to fill the Post Build Actions related option for the project. Running this script on script console will ensure that the option[1] is filled. 

[1]Release environment variable

Note:To change the parameters for Release environment variable, update the below  parameter[2] 

[2]releaseEnvVar="IS_M2RELEASEBUILD";


=================
Add/Remove Trigger
=================
This script will help to change the build triggers for the projects. Running this script on script console will ensure that the option[1] is unchecked and option[2] is checked

[1]Poll SCM

[2]Build when a change is pushed to GitHub



=================
To run the script
=================

Preconditions:Project Selection Filters
=========================
[1].To run the script for a single project, add a value to projName and comment out the line with "item.name ==~/carbon-([a-zA-Z])+/)" and run the script.


 String projName="carbon-data"
   // if(!item.disabled&&item.getLastBuild()!=null&&(item.name ==~/carbon-([a-zA-Z])+/)){
   if(!item.disabled&&item.getLastBuild()!=null&&(item.name ==projName)){

[2].To run the script for matching patterns that has a project name like carbon-data /carbon-uuf uncomment the line below

    if(!item.disabled&&item.getLastBuild()!=null&&(item.name ==~/carbon-([a-zA-Z])+/)){

    Note: if you want to match names such as "carbon-event-processing" you can update the above pattern as ([a-zA-Z-a-zA-Z] 

[3].To match project names such as "siddhi-window-unique-length" you may also use a pattern such as shown below.

    if(item.getLastBuild()!=null&&(item.name ==~ /(.*)siddhi-(.*)/)){

    Note: This pattern[3] was tested for project names as "carbon-event-processing" and siddhi-window-unique-length

Executing the script
====================
Past the script on Script Console option available under the Manage Jenkins option and click on run button to execute the results.

