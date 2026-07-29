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

## 



