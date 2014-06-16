Productivity
============

Based on my personal experiences.

What causes slow downs in FE productivity?
---
- Unclear what the consequences are of a user action due to events triggered all over the place
- Not clear what is being rendered on the screen
- Anything that is implicit (dependency injection, magical binding)
  
  At first this might seem totally awesome, but the next developer also needs to understand what happens. And that is where dependency injection, and two-way binding fall short in my experience. Other developers should be able to easily understand the flow within the application. Therefore I prefer to be explicit, even if that takes several lines extra.

  Also when calling functions, it should be clear what your intention is. The other developer shouldn't be guessing too much for your intentions. So don't write ``addNode('Honda', true, false, 1, 20)``, but write something like: ``addNode({label: 'Honda', hasChildren: true, alternateStyling: false, notifications: 1, nrOfChildren: 20})``
  
- Wrong separation of concerns
  
The separation between views and templates are a wrong separation of concerns, and 2 way binding is a way to facilitate this already broken abstraction. Reactjs solved this in the correct way by ensuring there is no difference between views and templates. 

- Not using different layers of abstraction

  Logic in views, calling the back end from a view, handling user actions in views - can result into potential problems when refactoring. 

- MVC in general is a bringer of pain

  "Game engine" approach is much better in my experience.
- Slow build environment

  If it takes longer then 5 minutes to get your new environment up and running, you are doing it wrong.
- No control over FE build environment
- Being too nice when using JSHint or CSSLint
- No time for refactoring
- CSS coupled to everything, elements, ids or attributes
  
  This can make refactoring rather hard, therefore: use only classes with prefixes. Max. depth level should be 3.
- Separation based on technology instead of functionality
- Wrong backend implementation: either by sending blocks of HTML or not proper REST
- "Everybody can do everything" mentality without the proper architecture
- Working against the language

How to speed up FE productivity?
---
TODO
