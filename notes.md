# Avant-garde Computer Programming

## Separation of Concerns

History and its lessons.

<!--
Throughout history the paradigms of computer programs have changed and shifted
but there remain a few immutable thruths - "decoupling" the UI from the stuff
that the user needn't know about.
-->

_"Decoupling"_ and cringe.

"Separation of concerns".

_Concerns_ and ways to _separate_ them.

<!--
I used to cringe because I had a strong SUBCONSCIOUS feeling that I
didn't know what this word "decoupling" meant and it tortured me, and then for years I
searched for an answer
-->

A long and winding road.

## How

<!--
So what is the answer?

It is two-fold. The easy part is to follow established principles
that stem from what we have seen about computer programs throughout
history. This is the easy part.

The second is to build intuition. This is the hard part.
-->

- Principles.
- Intuition.

### Principles

- **SOLID**: **SOLI**D **D**oesn't Mean Anything.
- **DDD**: **D**omain **D**riven **D**evelopment.

Computers can prove ideas about code.

#### **SOLID**

Consequence of observing the history.

A convoluted set of vague concepts.

Separation of concerns.

Robert C. Martin - Clean Architecture.

Ports and adapters.

Pervasive layers: domain, infrastructure (externalities, data), API.

DIP.

#### *DDD*

The domain matters.

Domain language.

Technical domains.

The domain and externalities.

Data formats and DTOs.

Principles need not be taken literally.

### Intuition

#### STOP. THINK.

Autopilot day job.

Do not settle on a random solution that looks aesthetically pleasing.

Why?

Why is this bad?

Why is this good?

Why am I frustrated?

Why do I enjoy this?

Nothing is easy, everything takes time.

Write code outside your day job.

#### Cognitive Complexity

Amount of information needed at once.

Interface complexity.

Implementation complexity.

Point: managing complexity.

<!--
Example: caching, disable = zero timeout, I need a slide for this.
Adding another adapter class just to move an if from one place to
another is an example of what is commonly thought to be "good" but
actually only increases complexity.

If the caching behavior is complex, then it is worth drawing a boundary,
but it's still rarely a good idea to expose the user to both MyClass
and CachingMyClass and force them to do the plumbing, etc.
-->
Edge cases.

Information hiding.

Conclusion: restrictions. Perl (or Bash) vs. Rust.

#### Documentation

Interface docs.

Long function names.

Short function names with good documentation.

Implementation docs.

"Write short functions" mantra.

#### Testing

Help not hinder.

Footguns.

Test at the highest level of abstraction.

Only mock externalities.

Testing the public API layer. Convenient because it's the highest level
and it doesn't change often.

Testing the internal API layer. Less convenient because it might change
more often orthogonally to to the underlying implementation, still
not a terrible idea for certain applications.

Testing the UI layer. Can be a pretty bad idea because changes orthogonal
to the implementation might be very common.

##### Refactoring

Hand-in-hand with tests.

Unavoidable.

Code rot.

Knowledge comes with time.

Code adapts to knowledge by refactoring.

### Computers Can Prove Ideas About Code

Corollary of complexity: restrictions liberate.

Tools of restriction.

Invariants.

Newtypes.

Units. (ETH and wei, BTC and sats.)

Enums and strongly typed state machines.

Refactoring.

## Examples

Problem statement, solution, why is it bad or good?

### Bad

#### Zap

The team structure.

Over-engineering.

Production issues can commonly be a symptom of bad design.

Implementing simple things becomes impossible, talk about that exchange thing.

Talk about EBOs, it's so funny that I still remember this.

#### WalletConnect

100 lines of Rust to send a value down a channel.

Point of the above: avoid a dynamic allocation that wasn't needed anyway, mocking.

Running circles with dependencies, `Conn`s everywhere.

### Good

Driver example.

The bad: calling it driver.

The good: DDD and the separation of domain layer,
which modules know about which other modules and why that makes sense.

How to isolate and seclude the bad code when you can't get rid of it.

Coupler network, a good example of good separation of concerns without DDD.

exa

Although it doesn't demonstrate DDD, the code is really good,
features a very good separation of concerns and good code documentation.

Git support is decoupled well.
