---
title: "Faded Parsons Problems"
subtitle: "Reconstructing expert solutions to programming & subgoal-decomposition problems"
description: "Our earlier work on AutoStyle revealed that the students who benefited least from automatic coding-style hints are those who began with a poor high-level structure or strategy for the coding problem. This led us to ask: how can we teach/scaffold/verify…"
order: 2
active: true
card_image: null
categories:
  - Programming Education
---

<!-- Migrated from https://acelab.berkeley.edu/projects/faded-parsons/ (last modified 2024-03-18). Content may be out of date. -->

**Researchers:**

- Faculty: Armando Fox, Marti Hearst
- Serena Caraco (PhD, advised by Armando Fox)
- Nelson Lojo (MS, advised by Armando Fox)
- Prof. Mike Verdicchio, The Citadel Military College of Virginia

**Alumni:**

- [Nate Weinman](http://people.eecs.berkeley.edu/~nathaniel_weinman/) (PhD 2022, advised by Armando Fox and Marti Hearst, now at Figma)
- Eliane Wiese (postdoc 2018, now at University of Utah)
- Undergraduate researchers: Brian Hsu, Alexia Camacho

## Introducing Faded Parsons Problems

Our earlier work on [AutoStyle]({{ site.baseurl }}/projects/autostyle/) revealed that the students who benefited *least*  from automatic coding-style hints are those who began with a poor high-level structure or strategy for the coding problem. This led us to ask: **how can we teach/scaffold/verify the process by which a student produces a high-level strategy?**

Often, the student was unaware of a particular programming idiom or *pattern*  that could be used to solve the problem more elegantly. Programming patterns (sometimes called plans, schemata, templates) are higher-level, partial implementations of reusable higher-level programming concepts or strategies that achieve some goal. For example, an introductory-level programming pattern is “premature return from a loop”: searching a collection until some element satisfies a predicate, then breaking out of the loop to immediately return that element, with a catch-all return after the loop in case no match is found. According to cognitive theory, when people view example problems with identifiable similarities, they eventually construct, store, and are able to recall and reuse a complex pattern when solving a problem that fits the pattern, rather than constructing the problem’s solution from scratch. Learning to recognize and apply patterns is therefore critical to becoming a proficient software engineer. But in traditional code-writing exercises, if a student doesn’t already know the pattern (and recognize the opportunity to use it), the student is now faced with having to simultaneously learn and understand the concept behind the pattern (e.g. “premature return from a loop”) and the specific syntax required to adapt the pattern to a variety of situations.

To address this challenge, we developed **Faded Parsons Problems**  [[1]](#ref-Weinman2020). Original Parsons Problems require students to unscramble lines of code to form a working solution; Faded Parsons Problems also allow the instructor to replace some tokens in the given code with blanks, gradually shifting the focus from *reconstructing an expert’s solution* to *code-writing*. With few or no blanks, the student can focus on learning the pattern without worrying about constructing the right syntax; as blanks are introduced, the student must fill in more and more of the code, learning the syntax as they go. In contrast to regular Parsons Problems, whose learning gains do not necessarily transfer to code-writing tasks [[1]](#ref-Weinman2020), Faded Parsons Problems were specifically found to improve code-writing skills as well as or better than code-writing exercises [[2]](#ref-parsons-chi2021). They are also valuable in *exposing* students to new programming patterns by reconstructing expert solutions that use them.

This short [video](https://youtu.be/dmcCxy34NE8) shows the student experience of solving a Faded Parsons Problem.

<video controls preload="metadata" style="max-width:100%" src="{{ site.baseurl }}/assets/uploads/faded-parsons-demo.mp4"></video>

We subsequently adapted our tool [[3]](#ref-fpp-element) to work with the [PrairieLearn](http://prairielearn.org) assessment authoring and delivery system, which we are using heavily as part of our [proficiency-based learning efforts in the LEARNER Lab](http://learner.berkeley.edu).

## Teaching Test-Writing Using Faded Parsons Problems

Testing is a critical skill in real-world software engineering, yet is woefully underemphasized in many CS programs. Testing is much more complex than just calling a leaf function and checking the return values: correctly stimulating part of the system under test may require setting up preconditions, controlling the return values of helper functions it calls (i.e. stubbing), providing “test double” objects to fill roles that are necessary for the subject code to run but are not the focus of the test itself (i.e. mock objects), and so on. Real-world testing libraries often include sophisticated functions to help with such tasks. Learning to write tests therefore presents **two** challenges:

- *Conceptual:* how do I set up and control the environment in which the subject code runs, in order to isolate the specific behavior being tested?
- *Syntactic:* how do I make use of the facilities of testing libraries to accomplish those goals?

We observe that *test-writing is a programming pattern,* namely the Arrange-Act-Assert pattern underlying all tests, and we should therefore be able to use exercises aimed at teaching patterns (such as Faded Parsons Problems) to teach it. This also requires changes to autograding, since the usual approach in which student code is tested against instructor-provided test cases doesn’t apply here. Instead, we use a form of *mutation testing* to autograde students’ work. We have developed these tools [[4]](#ref-rspec-faded-parsons) as a PrairieLearn element that we are incorporating into our [Intro to Software Engineering course.](http://cs169a.cs169.org)

## Scaffolding Subgoal Decomposition for Complex Software Tasks

Another challenge area for CS100-level students is working with large codebases, especially those in which control flow and data ownership are distributed across multiple subsystems.

For example, in a Model-View-Controller framework such as Rails, adding a new feature to an app typically requires adding code in one or more models, one or more views, and one or more controllers, plus possibly helper code in other places. Novices don’t always know what responsibilities belong where, and if they start writing code without this understanding, the result may violate architectural conventions that makes their code harder to understand, test, and maintain. Another example from the SaaS world is third-party authentication (“Login with Google”): there is a complex workflow in which control shifts among various places in the app that the user is signing into and the third-party authentication provider. Yet another example is the flow of control and data when a Web page makes an AJAX call to a server and must register a callback to receive data from the server. In all these cases, the software developer must know:

- What are the modules or subsystems involved in the operation, and how does control shift across them during the operation?
- What data is expected/consumed by each subsystem, and by which subsystem was it created?

As with Faded Parsons, we attempt to scaffold the learning of this *decomposition* problem in a way that initially abstracts the syntax and mechanics. Students work on interactive exercises inspired by Faded Parsons Problems in order to master this “structural decomposition” before starting to code.

### Example: Step 1

Here is a typical two-step exercise based on the Rails SaaS framework, which implements the Model–View–Controller architecture. The overall task here is to add third-party authentication via the OmniAuth library to an existing app. In the first step of the exercise, students must first drag each subgoal block (b) to the correct higher-level goal (a) and arrange the goals and subgoals in the correct order. The dropdown menus (c) are used for the student to indicate where in the app the corresponding code will eventually go (model, view, controller, configuration files, or just running a command to make something happen).

![]({{ site.baseurl }}/assets/uploads/subgoal_decomp_v1.png)

### Example: Step 2

Then, given the correctly-ordered goals and subgoals (a), new containers appear inside each subgoal (b) to indicate what data is consumed/produced as a result of that subgoal step; students must drag correct Data Blocks (d) to fill in these containers, using the ‘X’ button (e) to delete incorrectly-placed blocks.

![]({{ site.baseurl }}/assets/uploads/data_flow_v1.png)

This tool exists in prototype form, but our plan is to incorporate it into the PrairieLearn framework, as we have done with the Faded Parsons Problem element.

---

**Support acknowledgment:** This work is supported by a National Science Foundation Graduate Fellowship grant #DGE 1752814, and by grants #OPR19186 and #00005919 from the [California Education Learning Lab](http://calearninglab.org), an initiative of the California Governor’s Office of Planning and Research.

## References

1. <a id="ref-Weinman2020"></a>Nathaniel Weinman, Armando Fox and Marti Hearst. “Exploring Challenging Variations of Parsons Problems.” *Proceedings of the 51st ACM Technical Symposium on Computer Science Education*, 2020. [Link](https://doi.org/10.1145/3328778.3372639) [PDF]({{ site.baseurl }}/assets/papers/Weinman2020.pdf)
2. <a id="ref-parsons-chi2021"></a>Nathaniel Weinman, Armando Fox and Marti A. Hearst. “Improving Instruction of Programming Patterns With Faded Parsons Problems.” *2021 ACM CHI Virtual Conference on Human Factors in Computing Systems (CHI 2021)*, 2021. [PDF]({{ site.baseurl }}/assets/papers/parsons-chi2021.pdf)
3. <a id="ref-fpp-element"></a>Logan Caraco, Nate Weinman, Stanley Ko and Armando Fox. “Automatically Converting Code-Writing Exercises to Variably-Scaffolded Parsons Problems.” *EECS Department, University of California, Berkeley*, 2022. [Link](http://www2.eecs.berkeley.edu/Pubs/TechRpts/2022/EECS-2022-173.html) [PDF]({{ site.baseurl }}/assets/papers/fpp-element-techreport.pdf)
4. <a id="ref-rspec-faded-parsons"></a>Nelson Lojo and Armando Fox. “Teaching Test-Writing As a Variably-Scaffolded Programming Pattern.” *27th Annual Conference on Innovation and Technology in Computer Science Education (ITiCSE 2022)*, 2022. [PDF]({{ site.baseurl }}/assets/papers/rspec-faded-parsons.pdf)
