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
A general technique that was used when refactoring high complexity functions was to amongst other techniques, split up the function into several helper functions withe low complexity as well as the main function itself that calls the helpers which reduces its own complexity.

## Test logs

Initially all the tests in the project passed. Everytime a refactoring was merged into master, the tests were re-executed to ensure that the refactoring introduced to the code has not introduced bugs or changed code functionality. The tests seem to pass just fine after the refactorings have been added.

## Effort Spent

### Jakob

Time spent:
I did spend about 5-6 hours looking for suitable projects on github before us a a group settling on Jenny’s suggestion of the android commons app. This time included finding some suggestions, that ended up being taken in the spreadsheet before we could pick it. Furthermore, getting the project to build took some time for me. The commons app utilises gradle as a build tool, and supposedly that should make things easier, but it did not. Since gradle was complaining about an library not being found, The error was as follows: Could not find com.github.deano2390:MaterialShowcaseView:1.2.0. After some trial and error, which for me took about five hours in total, I could build the project. The walkthrough (https://github.com/commons-app/apps-android-commons/wiki/Quick-start-guide-for-Developers) was kind of lackluster since it did not mention the issue I encountered, which then required googling and troubleshooting on my own.

Furthermore, I spent some time (1-2 hours) finding a suitable UML tool, I settled on Visual Paradigm, after trying out some android studio plugins which did not work at all.


Additionally, I spent about 2-3 hours getting a feel for the project and its structure after succeeding in building it. I used lizard to identify classes with high mean CCN and functions with high cyclomatic complexity, as specified by the issue.

Actual refactoring: 4 hours
I refactored two classes and reduced their mean CCN by quite a bit.


### Jenny

#### Project Search: 10h
The initial task of finding a project to work with took about 10 hours for me. It ended up being very challenging to find a project that was suitable since there were many requirements for the project. We needed a project that had open unassigned issues which was hard enough to find, after that you needed to check all the project criteria from assignment 3, double check if anyone else had claimed the issue (which some of them were) and evaluate the viability and suitability of the issue and project. All of this made finding a project the most time consuming task of this assignment. Tools like cloc helped but the task was still a big time sink.

#### Building: 10h
Whilst there is some wikis for the project we encountered problems with building the code that wasn’t described in the wiki. Time includes reinstalls, research, troubleshooting and communicating with members of the selected project.

#### Refactoring: 13h
###### MainActivity
Lowered average class cyclomatic complexity number from 2.11 to 2.0
Addressed functions was onBackPressed and onRequestPermissionsResult. The functions were given helper functions and some of the logic was simplified. The refactoring did not increase the need for test or fail any of the previous tests.
###### NavigationBaseActivity
Lowered average class cyclomatic complexity number from 2.5 to 1.9
Addressed function was onNavigationItemSelected. The item identification and event handling was split up into separate functions to provide more readable code and a lower class complexity.  The refactoring did not increase the need for test or fail any of the previous tests.

### Fredrik

##### Building: 6h

I spent roughly 2 hours on installing software needed for the project. The `Android studio` program needed was not in the standard repository of my Linux distribution. Getting the project to run on my computer also took some time. Following the quick guide given in the project did not work for me.

##### Refactoring: 11h

Finding suitable functions to refactor took long time because many of the functions were not so easy to understand making it difficult to separate the functions into different parts in a logical way to reduce the cyclomatic complexity. Also some of the functions found were already taken by other group members. The actual refactoring did not take so much time.

###### Functions: 

`NearbyMapFragment::setListeners:` *Reduced CNN from **16 to 4** and average class CNN from **3.0 to 2.8**.*

`PlaceRenderer::hookListeners:` *Reduced CNN from **11 to 5** and average class CNN from **2.5 to 2.1**.*

`FileProcessor::findOtherImages:` *Reduced CNN from **11 to 8** and average class CNN from **3.4 to 3.1**.*

*NOTE: There were no unit testing of my chosen functions.*

##### UML: 5h

I searched for tools to make UML diagrams because it is so tedious to manually make it with some painting tools. I found a pretty nice program called `StarUML` which is good for making the UML diagrams manually. `SimpleUML` is a good plugin for autogenerating UML diagrams from the source code in `Android studio`. Worth mentioning is that the autogenerated diagrams gives good overview of the project and is not so specific down to function level.

*NOTE: The UML diagrams are located in `apps-android-commons/report/uml/fredrik/` where `project.png` is a class UML of the whole project where the other files are the exact classes that has been refactored.* 

##### Documenting: 4h

I worked with the report. Structuring and writing.

### Shiva

Initially I spent about 4-5 hours on searching through different projects that we could take up. It is possible that I even underestimated this time spent since the project that we chose for the previous lab ended up being not very appropriate for the task which made the task more difficult for us. So we tried to be very careful with project choice this time which meant a lot of searching through projects, familiarizing myself with the overall project and then deciding whether it could be an appropriate alternative for the task. The process of project choice and familiarizing ourselves with the projects were all being done remotely so we did not have any group meetings and we did all the communication through Slack. Once we did choose a project, the built instructions for me took quite some time. The instructions given by the project startup guide were actually not useful for me at all. Because I didn't do it their way and I did a different way to build the project which then meant that I had to figure out the small details of the project configuration process until successful build by myself. This then also took quite  a while. The reason I did it “my” way was because I was having trouble getting it to work when i followed the project’s startup guide. After successful build the rest of the time was spent on finding functions/classes that can be refactored further into having lower complexity as measured by their CCN, refactoring them and committing them to git. My commits then include the code refactored as well as the corresponding UML.

### Philip

Time spent:
I spent 4-5 hours looking for suitable project and evaluating others suggestions. Building the project took about 8 hours as I had to install Android studios and build the actual project. I also faced some issues such as the project not being compatible with the latest gradle version. After this it took ~5h finding functions/classes to improve and improv them. Lastly ~5h were spend on creating UML diagrams in yEd Graph Editor.


## Overall experience

The project is very large and the refactoring that could be done is very extensive. There has been some refactorings done to a number of high complexity functions with high measure of CCN and the complexity reductions have been recorded and most of them are refactored to a great extent. There is however much more possible refactorings that could be done and this group attempted at adressing as much refactoring as possible given the limited time-span.

A lot of functions with high complexity that were refactored lacked specific unit test cases and there are many more that lack specific unti test cases which is an issue to be addressed in the future.
