---
layout: post
title: CSS Animation
category: CSS
tags: [css]
---

Quick note about CSS animation. 

## CSS Animation

CSS3 animation lets an element gradually change from one style to another.

Two steps:

1. Use `@keyframes` to define an animation.
2. Set this animation on an element with animation properties

We could set properties one-by-one or with following shorthand:

{% highlight css %}
animation: [animation-name] [animation-duration] [animation-timing-function] [animation-delay] [animation-iteration-count] [animation-direction] [animation-fill-mode] [animation-play-state];
{% endhighlight %}

## @keyframes

It defines what the animation looks like at each stage of the animation timeline. It is composed of:

* Name of the animation. For example, changeColor.
* Stages: From 0% to 100% to represent the whole process of animation
* CSS Properties: The CSS properties defined for each stage of the animation timeline.

Following example creates an animation called `changeColor` and assign it to `div:hover`:

{% highlight css %}
@keyframes changeColor {
  0% {
    background: red;
  }
  60% {
    background: blue;
  }
  100%{
    background: green;
  }
}

div:hover{
