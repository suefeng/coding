# Abstraction

Abstraction
DRYness
OOD
Performance
Extensibility
Single responsibility principle
Abstraction

Can apply to CSS as well since speed, efficiency, reuse, maintainability, scalability are important to all code

Separate semantics from skin by using class names rather than tag names in CSS so there can be more flexibility in the way HTML structures are and they can change without needing to change CSS as much

rarely use location-dependent styles
instead of styling a specific `<h2>` with `.myObject h2 {…}`, create and apply a class that describes the `<h2>` in question, like `<h2 class=“category”>`.
 
This gives you the assurance that: (1) all unclassed `<h2>`s will look the same; (2) all elements with the category class (called a mixin) will look the same; and 3) you won’t need to create an override style for the case when you actually do want .myObject h2 to look like the normal `<h2>`.