# Crafting Easing Curves for UI

Easing curves are what takes decent animations and make them FANTASTIC! The problem is that understanding how easing curves work can be a bit confusing. I hope to clear that up through this post, which stems from the interest in timing functions my previous post [After Effects to CSS](https://medium.com/@ryan_brownhill/after-effects-to-css-79225c1d767e). People wanted a better understanding about how easing curves work and how do design your own.

An easing curve is a line that defines the acceleration pattern on a graph. Easing curves are commonly referred by many other names such as “Motion Curves”, “Timing Functions”, “Bezier Curves” or just “Curves”. The different shapes of an easing curves also has keywords like “ease in” , “ease out”, or “ease in out”.

## How Easing Curves Work

Easing curves are created via an (X,Y) axis. The meanings of the X and the Y can vary from application to application. For example, the (X,Y) meaning within After Effects is different than Cinema 4D. Within development, the meaning of the X and the Y states stays pretty consistent. Which is defined as Percent of Animation(Y) over Time(X).

![Animation Percent over Time Graph](/Users/ryanbrownhill/Dropbox/_4_SIDE_PROJECTS/BLOGS/Posts/Easing_Curves/curve--linear.png)

What does that this easing curve look like when put into practice? That's where the concepts of timing and spacing come into play.

### Timing and Spacing

Timing and Spacing Timing is the duration for an animation to finish. Spacing is the space between each “frame” but in our case it is the space between the each percent of animation. Below I have showcased how this spacing relates to an easing curve. Think of vertical = fast and horizontal = slow.

![Linear spacing of Graph & Dot](/Users/ryanbrownhill/Dropbox/_4_SIDE_PROJECTS/BLOGS/main-blog/images/posts/easing-curves/spacing--linear.png) [Created In CodePen](http://codepen.io/ryanbrownhill/pen/EjVdeY)

![Ease In Spacing of Graph & Dot](/Users/ryanbrownhill/Dropbox/_4_SIDE_PROJECTS/BLOGS/main-blog/images/posts/easing-curves/spacing--easein.png)[Created In CodePen](http://codepen.io/ryanbrownhill/pen/VLvEre)

![Ease Out Spacing of Graph & Dot](/Users/ryanbrownhill/Dropbox/_4_SIDE_PROJECTS/BLOGS/main-blog/images/posts/easing-curves/spacing--easeout.png) [Created In CodePen](http://codepen.io/ryanbrownhill/pen/MwaPBZ)


## Easing Curves within Development

Easing curves within development are called “Timing Functions” which are mathematical equations that create a bezier curve that defines the acceleration pattern on a graph. The function that is commonly used within development is the cubic-bezier. That is what I will be going over in this post.

The structure of a cubic-bezier:

![Cubic Bezier](/Users/ryanbrownhill/Dropbox/_4_SIDE_PROJECTS/BLOGS/main-blog/images/posts/easing-curves/cubicbezier-06.png)

Within most programming languages, there are some predefined easing curves like `ease-in`, `ease-out`, and `ease-in-out`. Be sure to check the documentation to see which curves are predefined. Below I listed the easing curves that are predefined within CSS.

`ease-in` = `cubic-bezier(.42, 0, 1, 1)`

`ease-out` = `cubic-bezier(0, 0, .58, 1)`

`ease-in-out` = `cubic-bezier(.42, 0, .58, 1)`

### Defining Easing Curves in CSS

**Global**

In CSS there is the “global” ease that can be defined in the object class, this applies the same ease to every keyframe. For example, if you have a bounce, the animation will bounce at every keyframe.

[CodePen](http://codepen.io/ryanbrownhill/pen/JdYmqG)

```scss
.object-class {
 animation-name: animation-rocks;
 animation-timing-function: easeOutBounce;
}
```

**Per Keyframe**

You can get more precise with eases by defining them within keyframes. It is important to keep in mind that the easing curve is defined in the percentage value *before* you want the ease to happen.

[CodePen](http://codepen.io/ryanbrownhill/pen/JdYejX)

```scss
@keyframes animation-name {
  0% {
    animation-timing-function:ease-out;
  }
  23% {
    animation-timing-function:ease-in;
  }
  50% {
    animation-timing-function:cubic-bezier(.5,0,.5,1.5);
  }
  76% {
    animation-timing-function:cubic-bezier(0,0,0,1);
  }
  100% {
  }
}
```

## Designing an Easing Curve


Designing an Easing Curve People always ask me, “What easing curve do I use and when?” My answer — it really depends on the scenario. There is not one easing curve that work for absolutely everything. This is a key component of designing motion — crafting these curves. Easing curves are commonly designed after physics within the real world, but don’t always follow those rules. The real world is a great place to gain inspiration for animation. For example, no object in the real world starts at full velocity and immediately stops — like a linear easing curve does. Objects always have some kind of acceleration or decelation. This is just one of the concepts Disney has outlined in the [12 principles of animation](https://vimeo.com/93206523), which is largely based on physics.

When crafting an easing curve keep in mind that vertical is fast and horizontal is slow. The curve you create should be dependent on the interaction. You can create many different types of curves within the (X,Y) grid.

[Insert Sine ,etc ]

In addition crafting curves within the frame, one can break the frame! Breaking the frame will cause the animation to go outside of the values in between the keyframes. Breaking the frame can create bounce or anticipation effects.

[Insert Bounce]

There are many tools for creating cubic bezier's here are a few:

- [cubic-bezier.com](cubic-bezier.com)
- [Cesear](http://matthewlein.com/ceaser/)
- [Easings.net](http://easings.net/)


### Curved Delays

The concept of easing curves doesn’t just apply to a single animation but can applied to delays! Which can be really fun when there are many elements on the screen animating. Here is an example of a Sine wave delay. I created this by created a Sass loop and using Compass math helpers to calculate Sine.


<iframe height='355' scrolling='no' src='//codepen.io/ryanbrownhill/embed/NqGxgr/?height=355&theme-id=14830' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/ryanbrownhill/pen/NqGxgr/'>Sine Delay Loop</a> by Ryan Brownhill (<a href='http://codepen.io/ryanbrownhill'>@ryanbrownhill</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>
