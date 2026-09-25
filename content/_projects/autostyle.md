---
title: "AutoStyle"
subtitle: "Automatic hints for improving student code style"
description: "Our focus is on the (relatively under-researched) area of helping “post-CS1” students build the skills expected of experienced programmers. The upper-division Intro to Software Engineering course and the accompanying project course are representative of those skills."
order: 10
active: false
card_image: null
categories:
  - Programming Education
---

<!-- Migrated from https://acelab.berkeley.edu/projects/autostyle/ (last modified 2022-06-21). Content may be out of date. -->

**Students**: HeZheng Yin (PhD, on leave), Joseph Moghadam (MS 2015), Rohan Roy Choudhury (MS 2015), Antares Chen, Eliane Wiese (postdoc 2018, now faculty at University of Utah)

Advised by **Armando Fox**

Our focus is on the (relatively under-researched) area of helping “post-CS1” students build the skills expected of experienced programmers. The [upper-division Intro to Software Engineering course](http://cs169a.cs169.org) and the accompanying [project course](http://cs169L.cs169.org) are representative of those skills.

Among the most important are **working effectively in a software team** (a group skill we address in our [Teamscope]({{ site.baseurl }}/projects/teamscope/) work) and **writing maintainable code** (an individual skill). In Robert C. “Uncle Bob” Martin’s book *Clean Code: A Handbook of Agile Software Craftsmanship,* Ward Christensen is quoted as saying that beautiful code “makes it look like the language was made for the problem.” Clean code is more maintainable because, to an expert, it more readily reveals its design intent and is well factored.

Inspired in part by my experience teaching Berkeley’s first MOOC on software engineering, the idea behind AutoStyle was that when many students submit functionally-correct solutions to the same programming problem, some students’ code will be closer to what an expert would produce than that of other students. Could we automatically identify *which*  aspects of the “better” solutions made them better, and synthesize hints to give to students who came up with weaker solutions?

We built a tool called AutoStyle that did just this, by using existing software engineering static-analysis tools to identify “better styled” code (empirically, we found that a low “ABC score”, which counts for assignments, branches, and conditions, was a good proxy for conciseness), analyzing the abstract syntax trees of correct submissions, and arranging them into a tree whose root represents (one of the) “best” solutions and in which an edge connects a child to a parent if the child is within a threshold Zhang-Shasha edit distance of the parent. We then find a “chain” of transformations from any given student’s solution to the root, and propose the required transformations as hints to the student to gradually refine their code.

<video controls preload="metadata" style="max-width:100%" src="{{ site.baseurl }}/assets/uploads/Autostyle-figures-movies.mp4"></video>

We did a randomized controlled trial [[1]](#ref-autostyle-its2016) in which students were asked to continue to improve and resubmit their code until the style “score” exceeded some threshold. Students who received automated restructuring hints from AutoStyle produced statistically significantly better-styled code than a control group who were given the same style guidelines but no hints.

But this promising result was dampened by other findings. In our study, the best results were achieved by students whose overall “game plan” for writing the code was sound (i.e. close to that of an experienced programmer); in that case, AST-based style hints would get them the rest of the way there. But students who started with a poor game plan–usually because they failed to recognize that the coding problem lent itself to the use of particular patterns or idioms–were unable to use the hints productively; the best advice to them would basically be “start over with a different game plan.” This suggested that *before* asking students to write code and receive hints, we should ensure that they had identified the correct “game plan” (programming pattern) for solving the problem.

Second, we subsequently found [[2]](#ref-autostyle-las2017) that while working with the AutoStyle “tutor” helps students write better code, they are not able to transfer that knowledge once the tutor’s scaffolding is removed. Part of the reason for this lack of transfer is that novice students cannot always *recognize* beautiful code, so they don’t share an expert’s opinion that that code is better [[3]](#ref-autostyle-readability-comprehension-icse2019), but we noted that exposure to AutoStyle did improve their ability to recognize beautiful code.

We concluded that we needed to (a) repeatedly expose students to “expert” programming patterns so that they would be sure to recognize them when appropriate for a programming problem, and (b) find a way to elicit from the student some evidence that they knew which pattern was appropriate to use for a given problem, *before* starting to write code for the problem and getting style feedback. Those observations ultimately led to our work on [Scaffolding the Learning of Programming Patterns and Subgoal Decomposition.]({{ site.baseurl }}/projects/faded-parsons/)

## References

1. <a id="ref-autostyle-its2016"></a>Rohan Roy Choudhury, HeZheng Yin and Armando Fox. “Scale-Driven Automatic Hint Generation for Coding Style.” *13th International Conference on Intelligent Tutoring Systems (ITS 2016)*, 2016. [PDF]({{ site.baseurl }}/assets/papers/autostyle-its2016.pdf)
2. <a id="ref-autostyle-las2017"></a>Eliane S. Wiese, Michael Yen, Antares Chen, Lucas A. Santos and Armando Fox. “Teaching Students to Recognize and Implement Good Coding Style.” *L@S 2017: Proceedings of the Fourth ACM Conference on Learning at Scale*, 2017. [PDF]({{ site.baseurl }}/assets/papers/autostyle-las2017.pdf)
3. <a id="ref-autostyle-readability-comprehension-icse2019"></a>Eliane Wiese, Anna Rafferty and Armando Fox. “Linking Code Readability, Structure, and Comprehension Among Novices: It's Complicated.” *2019 International Conference on Software Engineering (ICSE 2019), Software Engineering, Education, and Training Track (SEET)*, 2019. [PDF]({{ site.baseurl }}/assets/papers/autostyle-readability-comprehension-icse2019.pdf)
