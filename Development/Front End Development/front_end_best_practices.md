# Front End Best Practices <!-- omit in toc --> 

## Table of Contents <!-- omit in toc --> 
- [Priorities](#priorities)
- [Mobile First](#mobile-first)
- [Componentizing/Modularization](#componentizingmodularization)
- [Organizing Styles](#organizing-styles)
  - [Scss vs Css](#scss-vs-css)
  - [Top-down reading](#top-down-reading)
  - [CSS Naming](#css-naming)
  - [Html](#html)
  - [Scss Variables](#scss-variables)
  - [Inline documentation](#inline-documentation)
- [Libraries](#libraries)

## Priorities

- Minimalist
- Readability
- Mobile First
- Componentization

## Mobile First

We work with mobile-first design and development. This means that we build first for the smallest screens and then add custom styling as we go up.

Supporting the smaller screens first forces us to have all the important information and content available for mobile screens first rather. The issue with supporting desktop first, is that squishing down from a large, spaceous screen to a tiny one is much harder.

If you take a look at our .scss files, you should see the breakpoints declared by using ``min-width`` rather than ``max-width``. This starts the new settings at the minimum width and does not stop the settings at a ``max-width``. The settings just gets overwritten if we need to by a bigger ``min-width`` *if* we need to.

Mobile-first is of course not right for every scenario but for our audience and our needs, it works.

## Componentizing/Modularization

We break down different parts of our front end into logical, smaller pieces. This includes styling that corresponds with a React component. This makes it easier to find and manage what styles relate to what html. If done correctly, it can also keep down issues with name space/naming collisions.

Global styling should be minimal.

## Organizing Styles

### Scss vs Css

Scss enables us to take advantage of nesting. It can better show relationships between the components each style is targetting.

### Top-down reading

While developing, it's much easier to organize your styles in the same order as how your html is organized. This could be more challenging if we lumped our the styling information together, but by separating out our styles in the same way html is separated out, we end up with one javascript file on one window pane and a the scss file in a second window pane.

As we scroll down the work we do for the html, we also scroll down the scss file.

### CSS Naming

Labeling for css styles should be done with care. Do not pollute the namespaces unnecessarily. If it's easy enough to just target the only h1 within a section with an ID, just target the h1 there rather than giving it an ID or a class if there is no other need to do so.

- ID's should be used for only one item that will use it in the global space. Therefore, use this sparingly.
- Classes should only be used for styles that will be reused. Ideally only within your component. At this point, the components are already built for reusability. So if we need to rewrite the same style in a different component, consider writing a new component rather than writing a reusable class.

### Html

- Do not have unnecessary html tags. The more minimal the html, the better. Is that extra div really necessary? Is there a more minimal way of doing it.
- Use descriptive tags. If we have a header in a section, do not use a ``<div>`` tag for it. Use one of the ``h`` tags instead. This will help accessibility for devices such as screen readers. It would also remove unnecessary classes or ID's that might be used to described the header as a header. Divs are better used for helping to organize content for positioning.
- Add extra labels like alt attributes. This will also help with accessibility. Check [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML) for more information on what's available for what tag.

### Scss Variables

- Use descriptive scss variables for settings we need to use such as branding colors.

### Inline documentation

- It's good to add comments especially in javascript files and styles to describe what it is for an what something is doing.

## Libraries

Keep use of outside libraries to a minimum. Check licenses and make sure they are open source and give us permission to use their libraries.