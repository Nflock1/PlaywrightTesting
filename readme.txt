Use the standard "npx playwright test" to run tests


Write up:


I’d like to start by saying that I really enjoyed this opportunity to get to play around and experiment with a new testing framework 
within a shell that has already been configured. Doing so was a great experience for me and has given me a lot of ideas for some personal 
projects I have on the backburner. 

While embarking on interacting with the Playwright testing framework that I had not been exposed to yet, I certainly encountered challenges.

Challenge: A very complicated Nested DOM: While trying to sort out the best classes, types, roles, etc to create my playwright locator, I 
  was met with an incredibly complicated DOM with many similar or redundant class names and a VERY deep data structure. So deep/nested was the 
  DOM that I managed to frequently lag the console/web page while navigating it and even crashed the chrome debugging console multiple times. 
  This also made locating the correct card_tile within the correct column a bit complicated.

  To Solve this I had to be patient and keep a keen eye on the complicated structure, while learning a number of new syntactical queries search 
  within the children of the class name matched elements to write robust and intuitive testing workflows.

Challenge: intermittent timeouts: while working initially from my laptop, I continually got over 30 second runtimes on tests that executed 
  in webkit which would automatically cause them to fail. In addition to this, there were intermittent timeouts on certain certain other actions 
  that would cause tests which should have succeeded to fail

  To solve this, I took a break before transferring off of my bogged down laptop and onto my better desktop PC while closing nearly all my 
  chrome windows. This alone was able to resolve webkit’s runtime issue, however timeouts on certain specific actions required me to dig a bit 
  more into playwright’s documentation to increase timeouts for actions that needed to navigate/query the previously mentioned complex DOM.

Challenge: unfamiliarity with Playwright: This has an obvious and straightforward solution: study up. I made sure to fully review any provided 
  resources as well as seek out my own before I even began writing code - I find that even something as simple as watching a general tutorial on 
  a new piece of software can help you get an idea of the language, it’s patterns, it’s capability, and even it’s best practices (luckily there 
  was a section on playwrights documentation for this as well). Then, even if you didn’t watch a tutorial on exactly what you are attempting to 
  accomplish, you can orient yourself and head in the right direction.

Through overcoming these challenges and interacting with playwright, I have a few recommendations:

if possible, reduce the complexity of the DOM. It seems like there were often parts of the application that were wrapped in 3-5 divs that either 
provided little value OR did not need to be their own DOM object to accomplish the intended function. Though there is certainly merit to modular 
and re-usable code, this DOM seemed to impact the efficiency of the page loading; Across all 3 browsing platforms that were tested, there were 
issues with intermittent timeouts on locator functions likely due to this complexity. Therefore condensing the code will at least make it easier 
to test OR even improve user experience and load times on more dynamic components.

In the same vein as above, many styling naming conventions were stacked on top of each other such that one element may have 10 class styles applied. 
Again, modularity and reusability are important, but when done to this extent, it convolutes the intended functionality, makes it more difficult to 
test, and likely does not abide by “least code” principles.

Due to webkit timeouts, I would investigate if there are any ways to improve the build so that it is smaller in size or more efficient during runtime. 
It’s unlikely that it can be improved to the speeds that chromium and mozilla run at, it’s still worth it for the user experience.

Though this was just an exercise to assess my skill, I do believe it would be better to build tests in smaller units. It would have been best to test 
that the login mechanism works in the intended way BEFORE trying to navigate to the Asana project and BEFORE card placement is validated. Each of these 
smaller tests could then be worked into larger ones to reduce test code complexity, if Playwright allows this kind of integration.

Since I have pointed out multiple issues with Asana’s DOM complexity and intermittent runtime timeouts, I think it would be worth setting up performance 
testing as well to see where the pinch points are, if any. This could aid in directing the efforts to improve the loading of dynamic components, 
particularly in webkit.


Again, thank you so much, I really look forward to learning more about Playwright and any other software I can get my hands on.




