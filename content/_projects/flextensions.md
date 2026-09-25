---
title: "Flextensions"
subtitle: null
description: "What happens when a student is faced with multiple fixed deadlines for formative assessments and cannot meet them all? Our hypothesis is that students may “cut their losses” by simply not turning in some of the work, if the late…"
order: 3
active: true
card_image: null
categories:
  - Course Logistics
---

<!-- Migrated from https://acelab.berkeley.edu/projects/flextensions/ (last modified 2023-10-06). Content may be out of date. -->

**Researchers:**

- Faculty: Armando Fox, Lisa Yan, Narges Norouzi
- Undergraduate researchers: Dana Benedicto, Charisse Liu, Jordan Schwartz, Yuerou Tang, Jacob Yin
- Alumni: Madison Bohannan, Fuzail Shakir

**What happens when a student is faced with multiple fixed deadlines for formative assessments and cannot meet them all?** Our hypothesis is that students may “cut their losses” by simply not turning in some of the work, if the late penalty is so large that they wouldn’t get the points. This results in *reduced learning* because the student is forgoing practice-with-feedback that they might otherwise have attempted if they thought the “calculus of grading” would justify it, and all because of the presence of a fixed deadline. This scenario works directly against the goals of [mastery learning]({{ site.baseurl }}/projects/cbt/) and those of adaptive equity-based grading. Indeed, one of the “checklist items” for implementing equity-based grading is flexible deadlines. That is, requesting an extension should be destigmatized, and within reasonable limits, extensions should be penalty-free, to remove any *disincentive* for spending more time with practice materials.

**What would it take to practically implement such a flexible extension policy?**

1. It must be possible for late work to be graded “off schedule” without requiring excessive staff effort. In many of our large courses, this problem is solved by autograders. Our courses use a variety of systems for submission and autograding of student work, including Canvas, Gradescope, OKpy, and PrairieLearn.
2. The management and tracking of extension requests, including (ideally) automatically adjusting submit deadlines in the LMS or other submission mechanism, must be highly automated to avoid requiring staff effort.

The *Flextension pipeline* consists of:

- A **[Google Form](https://forms.gle/m25EswwXMpq6vqrp7)** that students fill out to request an extension on a specific assessment
- A **[Google Sheet](https://docs.google.com/spreadsheets/d/1BabID1n6fPgeuuO4-1r3mkoQ9Nx5dquNwdsET75In1E/edit#gid=790260459)** that collects form submissions and includes Google Cloud logic to do the following:
  - Process form data in combination with a student’s “record” (which includes DSP status and prior extension requests) to enter either an auto-approval or manual-approval flow.
  - Sends updates to staff through a **Slack Webhook**, enabling simple internal discussion of student cases through Slack threads.
  - Sends updates to students through the **CS 162 Mailserver** via **CS 61A’s RPC Interface**.
  - Optionally publishes assignment extensions to one or more **Gradescope** assignments.

Depending on course policy, instructors can set a threshold number of days for automatic granting of extensions; longer ones trigger an email to the student that they need to meet with a course staff member to ensure there isn’t a systemic problem that will just cascade to more extensions later in the semester. *Anecdotally, many students are pleasantly surprised when course staff reach out to them to ask if everything’s OK, rather than to badger them about a late submission.*

We are in the process of analyzing data from several courses using Flextensions in the past several semesters. We hope to demonstrate that Flextensions have a positive effect on student affect, have a non-negative effect on overall student learning as measured by grades on individual assessments and the course overall, and require minimal additional staff time or effort; and that we therefore encourage all courses meeting the above criteria consider adopting the practice.

The Flextensions Pipeline addresses all of these challenges, significantly **reducing course staff workload** while (we hope) **improving quality-of-life for students**.
