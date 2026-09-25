---
title: "Resources for PrairieLearn Content Creators"
subtitle: "Computer-Based Testing Facility (CBTF)"
redirect_from:
  - /cbtf/resources-for-prairielearn-content-creators/
---

<!-- Migrated from https://acelab.berkeley.edu/cbtf/resources-for-prairielearn-content-creators/ (last modified 2025-06-03). Content may be out of date. -->

This page is a work in progress. Contact [Armando Fox](mailto:fox@berkeley.edu) with questions if what you’re looking for is still missing.

# Online resources

- [PrairieLearn documentation](https://prairielearn.readthedocs.io/en/latest)
- [Community-created elements](https://www.prairielearn.com/catalog/elements)
- [STAR Assessments course](http://eecs.link/star) offered by Armando Fox, Dan Garcia, and Narges Norouzi, in which students build and evaluate the efficacy of PrairieLearn assessments
- Hire students with experience in creating PrairieLearn content [coming soon]

# Where to begin

There are, roughly speaking, three “levels” of content creation possible in PrairieLearn, depending on how much coding ability you have:

1. Simple text markup to create simple question types such as multiple-choice, select-all-that-apply, fill-in-blank, and so on. Zero coding or software tools skills needed.
2. Use built-in PrairieLearn “elements” (there are dozens) to create more sophisticated question types such as matching, drawing or getting student input in the form of graphs and diagrams, numerical-answer questions, put-these-things-in-the-right-order questions, and much more. This level also gives you much more control over randomizing some aspects of the question, such as the order in which choices appear, which distractors are chosen for multiple-choice questions, the numeric parameter values of questions involving arithmetic, and so on. Requires minimal HTML coding skills and some facility with editing plain text files.
3. Custom code, in which you create arbitrary HTML/JavaScript/Python code from scratch to create a question that does something bespoke. If you can display it in a Web browser, you can make a question out of it, and provide arbitrarily sophisticated custom code for grading the student’s answer.

## Converting existing content

If you have an existing bank of questions in Canvas (bCourses) or Gradescope format, we may be able to fully or partially automate its conversion to PrairieLearn! [Contact Armando Fox](mailto:fox@berkeley.edu) to get started/learn more.

A few concepts and terminology will help you get off the ground quickly:

- A *course* is the Platonic ideal of a course that is offered repeatedly, such as “CS 169A Intro to Software Engineering”.
- A course has many *instances,* each corresponding to an offering of that course; for example, “Fa25”, “Sp26”, and so on.
- A course also has many *questions,* in the sense of a bank of questions. Each question may or may not have the ability to yield multiple *variants* based on randomization as above. This feature allows each student doing an exam or homework to get a different variant of “the same” question.
- A course instance has a set of *assessments*. An assessment is a collection of questions together with a presentation policy (should the question order be randomized? should a particular question “slot” randomly choose one of several related but distinct questions, rather than showing every student the same question in that slot? etc.) and an administration policy (is this a homework or an exam? Are multiple attempts allowed? Is it time-limited? May students complete it remotely, or only in the [CBTF]({{ site.baseurl }}/resources/cbtf/) during an assigned reservation?). Examples might include “Homework set #1” or “Midterm quiz #1” or “Final exam”.

With the above in mind, we recommend first reading the [quick start](https://prairielearn.readthedocs.io/en/latest/getStarted/) section of the PrairieLearn documentation and experimenting from there. The rest of this page lists additional UC Berkeley-specific information and resources for content creators.

## Community-created elements

For Level 2 creators, PrairieLearn maintains a page of [links to community-created elements](https://www.prairielearn.com/catalog/elements) in addition to the ones “built in” to PrairieLearn itself. The inaugural launch of this collection includes several elements contributed by UC Berkeley students in the [STAR Assessments](http://eecs.link/star) course.

## Recruiting students with PrairieLearn experience

TBD
