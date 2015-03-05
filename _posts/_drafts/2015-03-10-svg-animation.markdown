---
layout: post
title:  "SVG Animations"
date:   2015-03-10 17:42:59
categories: animation fed
---

# SVG Animation
---

SVG stands for Scalable Vector Graphics. Which means you can scale the graphic and it will never ever pixelate. This post I am going to be diving into animating these SVGs!

Animating SVGs is **SUPER EXCITING!** There are so many attibutes you can animate and you can even style the animation with CSS! Its like animating with a shape layer in After Effects. Its like having a GIF that you can scale, style and tweek!
Its basically a GIF on steroids.


## 1. Exporting SVG

There are many applications that export SVG in the world but I only have experience with Illustrator & Sketch. When exporting from these applications I noticed some of differences. Overall, Illustrator exports messy SVG code and Sketch exported clean code with some extra perks. For example: Sketch exports the path name to a `id="path-name"` in the SVG file, and does the same for groups on the `<g>` tag. This is saves a ton of time so that when you write your animations you have the id selector there ready for you to control. So overall when exporting SVG file - I recommend Sketch. 

If you want to know more about SVG Exporting, Alex Walker did a post about this on [sitepoint.](http://www.sitepoint.com/designers-guide-working-with-svg/)


## 2. Styling Properties

There are so many properties you can use when animating SVGs its AMAZING! You can look at the [SVG Styling Properties Documentation](http://www.w3.org/TR/SVG2/styling.html#SVGStylingProperties) to see all the attributes. Some of these styling you might be familiar with from CSS. Below I have pulled out the styling properties that are unique to SVGs.

![svg-properties](../../images/posts/svg-animation/svg-properties.png)


## 3. SVG Animation Syntax

### What is SMIL

Now for the nerdy stuff, so what is SMIL and how does it relate to SVG? SVG is a host language for SMIL Animation. SVG's animations have the contstraints and features that are permitted by the [SMIL Animation Spec](http://www.w3.org/TR/2001/REC-smil-animation-20010904/). SVG's also has SVG-specific rules stated in [W3 SVG Animation Spec](http://www.w3.org/TR/SVG/animate.html).

SVG animations are simular to CSS animations as they have keyframes, easing curves, etc. but, it's just presented in a different syntax. One of the downsides of SMIL is that it doesn't work with any version of IE and Opera Mini. [CanIUse](http://caniuse.com/#feat=svg-smil)

### Animate Tag

`<animate/>`tag structure
 Specify the target for the animation using `xlink:href`
 `attributeName` & `attributeType`

### How I Animate

* Define Shape/Path for Animation
* Define Property to Animate
* List out Property Values
* Define Percentage over time for those values.
* Map out the easing curves between keyframes.

### Other Cool things:

* Animate along path with `<animateMotion>`
* Interactivity (kinda) `begin="click"` 


	
This is a walk through of just SVG animation but mostly everything you can animate in CSS you can apply to the SVG through the #id-selector and CSS keyframes or transition animations.


## 4. Easing Curves

So how to you make the BEAUTIFUL easing curves with SVG animation? I will show you how! 		
![SVG Animation Breakdown](../../images/posts/svg-animation/svg-ani-03.png)

Above you see the CSS `@keyframe` animation structure on the left and on the right the SVG animation structure. I added color highlights so you can see where the attributes go when translated from CSS to SVG.
Note there is no CSS property called `cy`. I have it there as a place holder to gain a better understanding of SVG animation structure.

#### CSS to SMIL:
* `cy` property = `attributeName="cy"`
* `cy` value = `values`
* `@keyframes` animation % = `keyTimes`
* `animation-tmining-function` = `keySplines`


Things that don't translate from CSS to SVG animation are pre-defined cubic-bezier's. For example: `ease-in` in CSS = `cubic-bezier(0.47, 0, 0.745, 0.715)` in SVG. There is a great tool by [Lea Verou](http://cubic-bezier.com/#.17,.67,.83,.67) that does these calculations for you. To understand more about CSS animation check out my other post [Ae to CSS](https://medium.com/@ryan_brownhill/after-effects-to-css-79225c1d767e).



## Resources:
[Slide Deck](http://slides.com/sarasoueidan/styling-animating-svgs-with-css#/10)

[Where I found the solution to easing curves for svg's](https://msdn.microsoft.com/en-us/library/ms533119%28v=vs.85%29.aspx)
		
[CSS Tricks for SMIL animations](https://css-tricks.com/guide-svg-animations-smil/)

[SVG Animatable Attributes](http://www.w3.org/TR/SVG2/animate.html#AnimationAttributesAndProperties)

#### Other Notes:

* Optimizing SVGs
* [Peter Collingridge's Tool](http://petercollingridge.appspot.com/svg-editor)
* Standalone Tools
	* [SVG-O](https://github.com/svg/svgo) 
	* [SVG GUI](https://github.com/svg/svgo-gui)
	`<object type="image/svg+xml" data="mySVG.svg"><!--fallback--></object>`
			