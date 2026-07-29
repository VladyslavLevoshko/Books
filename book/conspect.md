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
Orthogonality and Teams
Orthogonal architecture also improves teamwork.
When responsibilities are clearly separated, teams can work on different parts of the system with fewer conflicts.
Organizing teams around independent system components provides similar benefits to encapsulation in code:
changes are limited to one area;
ownership is clearer;
responsibilities are easier to manage.
Orthogonality and Testing
Orthogonal systems are easier to test because components have limited interactions.
A module should be testable independently.
If testing one component requires connecting a large part of the system, it may indicate:
poor separation of responsibilities;
excessive coupling;
weak architecture.
The same principle applies to debugging:
The fewer components affected by a change, the easier it is to find and fix problems.
Orthogonality Beyond Code
Orthogonality should also apply to documentation and processes.
For example:
changing documentation style should not require changing its content;
changing deployment details should not require rewriting business logic.
Independent parts should remain independent.
Avoid Global State
Global objects often create hidden dependencies.
They make it harder to understand:
who changes the data;
when the data changes;
which parts of the system depend on it.
Prefer explicit dependencies and controlled communication.
Aspect-Oriented Programming (AOP)
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

Communication Between Modules
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
Object Encapsulation
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
Key Takeaways
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

```text
User Interface
       |
       ↓
Application Logic
       |
       ↓
Database
The tracer implementation proves that all parts can communicate correctly.
Benefits of Tracer Code
Tracer code helps:
validate architecture early;
discover integration problems sooner;
avoid large integration phases;
provide a foundation for future development.
A small working system is easier to improve than a large unfinished system.
Incremental Development
New functionality can be added gradually:
Create a minimal working path.
Add one feature.
Write tests.
Improve the design.
Repeat.
Small changes are easier to test and problems are easier to locate.
Avoid the "big bang" approach where everything is integrated at the end.
Keep Business Rules Separate from Implementation Details
Code should express business concepts, not technical details.
The system should speak the language of the problem domain.
Bad:
database.updateUserRecord(id, data);
Better:
customer.changeAddress(newAddress);
The second example describes a business action instead of a technical operation.
Domain-Specific Languages (DSL)
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
Put Abstractions in Code, Details in Metadata
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
Cooperative Configuration
Cooperative Configuration is an approach where system components can configure themselves and adapt to changing conditions.
Instead of hard-coding every possible behavior, components use external configuration and metadata.
This allows systems to evolve without modifying core logic.
Avoid Fragile Object Design
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
Constructors Should Create Valid Objects
A constructor should create a complete and usable object.
Avoid separating creation and initialization.
Bad:
const user = new User();
user.initialize();
The object exists in an incomplete state.
Better:
const user = new User(name, email);
The object should not allow invalid states.
Maintain Invariants
An invariant is a condition that should always remain true.
After every public method call, the object should still satisfy its invariants.
Example:
A bank account:
Balance cannot be negative
Every operation must preserve this rule.
Good objects protect their own correctness.
Always Design for Concurrency
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
Key Takeaways
Avoid irreversible decisions when possible.
Design architecture for change.
Use tracer implementations to validate ideas early.
Keep business rules separate from technical details.
Store changing information in metadata, not code.
Objects should protect their own invariants.
Good architecture reduces the cost of future changes.



