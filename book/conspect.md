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

const MAX_USERS = 100;

---

## Single Source of Truth

Every important piece of knowledge should have one authoritative source.
Other parts of the system should depend on this source or be generated automatically.
Benefits:
fewer inconsistencies;
easier maintenance;
safer changes.

---

## Duplication Is Sometimes Inevitable
The goal of DRY is not to remove every repeated line of code.
The real goal is to avoid duplicated knowledge.
Two similar pieces of code can represent different concepts and may evolve independently.
Removing such duplication can create unnecessary coupling and complex abstractions.

---

## Accept the Risks
When duplication is intentional:
accept the risks;
document the reason;
make other developers aware of it.
Intentional duplication is often better than unnecessary complexity.

---

## Inadvertent Duplication
Sometimes developers create abstractions because they expect future changes.

Example:
function getValue() {
    return value;
}

The argument is:
"Maybe later we will need additional logic here."
However, adding abstractions without a real requirement can make the system harder to understand and maintain.

---

## Key Takeaways
Avoid duplicated knowledge.
Do not create abstractions before they are needed.
Prefer simple solutions over unnecessary flexibility.
Intentional duplication is acceptable when the risks are understood and documented

---

## YAGNI (You Aren't Gonna Need It)
YAGNI is a principle that says:
Do not add functionality until it is actually needed.
Avoid creating solutions for problems that do not exist yet.
Premature abstractions often lead to:
unnecessary complexity;
harder maintenance;
more difficult design decisions.
A simple solution today is usually better than a flexible solution that may never be needed.

---

## DRY vs YAGNI
These principles can sometimes conflict.
DRY says:
Avoid repeating knowledge.
YAGNI says:
Do not create abstractions before they are necessary.
The balance:
remove meaningful duplication;
avoid unnecessary abstractions;
let real requirements guide design decisions. 

---

## Shared Knowledge
Developers should communicate openly without fear of appearing inexperienced.
Asking questions is part of professional growth.
A team should create a shared knowledge base containing:
solutions to common problems;
architectural decisions;
technical explanations;
lessons learned.
Reading other people's code is one of the best ways to improve.
Understanding different approaches helps develop better engineering judgment.

---

# Orthogonality and Modularity

## Orthogonality

Orthogonality is a design principle where components of a system are independent from each other.

Changing one part of the system should not unexpectedly affect unrelated parts.

A system with high dependency between components becomes fragile:

> When components of any system are highly interdependent, there is no such thing as a local fix.

Every change can have unexpected consequences.

---

## Benefits of Orthogonal Design

An orthogonal system provides:

- lower risk of changes;
- easier testing;
- better maintainability;
- improved productivity;
- easier debugging.

When a change is isolated to one component, developers can reason about the system more effectively.

---

## Local Changes Should Stay Local

A well-designed system allows developers to make changes without understanding the entire codebase.

If modifying one feature requires changing many unrelated components, the architecture has strong coupling.

The goal:

> A change should affect the smallest possible part of the system.

---

# High Cohesion and Low Coupling

Two important characteristics of good modular design are:

## High Cohesion

A module should focus on one logically related responsibility.

A module with high cohesion:

- has a clear purpose;
- contains related functionality;
- is easier to understand and modify.

Example:

Good:

UserService
 ├── createUser()
 ├── updateUser()
 └── deleteUser()

Bad:

Utils
 ├── createUser()
 ├── sendEmail()
 ├── calculateTax()
 └── resizeImage()

---

## Low Coupling
Modules should have minimal dependencies on each other.
A module should know as little as possible about the internal implementation of other modules.
Low coupling makes it easier to:
replace components;
test modules independently;
modify implementation details.

---
## Orthogonality and Teams
Orthogonal architecture also improves teamwork.
When responsibilities are clearly separated, teams can work on different parts of the system with fewer conflicts.
Organizing teams around independent system components provides similar benefits to encapsulation in code:
changes are limited to one area;
ownership is clearer;
responsibilities are easier to manage.

---
## Orthogonality and Testing
Orthogonal systems are easier to test because components have limited interactions.
A module should be testable independently.
If testing one component requires connecting a large part of the system, it may indicate:
poor separation of responsibilities;
excessive coupling;
weak architecture.
The same principle applies to debugging:
The fewer components affected by a change, the easier it is to find and fix problems.

---

## Orthogonality Beyond Code
Orthogonality should also apply to documentation and processes.
For example:
changing documentation style should not require changing its content;
changing deployment details should not require rewriting business logic.
Independent parts should remain independent.

---

## Avoid Global State
Global objects often create hidden dependencies.
They make it harder to understand:
who changes the data;
when the data changes;
which parts of the system depend on it.
Prefer explicit dependencies and controlled communication.

---

## Aspect-Oriented Programming (AOP)
Aspect-Oriented Programming is a technique for separating cross-cutting concerns from the main business logic.
Cross-cutting concerns are behaviors that appear in many parts of a system:
logging;
security;
authentication;
monitoring;
transaction management.
Instead of repeating the same logic everywhere, AOP allows these behaviors to be defined separately and automatically applied where needed.
Example:
Without AOP:

function createUser() {
    log();
    checkPermission();
    saveUser();
}

The same logging and security code may appear in many places.
With AOP:

Business Logic
       +
Cross-cutting Concerns

The main code remains focused on its responsibility.

---

## Communication Between Modules
Avoid unnecessary direct dependencies between modules.
Instead of modules calling each other directly, they can communicate through:
events;
messages;
interfaces.
Example:
Direct coupling:
OrderService → EmailService
Event-based communication:
OrderService
      |
      ↓
 OrderCreated Event
      |
      ↓
EmailService
This allows components to evolve independently.

---

## Object Encapsulation
When an object needs to change its state, ask the object to perform the operation itself.
Prefer:
account.withdraw(amount);
instead of:
account.balance -= amount;
The object should control its own rules and invariants.
Benefits:
less dependency on implementation details;
easier future changes;
better encapsulation.

---

## Key Takeaways
Keep components independent.
Prefer high cohesion and low coupling.
Local changes should remain local.
Avoid hidden dependencies and global state.
Design modules around clear responsibilities.
Use events and interfaces to reduce direct coupling.
Good architecture makes testing, debugging, and future changes easier.

# Software Architecture

## There Are No Final Decisions

Good architecture should allow changes.

Technology choices, platforms, deployment methods, and external dependencies may change over time.

A flexible system should allow these changes without rewriting the entire application.

Avoid making decisions that are difficult to reverse unless there is a strong reason.

---

## Design for Change

The future is uncertain.

Requirements evolve, technologies become outdated, and business rules change.

A good architecture isolates areas that are likely to change.

Examples of things that often change:

- databases;
- frameworks;
- external services;
- deployment environments;
- user interfaces.

The goal is not to predict the future perfectly, but to make future changes less expensive.

---

# Use Tracer Bullets to Find the Target

## Tracer Code Approach

A **tracer code** approach is creating a minimal working version of a system that goes through all important architectural layers.

Instead of building one part completely and integrating everything later, create a small end-to-end implementation first.

Example:

User Interface
       |
       ↓
Application Logic
       |
       ↓
Database
The tracer implementation proves that all parts can communicate correctly.

---

## Benefits of Tracer Code
Tracer code helps:
validate architecture early;
discover integration problems sooner;
avoid large integration phases;
provide a foundation for future development.
A small working system is easier to improve than a large unfinished system.

---

## Incremental Development
New functionality can be added gradually:
Create a minimal working path.
Add one feature.
Write tests.
Improve the design.
Repeat.
Small changes are easier to test and problems are easier to locate.
Avoid the "big bang" approach where everything is integrated at the end.

---

## Keep Business Rules Separate from Implementation Details
Code should express business concepts, not technical details.
The system should speak the language of the problem domain.
Bad:
database.updateUserRecord(id, data);
Better:
customer.changeAddress(newAddress);
The second example describes a business action instead of a technical operation.

---

## Domain-Specific Languages (DSL)
A Domain-Specific Language (DSL) is a language designed for a specific problem domain.
Unlike general-purpose languages:
TypeScript;
Java;
Python;
a DSL uses concepts and terminology from a specific area.
Examples:
SQL for databases;
regular expressions for text patterns;
configuration languages.
A good DSL allows developers and domain experts to communicate using the same concepts.

---

## Put Abstractions in Code, Details in Metadata
Do not hard-code information that is likely to change.
Changing data should be stored separately from the program logic.
Bad:
if (user.role === "admin") {
    allowAccess();
}
when roles constantly change.
Better:
Configuration / Metadata
        |
        ↓
Application Logic
Benefits:
easier changes;
less code modification;
better flexibility.

---

## Cooperative Configuration
Cooperative Configuration is an approach where system components can configure themselves and adapt to changing conditions.
Instead of hard-coding every possible behavior, components use external configuration and metadata.
This allows systems to evolve without modifying core logic.

---

## Avoid Fragile Object Design
Objects should be designed as if they can be called at any moment and in any order.
A fragile design requires a strict sequence:
create()
   ↓
initialize()
   ↓
prepare()
   ↓
show()
   ↓
use()
If an object only works after a specific sequence of calls, it is difficult to understand and maintain.

---

## Constructors Should Create Valid Objects
A constructor should create a complete and usable object.

---

## Avoid separating creation and initialization.
Bad:
const user = new User();
user.initialize();
The object exists in an incomplete state.
Better:
const user = new User(name, email);
The object should not allow invalid states.

---

## Maintain Invariants
An invariant is a condition that should always remain true.
After every public method call, the object should still satisfy its invariants.
Example:
A bank account:
Balance cannot be negative
Every operation must preserve this rule.
Good objects protect their own correctness.

---

## Always Design for Concurrency
Concurrency is not only a source of complexity.
It is also a test of architecture quality.
Design systems so they:
do not depend on hidden execution order;
avoid unnecessary shared state;
minimize temporal dependencies.
Even if concurrency is not required today, such design usually produces:
more modular code;
fewer hidden dependencies;
more predictable behavior.

# Estimation and Project Management

## Estimations Are Models, Not Predictions

An estimate is not a guarantee.

Every estimate is based on a model of the problem and the assumptions behind it.

A good estimate should include:

- what is included;
- what is excluded;
- what assumptions were made;
- what level of uncertainty exists.

---

# Understand the Scope Before Estimating

Before giving an estimate, first understand what exactly needs to be built.

Questions to clarify:

- Is only the backend required?
- Are tests included?
- Is documentation required?
- Are deployment and configuration included?
- Are external dependencies involved?

Without a clear scope, an estimate has little value.

Example:

> If the task includes only API implementation, the estimate is 2 days.  
> If it also includes tests, documentation, and deployment, the estimate changes.

The assumptions are part of the estimate.

---

# Do Not Give False Precision

The precision of an estimate should match the level of confidence.

Do not create an illusion of accuracy.

Bad:

The task will take 17 hours and 30 minutes.

---
#Build a Model of the Problem
Every estimate is based on a simplified model.
A model:
identifies important elements;
breaks the problem into smaller parts;
helps understand complexity;
allows comparison with previous experience.
A model is always an approximation.
The goal is to find a balance between simplicity and accuracy. 

---

## Learn From Existing Solutions
Before creating your own estimation model, look at how similar problems were solved before.
Previous experience can provide:
realistic assumptions;
common risks;
expected complexity;
better estimates.
You do not need an identical project.
Similar problems often provide valuable information.

---

## Estimates Should Evolve
Do not try to predict the entire project perfectly at the beginning.
As the project develops:
requirements become clearer;
risks become visible;
technical decisions are made.
Therefore, estimates should be updated together with new information.
A changing estimate is not a failure.
It is a more accurate reflection of reality. 

---

## What to Say When Asked for an Estimate
When you do not have enough information:
"I'll get back to you."
A professional developer does not guess.
Take time to:
understand requirements;
analyze risks;
build a model;
provide a realistic estimate.

---

## Algorithm Complexity and Big O Notation
The O() Notation
Big O notation describes how the resource usage of an algorithm grows as the input size increases.
It describes:
time complexity;
memory complexity;
scalability.
It does not describe the exact execution time 

---

## Think About Growth, Not Exact Speed
Do not only write algorithms.
Learn to estimate how their complexity grows.
Understanding Big O helps answer questions like:
Will this solution work with millions of records?
How will performance change as data grows?
Is this approach scalable?

---

## Do Not Optimize Too Early
The algorithm with the best theoretical complexity is not always the best practical choice.
Consider:
input size;
implementation complexity;
maintenance cost;
real performance measurements.
A good approach:
Create a simple solution.
Measure performance.
Identify real bottlenecks.
Optimize only where necessary. 

---

## Managing Technical Debt
Technical debt should not exist only in someone's memory.
Record it.
A good team:
documents technical debt;
tracks future improvements;
communicates possible risks.
Refactoring should be a planned process, not random cleanup. 

---

## Refactoring Rules
Do not refactor and add new functionality at the same time.
These are separate activities.
Before refactoring:
make sure you have good tests;
run tests frequently;
verify that behavior has not changed.
Tests provide confidence during structural changes. 

---

# Tools and Automation

## Automate Repetitive Tasks

Professional developers should control computers through automation, not only through manual interaction.

If a process is repeated regularly, do not rely on memory and discipline.

Turn repeated procedures into:

- scripts;
- tools;
- automated workflows.

Automation provides:

- reproducibility;
- fewer human errors;
- saved time;
- consistent results.

---

# Use the Power of Your Tools

A professional developer should know their tools deeply.

Using one well-mastered editor often improves productivity.

The goal is not choosing a specific editor.

The goal is mastering your chosen tool:

- know shortcuts;
- understand workflows;
- reduce unnecessary actions;
- make common operations automatic.

Good tools reduce cognitive load and allow you to focus on solving problems.

---

# Always Use Version Control

Every project should use a version control system.

Version control provides:

- history of changes;
- collaboration;
- ability to restore previous versions;
- safer experimentation.

Git is not only a backup tool.

It is a tool for managing the evolution of software.

---

# Write Code That Writes Code

Developers should not only write application code.

They should also create tools that help them write code faster and more reliably.

Examples:

- code generators;
- scripts;
- automation tools;
- build systems;
- development utilities.

A small investment in automation can save many hours in the future.

---

# Debugging Is a Normal Part of Development

Bugs are inevitable.

Debugging should not become a search for someone to blame.

The goal is:

- find the cause;
- fix the problem;
- prevent it from happening again.

A professional team treats bugs as opportunities to improve the system.

---

# Generate, Don't Maintain

Whenever possible, avoid manually maintaining duplicated information.

Store knowledge in one place and generate everything else.

Example:

Database Schema

        ↓

Generated Types

        ↓

Application Code

---

## Design with Contracts
Design by Contract
Objects and functions should define clear expectations.
A contract consists of:
Preconditions — what must be true before execution;
Postconditions — what must be true after execution;
Invariants — what must always remain true.

---

##Preconditions
Conditions that must be satisfied before calling a function.
Example:
withdraw(amount)
Precondition:
Amount must be positive.

---
##Postconditions
Conditions guaranteed after successful execution.
Example:
After withdrawal, account balance is updated correctly.

---

## Invariants
Rules that must always remain true.
Example:
A bank account balance cannot violate business rules.
Invariants protect the correctness of the system.

---

##Semantic Invariants
Some invariants describe not only technical correctness but also the meaning of the system.
These are called semantic invariants.
They represent important truths that should remain valid under all circumstances.
Examples:
a user cannot own the same resource twice;
an order cannot be completed without payment;
a deleted account cannot perform operations.
Well-defined semantic invariants help guide:
architecture decisions;
error handling;
trade-offs.
One strong invariant can prevent many incorrect decisions across the system.

---

# Testing and Quality

## Verification and Validation

Testing is not only about checking whether the code works.

There are two different questions:

## Verification

**Verification** answers:

> Are we building the product correctly?

It checks whether the system was implemented according to its specification.

Examples:

- Does the code follow the design?
- Are requirements implemented correctly?
- Are algorithms and processes working as expected?

---

## Validation

**Validation** answers:

> Are we building the right product?

It checks whether the system actually solves the user's problem.

Examples:

- Does the application help users achieve their goals?
- Does the workflow match real user needs?
- Is the product useful in practice?

A system can be correctly implemented but still solve the wrong problem.

---

# Test Your Tests

## Use Saboteurs to Test Your Testing

Passing tests do not automatically mean that testing is effective.

A good way to verify test quality is to intentionally introduce small mistakes into the code and check whether tests detect them.

Example:

Original code:

function calculatePrice(price: number) {
    return price * 0.9;
} 

Introduce a bug:
function calculatePrice(price: number) {
    return price * 0.8;
}
If tests still pass, the tests are not detecting important errors.

---

##Why Test Quality Matters
A green test suite only proves that tests passed.
It does not prove that the tests are capable of finding problems.
Good tests should:
detect incorrect behavior;
protect important rules;
fail when the system is broken.

---

##Test State Coverage, Not Code Coverage
Code Coverage
Code coverage shows what percentage of code was executed during testing.
However, high code coverage does not guarantee high-quality tests.
Example:
A test may execute a line of code but never verify whether the result is correct.

---

##State Coverage
A better approach is testing different states and transitions of the system.
Many bugs appear not because a line of code is incorrect, but because the system enters an invalid state.
Test:
valid states;
invalid states;
transitions between states;
edge cases;
error conditions.
The important question is not:
"Did this code run?"
The important question is:
"Did we verify the important behaviors of the system?"

---

#Test Contracts
Unit tests should verify not only normal usage but also violations of contracts.
Tests should check:
preconditions;
postconditions;
invariants.
Example:
withdraw(amount)
Possible tests:
amount is positive;
balance is sufficient;
balance remains valid after withdrawal.
A module should maintain correct behavior even when receiving incorrect input. 

---

##Make Testing Easy
Testing should be simple and always available.
Running tests should be almost as easy as running the application.
A good development environment provides:
fast test execution;
automatic test runs;
clear error messages;
easy access for every developer.
If testing is difficult, people will avoid doing it.

---

##Refactoring Requires Good Tests
Do not refactor and add new functionality at the same time.
These activities have different goals:
Refactoring
Improves internal structure without changing external behavior.
Adding Features
Changes system behavior by introducing new functionality.
Mixing them makes it harder to understand what caused a problem.

---

##Safe Refactoring Process
Before refactoring:
Make sure important behavior is covered by tests.
Run tests before changes.
Refactor in small steps.
Run tests frequently.
Tests provide confidence that the system still behaves correctly.

---

##Debugging and Quality
Bugs are a normal part of software development.
When a bug appears, the goal is not to find someone responsible.
The goal is:
understand the cause;
fix the problem;
prevent similar problems in the future.
A good debugging process improves the entire system.

---

# Requirements and Users

## Work with a User to Think Like a User

Developers should understand not only what the system does, but also how users interact with it.

Sometimes the user interface is the entire system from the user's perspective.

A system can have:

- excellent architecture;
- clean code;
- reliable infrastructure;

but still fail if the user experience is inconvenient or does not match the real workflow.

---

# Understand the Real Problem

Requirements are not only a list of features.

They should describe:

- what problem the user is trying to solve;
- what goals they want to achieve;
- what constraints exist;
- how the system fits into their workflow.

A good developer tries to understand the user's perspective instead of only implementing instructions.

---

# Use a Project Glossary

Complex projects require a shared vocabulary.

A **project glossary** defines important terms and concepts used by the team.

Benefits:

- fewer misunderstandings;
- better communication;
- clearer requirements;
- consistent terminology across code and documentation.

The names used in the system should reflect the language of the domain.

---

# Find Real Constraints

When solving complex problems, look for real limitations.

Do not automatically accept every assumption as a rule.

Sometimes a problem appears impossible only because it is being solved within false constraints.

Ask:

- Is this limitation technical or just historical?
- Is there another way to approach the problem?
- Are we solving the actual problem?

Good engineers challenge assumptions.

---

# Start with a Prototype

If you do not know where to begin, start with a prototype.

A prototype helps:

- explore unknown areas;
- validate ideas;
- receive feedback;
- discover hidden requirements.

A small experiment is often more valuable than a long discussion about a perfect solution.

---

# The Specification Trap

## What Is the Specification Trap?

The specification trap is blindly following a specification without questioning whether it represents the real user need.

A specification can:

- contain incorrect assumptions;
- describe a specific solution instead of the actual problem;
- become outdated over time.

A good developer understands the purpose behind requirements, not only their wording.

---

# Requirements Are Models of Reality

Any specification is an interpretation of reality.

There is always a risk that information changes while passing through multiple layers:

```text
User

 ↓

Analyst

 ↓

Specification

 ↓

Developer

 ↓

Implementation

Each step can introduce misunderstandings.
The goal is to reduce the distance between the real user problem and the implemented solution.

---

##Prototyping and Feedback
Sometimes requirements cannot be fully understood in advance.
Instead of trying to create a perfect specification immediately:
Build a small prototype.
Show it to users.
Collect feedback.
Improve understanding.
Adjust the solution.
Users often cannot accurately imagine a future system from documents alone.
A working example provides much better feedback.

---

##Models Are Not Reality
A model is only a simplified representation of reality.
If developers work only with the model, they may implement the analyst's interpretation instead of the user's actual need.
Always verify assumptions with real feedback.

---

##User Interaction Is Part of the System
The system is not only its internal implementation.
The user's interaction with the system is also part of the product.
Consider:
usability;
workflow;
clarity;
speed;
reliability.
A technically correct system can still fail if it does not fit the user's needs.

# Teams and Communication

## Communication Is a Technical Skill

Software development is not only about writing code.

A large part of engineering is communication:

- understanding requirements;
- explaining decisions;
- sharing knowledge;
- discussing problems;
- giving and receiving feedback.

Poor communication creates misunderstandings, duplicated work, and unnecessary complexity.

---

# Listen to People

One of the most important techniques for effective communication is simple:

> Listen to people.

Before trying to convince others, understand their perspective.

Good communication requires:

- asking questions;
- paying attention;
- understanding different viewpoints;
- respecting other people's experience.

---

# Communicate Without Fear

Developers should communicate openly without fear of appearing inexperienced.

Asking questions is not a weakness.

A question asked early can prevent:

- incorrect assumptions;
- wasted development time;
- wrong architectural decisions.

A strong engineering culture allows people to say:

- "I do not understand this."
- "I need more information."
- "I see a possible problem."

---

# Share Knowledge

A team should create a shared knowledge base.

Useful knowledge should not remain only in one person's memory.

Examples:

- solutions to common problems;
- architectural decisions;
- debugging experiences;
- project conventions;
- technical explanations.

Shared knowledge makes teams more resilient.

---

# Read Other People's Code

Reading existing code is one of the best ways to improve as a developer.

It helps you learn:

- different approaches;
- design patterns;
- trade-offs;
- common mistakes.

Your own experience is limited, but studying other solutions expands your engineering perspective.

---

# Respond to Communication

Professional communication includes reliability.

Always respond to messages and requests, even if the answer is not immediate.

A simple response:

> "I received this. I will get back to you later."

is better than silence.

Reliable communication builds trust.

---

# Keep Communication Organized

Organize important information:

- emails;
- documents;
- technical notes;
- decisions.

Good organization reduces the time spent searching for information.

---

# Organize Teams Around Capabilities

Teams are often more effective when organized around system capabilities instead of professional roles.

Example:

Less effective:

Frontend Team
Backend Team
Database Team
Testing Team
More effective:
Payments Team

Authentication Team

User Management Team
A capability-focused team contains different skills needed to deliver a complete part of the system.

---

##Benefits of Functional Teams
Functional teams provide similar benefits to encapsulation in code.
A team responsible for one area of the product:
has clearer ownership;
understands its domain better;
reduces communication overhead;
can make decisions faster.
Changes are more likely to remain inside one area instead of affecting the entire organization.

---

##Team Structure and Software Structure
The way teams communicate often influences the architecture they create.
If teams are separated by technical layers, the system may naturally become tightly coupled.
If teams are organized around independent capabilities, the architecture is more likely to become modular.
Good organizational structure supports good software design.

---

##Avoid Hero Culture
A system should not depend on one person who knows everything.
If only one developer understands an important part of the project, it creates a risk.
Share knowledge through:
documentation;
code reviews;
discussions;
mentoring.
A strong team is built around shared understanding, not individual heroes.

---

# Code Quality and Professional Development

## Code Is Written for People

Code is not only executed by computers.

Most of the time, code is read, modified, and maintained by other developers.

Readable code reduces the cost of understanding and changing the system.

Good code should be:

- clear;
- simple;
- consistent;
- easy to modify.

---

# Code and Documentation Should Be Readable

Code and documentation are created for people.

They should be written with the same care as any other form of communication.

Quality includes:

- meaningful names;
- clear structure;
- consistent style;
- understandable explanations.

The goal is not to make code look impressive.

The goal is to make future changes easier.

---

# Professional Responsibility

Your code is your responsibility.

A developer's work is not only about completing tasks.

It is also about ensuring that the result is:

- understandable;
- maintainable;
- reliable.

Your code should represent your professional standards.

---

# Sign Your Work

A professional developer takes ownership of their work.

A signature in code represents responsibility:

> "I created this, and I stand behind its quality."

This does not mean that mistakes never happen.

It means that you care about the result and continuously improve your work.

---

# Simplicity Matters

Simple solutions are usually easier to:

- understand;
- test;
- modify;
- debug.

Complexity should be introduced only when it provides real value.

Avoid adding unnecessary layers, abstractions, or patterns without a clear reason.

---

# Do Not Let Existing Code Dictate Future Code

Existing code is not always the correct model for future development.

Legacy decisions may have been made because of:

- old requirements;
- previous limitations;
- missing knowledge;
- temporary solutions.

Respect existing systems, but do not allow them to prevent better designs.

---

# Separate Views from Models

A system should separate different responsibilities.

The presentation layer should not contain business logic.

The model should represent the data and rules of the system.

The view should represent how information is presented.

Benefits:

- easier testing;
- easier changes;
- better separation of concerns.

---

# Blackboard Pattern

The **Blackboard pattern** is an architectural approach where multiple independent components work through a shared data area.

Instead of components directly depending on each other:

Component A
      |
      ↓
  Blackboard
      ↑
      |
Component B 

Components contribute information and react to changes in the shared workspace. 

---

##Benefits of the Blackboard Pattern
This approach is useful for complex systems where:
multiple solutions are possible;
different components analyze the same information;
knowledge is built gradually.
Examples:
artificial intelligence systems;
image recognition;
complex decision systems.

---

##Use the Right Level of Abstraction
Good abstractions hide unnecessary details while exposing important concepts.
A bad abstraction:
hides useful information;
creates confusion;
makes simple tasks harder.
A good abstraction:
represents the real concept;
reduces complexity;
remains understandable.

---

#Avoid Overengineering
Not every problem requires a complex architecture.
Before introducing:
patterns;
frameworks;
abstractions;
additional layers;
ask:
Is there a real problem?
Does this complexity provide value?
Will this make future changes easier?
The best design is not the most complicated one.
It is the simplest design that solves the problem well. 

---

# Advanced Design Principles

## Separation of Concerns

A system should be divided into separate parts where each part has its own responsibility.

Each component should focus on one specific concern instead of handling unrelated tasks.

Examples of concerns:

- business logic;
- data storage;
- user interface;
- authentication;
- logging.

Benefits:

- easier understanding;
- easier testing;
- easier modification;
- reduced complexity.

---

# MVC as a General Design Pattern

**Model-View-Controller (MVC)** is often associated with graphical user interfaces, but the idea is much broader.

MVC is a way to separate responsibilities.

---

## Model

The model represents the actual data and business rules of the system.

The model:

- contains application logic;
- represents the state of the system;
- does not depend on how data is displayed.

---

## View

The view is an interpretation of the model.

It represents information in a way suitable for the user or another system.

The view should not contain business rules.

---

## Controller

The controller coordinates interactions.

It receives input, performs actions, and connects the model with the view.

The controller should coordinate, not contain the entire business logic.

---

# MVC Outside User Interfaces

MVC is not limited to graphical applications.

The same idea can be applied to many systems:

- command-line applications;
- APIs;
- background services;
- data processing systems.

The main idea is separation between:

- data and rules;
- presentation;
- coordination.

---

# Prefer Communication Through Abstractions

Components should communicate through stable interfaces instead of depending on implementation details.

Bad:

Service A
    |
    ↓
Internal details of Service B 
