# Sample Incubator IG
HL7 FHIR Sample Incubator IG

This sample IG is a skeleton IG to clone for use in creating an "incubator" IG to hold FHIR Additional Resources that have been removed from the main FHIR R6 Core Specification.

### Set Up Local Machine to Build FHIR IGs
- If not already set up, set up your local machine to build FHIR IGs:
  - set up IG publisher on your local machine, see: https://confluence.hl7.org/spaces/FHIR/pages/175618322/IG+Publisher+CLI
  - set up SUSHI (FHIR Shorthand) on your local machine, see: https://fshschool.org/docs/sushi/installation/

### Set Up Github
- Create a Github repository for your incubator IG in the [HL7 Github](https://github.com/HL7)
    - ask HL7 IT Support to set up a webhook so the CI Build will run when you push changes to Git
- Clone this (sample-incubator-ig) repo to your local machine
- Copy the folder structure and all the files into your incubator IG
  - Note: the .gitignore file contains paths and files that Git will ignore on commit/push - these are files and folders that do not need to be in the Git repo because they are not needed for the build
  - Note: the input/fsh folder contains a file called dummy-fsh-file.fsh - this folder and file are needed for Sushi to run and create the main IG file. If later, you end up adding profiles etc, that can be created in Sushi, you can delete this file

### Edit Files
- readme.md edit to suit your IG
- ig.ini file
  - update "ig = fsh-generated/resources/ImplementationGuide-hl7.fhir.uv.sample-incubator.json" - replace "sample-incubator" with the code from your IG Proposal
- sushi-config.yaml edit based on instructions contained in the comments in the file
- input/pagecontent/index.md - this is the main page of your IG, so edit to suit
- input/pagecontent/changes.md - this is where your change log will go

### Run IG Publisher
 - run _updatePublisher to get the latest publishe.jar and build scripts on your machine
 - run _genonce to build the IG
 - open output/index.html to see the built IG

 ### Add Additional Resources from the FHIR R6 Specification
  - TODO (get instructions from Grahame's tutorial)
  - video of tutorial is here: https://chat.fhir.org/user_uploads/10155/1t488mg5LrIIRvNw4IqnRNAx/FHIR-IG-Incubator-Creation-take-2-20251031_050251-Meeting-Recording.mp4

 ### Push Changes to Github
  - commit and push the changes to Git - if the webhook mentioned above has been set up, this will auto-build the IG on the CI Build (see: https://fhir.github.io/auto-ig-builder/builds.html)