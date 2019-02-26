# Report for assignment 4

This report is written by KTH students taking the course DD2480-Software Engineering for the purpose of assignment 4.
Group 9

## Project

**Name:**  `apps-android-commons`

**URL:**  *https://github.com/commons-app/apps-android-commons*

**Project Description:**

*The Wikimedia Commons Android app allows users to upload pictures from their Android phone/tablet to Wikimedia Commons.*

## Selected issue

**Title:** Refactor high complexity classes

**URL:** *https://github.com/commons-app/apps-android-commons/issues/888*

**Issue description:**

*Address the very high cyclomatic complexity we are seeing from Codacy by breaking up Activities & Fragments according to one of the well-respected architectural patterns (MVP / MVVM / etc).*

## Onboarding experience

The project provided a [quick start guide for developers](https://github.com/commons-app/apps-android-commons/wiki/Quick-start-guide-for-Developers) explaining how to run the code. However, the given guide did not work for some of our group members. 

When opening the `Android studio`  some of our group members were prompted to automatically update some programs which would cause the project not to work properly. This could have been documented in the quick start guide.

The group members were having different experiences regarding the build process. For some it took an incredible amount of time whereas for some it went quite smoothly. Some of us did not even exactly follow the 
project’s startup guide and still got it to build. 

## Requirements affected by functionality being refactored

The issue of the project that our group focused on required high complexity classes with particularly high measure of CCN to be refactored. The refactoring would then address functions with high CCN and attempt to reduce their complexity for the purpose of reducing the complexity of the corresponding classes as a whole.

## Existing test cases relating to refactored code

Several of the functions refactored did not have specific unit test cases that tested the function directly. This could be problematic specially when it comes to refactoring large projects where a lot of refactoring could be done. It makes it difficult to be sure whether the refactored code has not interfered with any functionality aspect of the original code. 

## The refactoring carried out

The UML diagrams have been attached as .jpg files in the specific UML folder under the report map in the project repository. The refactored functions are in the same classes and files they were located in originally. Neither the class structure nor the file structure of the original project has been modified. 
A genral technique that was used when refactoring high complexity functions was to amongst other techniques, split up the function into several helper functions withe low complexity as well as the main function itself that calls the helpers which reduces its own complexity. 

## Test logs

Initially all the tests in the project passed. Everytime a refactoring was merged into master, the tests were re-execurted to ensure that the refactoring introduced to the code has not introduced bugs or changed code funtionality. The tests seem to pass just fine after the refactorings have been added. 

## Effort Spent

### Jakob

### Jenny

### Fredrik

I spent roughly 2 hours on installing software needed for the project. The Android studio program needed were not in the standard repository of my Linux distribution. Getting the project to run on my computer also took some time. Following the quick guide given in the project did not work for me.

Finding suitable functions to refactor took long time because many of the functions were not so easy to understand. Making it difficult to separate the function into different parts to reduce complexity. Also some of the functions found were already taken by other group members. The actual refactoring barely took any time at all.

I assumed my functions had some kind of testing, which they did not have. Searching for non existent functions.

### Shiva

Initially I spent about 4-5 hours on searching through different projects that we could take up. It is possible that I even underestimated this time spent since the project that we chose for the previous lab ended up being not very appropriate for the task which made the task more difficult for us. So we tried to be very careful with project choice this time which meant a lot of searching through projects, familiarizing myself with the overall project and then deciding whether it could be an appropriate alternative for the task. The process of project choice and familiarizing ourselves with the projects were all being done remotely so we did not have any group meetings and we did all the communication through Slack. Once we did choose a project, the built instructions for me took quite some time. The instructions given by the project startup guide were actually not useful for me at all. Because I didn't do it their way and I did a different way to build the project which then meant that I had to figure out the small details of the project configuration process until successful build by myself. This then also took quite  a while. The reason I did it “my” way was because I was having trouble getting it to work when i followed the project’s startup guide. After successful build the rest of the time was spent on finding functions/classes that can be refactored further into having lower complexity as measured by their CCN, refactoring them and committing them to git. My commits then include the code refactored as well as the corresponding UML. 

### Philip

## Overall experience

The project is very large and the refactoring that could be done is very extensive. There has been some refactorings done to a number of high complexity functions with high measure of CCN and the complexity reductions have been recorded and most of them are refactored to a great extent. There is however much more possible refactorings that could be done and this group attempted at adressing as much refactoring as possible given the limited time-span. 

A lot of functions with high complexity that were refactored lacked specific unit test cases and there are many more that lack specific unti test cases which is an issue to be addressed in the future. 


