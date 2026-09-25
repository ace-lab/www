---
title: "Proficiency-Based / Mastery Learning"
subtitle: "Proficiency-based/mastery learning for EECS & beyond"
description: "Traditional teaching and assessment methods are “fixed time, variable learning”: assessments have inflexible deadlines, and student grades are based on a snapshot of what they can demonstrate at that moment in time. This approach magnifies equity gaps in student preparation:…"
order: 1
active: true
card_image: null
card_title: "Mastery Learning" # shorter title for the card banner
categories:
  - Mastery Learning
  - Assessment
---

<!-- Migrated from https://acelab.berkeley.edu/projects/cbt/ (last modified 2024-05-08). Content may be out of date. -->

- **PIs:**  Armando Fox & Dan Garcia (co-PIs); Neal Terrell, California State University, Long Beach; Solomon Russell and Edwin Ambrosio, El Camino College
- **Affiliated faculty:** Michael Ball, Josh Hug, Narges Norouzi, Lisa Yan
- **Students:** a great many, for a variety of courses!

## Mastery Learning at Berkeley in the news…

- *[Making the Grade: Berkeley professors develop “A’s for All” pilot](https://engineering.berkeley.edu/news/2023/12/making-the-grade/).* Berkeley Engineering News, Dec. 2023. A great overview of the project and its benefits for students and faculty.
- *[Three questions for UC Berkeley’s Oliver O’Reilly.](https://www.insidehighered.com/opinion/blogs/learning-innovation/2023/11/13/three-questions-uc-berkeleys-oliver-oreilly#)*  Inside Higher Ed, Nov. 2023. Focuses on improving accommodations for students with disabilities and student athletes, and discussed how computer-based testing and mastery learning can specifically benefit those students.
- *[Instructor survey regarding student accommodations](https://drive.google.com/file/d/101qiYeNhvInVgghAD1p1qwLuGoQPQL1w/view).* October 2023. This survey (N=3892), led by the Division of Undergraduate Education, reveals that proctoring is the #1 issue with which instructors need support for student accommodations. Computer-based testing solves many proctoring issues.

## Project Summary

Traditional teaching and assessment methods are “fixed time, variable learning”: assessments have inflexible deadlines, and student grades are based on a snapshot of what they can demonstrate at that moment in time. This approach **magnifies equity gaps** in student preparation: in our own lower-division CS courses, one of the best predictors of student grades is prior exposure to similar material.

In contrast, *mastery learning*  is “fixed learning, variable time”: flexible policies for assessment deadlines, *combined with many opportunities for students to practice and get feedback on their work,*  has long been shown to increase student success to a level comparable to one-on-one tutoring [1], and recent work has suggested the impact this could have if adopted more widely in CS education [2]. There are two challenges to implementing mastery learning in our traditional setting. First, summative assessments (exams) must be “async-resilient”: the exam’s integrity must not depend heavily on all students taking it simultaneously, thus allowing flexible scheduling and exam re-takes. Second, formative assessments (homework/labs), which foster new learning rather than measuring existing learning, must be plentiful and give immediate feedback, so that students can practice as much as they need to without the need for (slow) human grading.

We have been using PrairieLearn, developed at the University of Illinois at Urbana-Champaign, to author *question generators* that can generate many variants of a question on demand, both for student practice and to customize each student’s exam. This allows *flexible policies* regarding homework deadlines, exam re-takes, and so on. The technical and policy ingredients together enable mastery learning. *(Our related project on [Flextensions]({{ site.baseurl }}/projects/flextensions/) proposes a systematic and scalable solution to automating the management of flexible homework deadlines.)*

**Mastery learning is working.** In Fall 2020 as part of this project, any CS10 student who wished to pass, but was in danger of not passing, could elect to receive an Incomplete grade and finish the remaining work after the semester’s end with no fixed deadline. **URM students benefited relatively more from this policy: the percentage of students who would have otherwise failed, but passed given our new format, was higher for URM students than for women, and higher for women than for majority-group students.** In Fall 2022, any CS10 student who was on track to receive a grade lower than what they wished to receive could elect to receive an Incomplete grade and finish the remaining work after the semester’s end with no fixed deadline to get the higher grade. Once again, **45% of URM students (vs. 31% of non-URM) and 55% of women (vs. 52%) benefited from this policy**. See our [end-of-project 2022 report](https://drive.google.com/file/d/13kEggUavPq-jh8g6-MiVeq01iy6Bao-1/view?usp=share_link) for details.

**Mastery learning requires resources.** Developing question generators is being done primarily by our very talented and hardworking undergraduates, most of whom have TA or other academic staff experience. We have resources available to help onboard your teaching staff to do this, and we even offer a [CS special topics course](http://eecs.link/star) in designing and evaluating interactive online assessments.

This work is supported by seed funds from the UC Berkeley College of Engineering and the Office of the Vice Chancellor for Undergraduate Education, and by two major awards from the [California Education Learning Lab](https://opr.ca.gov/learninglab/) (CELL) in collaboration with Cal State Long Beach and El Camino College on this innovative and exciting [pilot project](https://opr.ca.gov/learninglab/grants/awards/reorienting_formative_summative_assesment.html) to improve student equity/diversity and institutional resilience in Computer Science through mastery learning.

The project’s hypotheses are that mastery learning using PQGs will contribute to higher retention, stronger learning outcomes, more effective use of instructor time, and an increase in successful participation in computing for traditionally underrepresented students. We hope the findings of this project will open the door towards new learning approaches to expand diversity and inclusion in Computer Science.

1. Bloom, Benjamin S (June–July 1984). “The 2 Sigma Problem: The Search for Methods of Group Instruction as Effective as One-to-One Tutoring” (PDF). Educational Researcher. 13 (6): 4–16. doi:10.3102/0013189×013006004
2. James Garner, Paul Denny, and Andrew Luxton-Reilly. 2019. Mastery Learning in Computer Science Education. In Proceedings of the Twenty-First Australasian Computing Education Conference (ACE ’19). Association for Computing Machinery, New York, NY, USA, 37–46. DOI:https://doi.org/10.1145/3286960.3286965

**Interested in joining the project? Already been invited to join?**  Email Armando Fox & Dan Garcia with the following info:

- Name, year, student teaching experience (GSI, tutor, etc)
- Relevant EECS/CS courses taken
- Course(s) you’d like to develop content for or do research on (it’s assumed you have the approval of the course’s instructor of record)
- GitHub user name

**Recent publications** in reverse chronological order

- Dan Garcia, Armando Fox, Craig Zilles, Matthew West, Mariana Silva, Neal Terrell, Solomon Russell, Edwin Ambrosio and Fuzail Shakir. “A's For All (As Time and Interest Allow).” *SIGCSE 2023*, 2023.
- Nelson Lojo and Armando Fox. “Teaching Test-Writing As a Variably-Scaffolded Programming Pattern.” *27th Annual Conference on Innovation and Technology in Computer Science Education (ITiCSE 2022)*, 2022. [PDF]({{ site.baseurl }}/assets/papers/rspec-faded-parsons.pdf)
- Logan Caraco, Nate Weinman, Stanley Ko and Armando Fox. “Automatically Converting Code-Writing Exercises to Variably-Scaffolded Parsons Problems.” *EECS Department, University of California, Berkeley*, 2022. [Link](http://www2.eecs.berkeley.edu/Pubs/TechRpts/2022/EECS-2022-173.html) [PDF]({{ site.baseurl }}/assets/papers/fpp-element-techreport.pdf)
- Nathaniel Weinman, Armando Fox and Marti A. Hearst. “Improving Instruction of Programming Patterns With Faded Parsons Problems.” *2021 ACM CHI Virtual Conference on Human Factors in Computing Systems (CHI 2021)*, 2021. [PDF]({{ site.baseurl }}/assets/papers/parsons-chi2021.pdf)
- Nathaniel Weinman, Armando Fox and Marti Hearst. “Exploring Challenging Variations of Parsons Problems.” *Proceedings of the 51st ACM Technical Symposium on Computer Science Education*, 2020. [Link](https://doi.org/10.1145/3328778.3372639) [PDF]({{ site.baseurl }}/assets/papers/Weinman2020.pdf)

#### **Just joined the project?** Onboarding materials are in this [private GitHub repo.](https://github.com/ace-lab/pl-ucb-csxxx) Your advisor can get you access.

# Project overviews

### Dan Garcia on the *why* of CBT: Proficiency-Based Learning (5 minutes)

<iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="" frameborder="0" height="360" loading="lazy" referrerpolicy="strict-origin-when-cross-origin" src="https://www.youtube.com/embed/-SBfhYIHr-0?feature=oembed" title="CELL TedX" width="640"></iframe>

### Armando Fox on the *how* of CBT: from Questions to Question Generators

<iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="" frameborder="0" height="360" loading="lazy" referrerpolicy="strict-origin-when-cross-origin" src="https://www.youtube.com/embed/rC_wI0h5cJs?feature=oembed" title="2020-11 Fox EAB presentation" width="640"></iframe>

- [Slides](https://docs.google.com/presentation/d/13YPfGH-gvi0KjgnsLb3pFTy-oDo60fVqYNDyEesUSvU/edit#slide=id.p) for Instructional Resiliency Task Force (presented by Armando Fox)

# More Details…

See the main [LEARNER Lab website](http://learner.berkeley.edu) for recent publications and more details on the team and current efforts.

# Help Wanted

We’re looking for Masters and ambitious undergraduates to help with various PrairieLearn-related enhancements. These are a mix of research and engineering, but we’d expect any of them to lead to one or more submitted publications, as well as become contributions to an assessment-authoring system used by thousands of students!

**Prerequisites: *Strong***  software development skills, including solid knowledge of Python *or*  the ability to pick it up fast because you’ve used other non-Python web frameworks or modern scripting languages. Self-starter, works well in a small team or as one of a pair. Ability to do significant pathfinding on your own, by researching what has been done on a particular topic, finding relevant articles online where appropriate (with your advisor’s or a senior student’s guidance), and in general getting from a high-level description of the project to a specific plan to build & execute it.

**Compensation:** Pay or credit may be possible, depending on the specific project.

### Courseware for CS169A Software Engineering

Did you do well in, and enjoy, CS169A? Do you love testing, agile workflows, and other areas of focus in CS169, and want to help fellow students understand and learn them better? We’re looking for students who recently took CS169 and feel confident with the material, to help develop innovative new assessments, both formative (labs, homework) and summative (exam questions), that take full advantage of PrairieLearn’s flexibility to create really cool interactive learning materials. Contact Prof. Armando Fox directly to apply.

### Courseware developers for high-enrollment CS courses

Have you been a GSI/reader/etc. for a high-enrollment upper or lower division CS course? Are you excited about the possibility of improving the course’s assessments by using PrairieLearn? Ask your course’s instructor for their blessing to develop content for the course as part of our group. We will embed you in a team to get you started, and figure out a way to get you compensated for the work. Contact Prof. Dan Garcia if interested, or the instructor or co-instructor of the CS course(s) you’d be interested in developing courseware for!

### Automatic support for “Cheat traps”

Prof. Nick Weaver has developed a mechanism that helps detect certain forms of cheating on remote (takehome) online exams. We believe his techniques can be adapted in such a way that *anyone* authoring assessments in PrairieLearn can build them in. Is this possible, and if so, do they successfully detect attempts at certain types of cheating?

### Automatic support for cheating detection via UI events

Picture this scenario: a student taking a remote exam has another window open on their screen, via which they are illicitly getting the answer to (e.g.) a coding question. They copy-and-paste the answer and submit. But if you could look at the timing of the keystrokes, you’d see that they would have had to type impossibly fast to do that. This and other mechanisms can be signals of less-than-honorable behavior when taking an online exam. This project would investigate and ideally prototype/develop some ways of building these detection mechanisms directly into PrairieLearn. Contact Prof. Nick Weaver if interested.
