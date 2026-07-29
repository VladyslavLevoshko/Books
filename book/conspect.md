# Pragmatic Programming Philosophy

## Think About Your Work

Understand that some tasks are difficult and may require significant time and effort.

Recognizing this beforehand gives you the patience and persistence needed to complete the work instead of giving up when problems appear.

---

## Care About Your Craft

Software development is a craft.

Every day, improve your existing skills and expand your toolbox by learning new technologies, techniques, and approaches.

A good developer continuously invests in becoming better.

---

## Provide Options, Don't Make Excuses

When facing a problem, do not simply explain why something cannot be done.

A professional developer provides possible solutions, explains trade-offs, and helps find the best approach.

---

## Don't Live with Broken Windows

In software, disorder accumulates over time. Developers often call this process **software rot**.

Small problems that are ignored today can become large problems in the future.

Do not accept:
- poor code quality;
- broken design decisions;
- unnecessary complexity;
- outdated documentation.

Fix problems before they grow.

---

## Be a Catalyst for Change

You do not need to wait for others to improve the system.

Small improvements introduced by one person can influence the entire team.

A good developer helps create a culture of continuous improvement.

---

## Remember the Big Picture

Do not focus only on the current task. Always keep the overall system and its long-term goals in mind.

A system can slowly degrade without anyone noticing, just like the famous example of a frog staying in gradually heating water.

Do not become that frog.

Regularly ask:

- Are we moving in the right direction?
- Are current decisions helping the future of the project?
- Are we solving the real problem?

The scope and quality of the system should be defined as part of its requirements.

---

## The Early Bird Might Get the Worm, But What Happens to the Early Worm?

Being first is not always the same as being successful.

Speed is important, but it should not come at the cost of quality, maintainability, and understanding.

A good solution at the right time is often better than a rushed solution.

---

# Managing Your Knowledge Portfolio

Managing knowledge is similar to managing a financial portfolio.

## Principles

### 1. Invest Regularly

Serious investors invest consistently.

Learning should become a habit, not something done only when problems appear.

---

### 2. Diversify Your Knowledge

Do not focus only on one technology.

Learn different areas:

- programming languages;
- databases;
- architecture;
- operating systems;
- algorithms;
- communication skills.

A broader perspective helps you make better decisions.

---

### 3. Balance Risk and Reward

Balance familiar technologies with new technologies.

Use stable knowledge for reliability, but explore new areas for growth.

---

### 4. Buy Low and Sell High

In terms of learning:

- learn emerging technologies before they become mainstream;
- abandon outdated approaches when better solutions appear.

---

### 5. Review and Rebalance Regularly

Your knowledge portfolio should evolve.

Regularly evaluate:

- what skills are becoming outdated;
- what areas are valuable;
- what should be learned next.

---

# Ways to Expand Your Knowledge

## Take Courses

Look for interesting courses at:

- universities;
- online platforms;
- conferences;
- professional communities.

---

## Participate in User Groups

Do not only listen.

Actively participate:

- ask questions;
- share experience;
- discuss solutions.

Isolation can slow professional growth.

---

## Stay Current

Follow:

- technical blogs;
- engineering articles;
- books;
- journals;
- newsletters.

Explore technologies outside your current project to avoid a narrow perspective.

---

## Critically Analyze What You Read and Hear

Do not blindly accept every recommendation.

Ask:

- Why does this approach work?
- What are the trade-offs?
- In which situations would it fail?

Good developers understand principles, not just rules.

# DRY Principle and Duplication

## DRY (Don't Repeat Yourself)

One of the most important principles in the Pragmatic Programmer's toolbox is **DRY**.

The main idea:

> Every piece of knowledge should have a single, authoritative representation.

If the same information is stored in multiple places, sooner or later these copies will diverge.

Duplication increases the risk of inconsistency because every change must be applied in multiple places.

---

## Comments Can Violate DRY

Comments are useful, but they can accidentally introduce duplication.

A comment that repeats information already present in the code creates another place where the same knowledge must be maintained.

Example:

```ts
const MAX_USERS = 100;

Single Source of Truth
Every important piece of knowledge should have one authoritative source.
Other parts of the system should depend on this source or be generated automatically.
Benefits:
fewer inconsistencies;
easier maintenance;
safer changes.

Duplication Is Sometimes Inevitable
The goal of DRY is not to remove every repeated line of code.
The real goal is to avoid duplicated knowledge.
Two similar pieces of code can represent different concepts and may evolve independently.
Removing such duplication can create unnecessary coupling and complex abstractions.

Key Takeaways
Avoid duplicated knowledge.
Do not create abstractions before they are needed.
Prefer simple solutions over unnecessary flexibility.
Intentional duplication is acceptable when the risks are understood and documented