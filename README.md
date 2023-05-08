Download Link: https://assignmentchef.com/product/solved-se465-assignment-1
<br>
<h1>Question 1</h1>

For this question, you will write JUnit tests for the FormattedCommandAlias class of the Bukkit Minecraft server API to achieve 100% statement coverage.

The provided Vagrant image includes a slightly modified version of Bukkit in the ˜/shared/bukkit directory (bukkit diff also available in course github at assignments/a1/bukkit-test-instrumentation.diff. I added a skeleton test class for FormattedCommandAlias, called FormattedCommandAliasTest.

You can run the tests in the VM with the command mvn test in the ˜/shared/bukkit directory. To generate the Jacoco coverage report, use mvn package. You’ll find the resulting reports in ˜/shared/bukkit/target/ site/jacoco/org.bukkit.command.

<strong>Your task. </strong>Add JUnit unit tests to FormattedCommandAliasTest that achieve 100% statement coverage for the org.bukkit.command.FormattedCommandAlias class and that verify the results of the computation.

Marking scheme: We will mark your modified org.bukkit.command.TestFormattedCommandAlias class. 5 points for coverage (full marks for 100% statement coverage, nonlinearly scaled down for less), 5 points for your tests having passing assertions that verify the output. You will get 0 points if your code doesn’t compile.

<h1>Questions 2–5: “se465-flashcards”</h1>

The next 4 questions are about the “se465-flashcards” webapp. I hope that using Glitch will ensure painless setup; when you click the “remix” button on <a href="https://glitch.com/~se465-flashcards">https://glitch.com/</a><a href="https://glitch.com/~se465-flashcards">˜</a><a href="https://glitch.com/~se465-flashcards">se465-flashcards</a><a href="https://glitch.com/~se465-flashcards">,</a> it will create a copy of the code and set up a virtual machine for you.

This webapp, written in Express + pug, includes both frontend code (in the public/js and views directories), as well as backend code (in the node.js files in the main directory).

You can get glitch to show you diffs by opening the Logs, and then pressing the Console button. That gets you a console, where you can ask for the git log of the project. You can then use git diff to print out the diffs that we ask you to submit.

<h1>Question 2</h1>

In this question, you will perform exploratory testing on “se465-flashcards”. The charter will be “Explore the overall functionality of se465-flashcards”. (1 point) Summarize in one or two sentences what you perceive as the goal of “se465-flashcards”. (5 points) Identify the tasks that “se465-flashcards” should be able to do and classify them as primary or contributing. (You probably want to do this in parallel with your exploratory testing). (1 points) Identify areas of potential instability. (3 points) Produce exploratory testing notes summarizing your findings (one or two paragraphs); in Question 3 you will report a bug, so no need to do that here.

<h1>Question 3</h1>

(3 points) Identify a failure (bug) in the “se465-flashcards” webapp. Limit yourself to using the front-end as presented by the application; that is, don’t enter custom URLs or send requests to the back-end. (2 points) Write down a sequence of steps to reproduce the bug. (5 points) Implement a fix for the bug and explain the fix; show the incorrect and correct outputs. (Screenshots are probably your best bet).

(Think about the program’s input space and poke at corners of the input space.)

<h1>Question 4</h1>

Now we’ll talk about the back-end. We talked about “controllability” and “observability” for systems. It turns out that the backend API has endpoints that provide controllability but not observability; the frontend directly queries the database to get its results (a poor design!) (1 point) Briefly summarize what each of the commands in apiRouter.js can do. (4 points) Propose changes to this API that would make each of the endpoints /api/update, /api/delete, and /api/upload testable. (3 points) Implement these changes and submit a diff. (7 points) Write automatic test cases for each of the 3 endpoints. These test cases should ensure that the system is in a known state before they start running. (Your test cases should target your own instance of the webapp.)

REST-assured (installed in the Vagrant image in ˜/shared/rest-assured) looks like a good way to use JUnit tests for REST testing: <a href="https://github.com/rest-assured/rest-assured">https://github.com/rest-assured/rest-assured</a><a href="https://github.com/rest-assured/rest-assured">,</a> although you are free to use a different framework, after checking with me.

<h1>Question 5</h1>

We’ll consider the front-end next. (1 points) What feature of the front-end makes it difficult to test? (2 points) How can we add more controllability to the front-end to make it easier to test? (3 points) Implement your proposed change. (9 points) Create a Selenium test suite that exercises 3 features of the se465-flashcards webapp.

In the shared/selenium directory in your repo, you will find a SeleniumExample. You can run tests from this example using the command: mvn test “-Dtest=se465.SeleniumExample#test*” -Dwebdriver.base.url=https://www.google.com

Your test suite should be called se465.FlashcardsTestSuite and we should be able to run your tests with this command: mvn test “-Dtest=se465.FlashcardsTestSuite#test*”

<strong>HINT: </strong>You can’t get the text from an input element with getText(). See instead <a href="https://www.w3schools.com/jsref/prop_text_value.asp">http://www.w3schools.</a>

<a href="https://www.w3schools.com/jsref/prop_text_value.asp">com/jsref/prop_text_value.asp</a><a href="https://www.w3schools.com/jsref/prop_text_value.asp">.</a>

Useful reference:

<a href="https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/WebElement.html">https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/WebElement.html</a>