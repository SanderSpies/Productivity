Productivity
============

Based on my personal views and experiences.

What causes slow downs in FE productivity?
---
- Unclear what the consequences are of a user action due to events triggered all over the place
- Not clear what is being rendered on the screen
- Anything that is implicit (dependency injection, magical binding)
  
  At first this might seem totally awesome, but the next developer also needs to understand what happens. And that is where dependency injection, and two-way binding fall short in my experience. Other developers should be able to easily understand the flow within the application. Therefore I prefer to be explicit, even if that takes several lines extra.

  Also when calling functions, it should be clear what your intention is. The other developer shouldn't be guessing too much for your intentions. So don't write ``addNode('Honda', true, false, 1, 20)``, but write something like: ``addNode({label: 'Honda', hasChildren: true, alternateStyling: false, notifications: 1, nrOfChildren: 20})``
  
- Wrong separation of concerns
  
  The separation between views and templates is a wrong separation of concerns, and template languages and 2 way binding is a way to facilitate this already broken abstraction. React.js solved this in the correct way by ensuring there is no difference between views and templates. Note that within the current Reactjs solution, only HTML is merged into JS. CSS is still left outside of the component, while ideally it should be inside of the component (FB is [thinking of it](https://github.com/reactjs/react-future/blob/master/04%20-%20Layout/Inline%20Style%20Extension.md). 

And I did my own attempt of [fixing it](https://github.com/SanderSpies/react-style). Also note that I create a [all:initial polyfill](https://github.com/SanderSpies/all-initial) specifically for react-style  which disables css cascading from parent elements.

- Using mutable objects models
  
  Although this is the current status quo in the Front End world, it comes with a set of problems. Versioning, undo, redo, etc. aren't easily possible with mutable objects. And doing this later is basically a no no. Also checking what has changed in a mutable model is a very cumbersome process.

Instead you more likely want to do a change, easily jump back to a previous version or next version, do versioning, and even more important: you want to easily see what has changed. Hence you want to use immutable objects.

Also you want to translate your business domain in the right way, which means the complete model with the relationships as you expect them. Not the simplistic models that for instance Backbone offers. 

I did an attempt with [WorldState.js](https://github.com/SanderSpies/worldstate.js) to solve this, however I believe I will need to go back to the drawing board. The new idea is to generate an immutable model from SQL database metadata, probably using Facebook's [immutable-js](https://github.com/facebook/immutable-js). 

- Not using different layers of abstraction

  Logic in views, calling the back end from a view, handling user actions in views - can result into potential problems when refactoring. 

- MVC in general is a bringer of pain

  "Game engine" approach is much better in my experience.
- Slow build environment

  If it takes longer then 5 minutes to get your new environment up and running, you are doing it wrong. And during development changes should happen around a second. Why? Mental context switching occurs if the developer needs to wait too long.
  
- No control over FE build environment
- Being too nice when using JSHint or CSSLint

  Try to run a tight ship when it comes to coding. 
- No time for refactoring

  Often architecture is done wrong in the beginning and organizations have the habit of continueing to build upon that architecture. Refactoring is a necessary evil, as developers are learning and experiencing what works best during the development process. Mistakes should be expected. Honesty is an important factor here also, by saying what works and doesn't.
  
- CSS coupled to everything, elements, ids or attributes
  
  This can make refactoring rather hard, therefore: use only classes with prefixes. Max. depth level should be 3. More ideally the CSS should directly be part of the component, and not separated by technology.
- Separation based on technology instead of functionality
- Wrong backend implementation: either by sending blocks of HTML or not proper REST.

  The backend should write an API for the world, not just a certain use case. 
- "Everybody can do everything" mentality without the proper architecture.
  Every developer has a certain expertise, and everything isn't it. So let the developer be experts in their own area, and be guided in the right way in lesser known areas. A good architecture is vital here, but most likely isn't in place.
- Not understanding JavaScript or CSS or HTML
- Working against the language
- Developer mentality

  

How to speed up FE productivity?
---
TODO
