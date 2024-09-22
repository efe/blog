---
layout: post
title: "TouchDesigner Beginners Workshop"
---

I've been interested in interactive programming tools like [Processing](https://processing.org/), [p5.js](https://p5js.org/) and [Touchdesigner](https://derivative.ca/showcase) as hobby. [@setupdesigns](https://instagram.com/setupdesigns), [Lucinda Dilworth](https://instagram.com/dil.worth), [Elekktronaut](https://instagram.com/elekktronaut) and [Josh Baptista](https://instagram.com/joshbaptista_) are good inspirations about it.

Even though I tried to learn TouchDesigner, node-based programming has a steep learning curve for those who come from procedural programmin like me. Therefore, I was so eager to join to the [Touchdesigner Beginners Workshop](https://creativecodingutrecht.nl/en/archive/td-beginners) in the [Utrecht Creative Coding](https://creativecodingutrecht.nl/en).

![Touchdesigner Beginners Workshop 1](/public/images/posts/touchdesigner-beginners-workshop/touchdesigner-workshop-1.jpg "Touchdesigner Beginners Workshop 1")
![Touchdesigner Beginners Workshop 2](/public/images/posts/touchdesigner-beginners-workshop/touchdesigner-workshop-2.jpg "Touchdesigner Beginners Workshop 2")

Let me summarize the insights I gained during this workshop.

- [LFO](https://docs.derivative.ca/LFO_CHOP) is useful for getting signals. Sine, ramp and square functions are handy. Lowering the frequency slows it down.
- [Math](https://docs.derivative.ca/Math_CHOP) provides mapping.
- [Switch](https://docs.derivative.ca/Switch_TOP) is switch.
- [Null](https://docs.derivative.ca/Null_CHOP) works like a variable.
- [Transform](https://docs.derivative.ca/Transform_TOP) applies to object (e.g. circle).
- [Lag](https://derivative.ca/UserGuide/Lag_CHOP) is lag.
- [audioAnalysis](https://derivative.ca/UserGuide/Palette%3AaudioAnalysis) and [Select](https://docs.derivative.ca/Select_CHOP) are good for building a pipeline for music.
- [Out](https://docs.derivative.ca/Out_CHOPs) can be used to preview the completed project.

<iframe width="560" height="315" src="https://www.youtube.com/embed/mEWpBxeNj6g?si=LT4aNu_4wEeXibNt" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[Raul's workshop repository](https://github.com/Rauleal/TouchDesigner_Bauhaus_workshop) has lot's of cool examples.

I’m planning to make a project involving audio, an external API, and a projector this year. If I like it, it would be nice to experiment with the Kinect sensor as the next step.