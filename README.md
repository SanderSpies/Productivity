Productivity
============

A guide for optimal Front End productivity. Note that is especially targetted towards Single Page Applications.

What causes slow downs in FE productivity?
---
- Unclear what the consequences are of a user action due to events triggered all over the place
- Not clear what is being rendered on the screen
- Anything that is implicit (dependency injection, magical binding)
  
  At first this might seem totally awesome, but the next developer also needs to understand what happens. And that is where dependency injection, and two-way binding fall short in my experience. Other developers should be able to easily understand the flow within the application. Therefore I prefer to be explicit, even if that takes several lines extra.
- Wrong separation of concerns
- Not using different layers of abstraction
- MVC in general is a bringer of pain

  "Game engine" approach is better
- Slow build environment
- No control over FE build environment
- Being too nice when using JSHint or CSSLint
- No time for refactoring
- No proper components: CSS coupled to everything, elements, ids or attributes
- Separation based on technology instead of features
- Wrong backend implementation: either by sending blocks of HTML or not proper REST
- "Everybody can do everything" mentality
- Working against the language

How to speed up FE productivity?
---
TODO
