---
layout: post
title:  "SVG Animations"
date:   2015-03-10 17:42:59
categories: animation fed
---

# SVG Animation
---

SVG stands for Scalable Vector Graphics. With SVG's you can animate the [SVG Styling Properties](http://www.w3.org/TR/SVG2/styling.html#SVGStylingProperties). Some of these styling you might be familiar with from CSS. I dive into some of these properties below.


## Exporting SVG

There are many applications that export SVG in the world but I only have experience with Illustrator & Sketch. When exporting from these applications I noticed some of differences. Overall, Illustrator exports messy SVG code and Sketch exported clean code with some extra perks. For example: Sketch exports the path name to a `id="path-name"` in the SVG file, and does the same for groups on the `<g>` tag. This is saves a ton of time so that when you write your animations either in CSS or SMIL you have the id selector there ready for you to control. So overall when exporting SVG file - I recommend Sketch. 

If you want to know more about SVG Exporting, Alex Walker did a post about this on [sitepoint.](http://www.sitepoint.com/designers-guide-working-with-svg/)


## What is SMIL

Now for the nerdy stuff, so what is SMIL and how does it relate to SVG? SVG is a host language for SMIL Animation. SVG's animations have the contstraints and features that are permitted by the [SMIL Animation Spec](http://www.w3.org/TR/2001/REC-smil-animation-20010904/). SVG's also has SVG-specific rules stated in [W3 SVG Animation Spec](http://www.w3.org/TR/SVG/animate.html).

SVG animations are simular to CSS animations as they have keyframes, easing curves, etc. Its just presented in a different syntax. One of the downsides of SMIL is that it doesn't work with any version of IE and Opera Mini. [CanIUse](http://caniuse.com/#feat=svg-smil)



## Animation Attributes



## Easing Curves

So how to you make the BEAUTIFUL easing curves with SVG animation? I will show you how! 		
![SVG Animation Breakdown](../../images/posts/svg-animation/svg-ani-03.png)

Above you see the CSS `@keyframe` animation structure on the left and on the right the SVG animation structure. I added color highlights so you can see where the attributes go when translated from CSS to SVG.
Note there is no CSS property called `cy`. I have it there as a place holder to gain a better understanding of SVG animation structure. To understand more about CSS animation check out my other post [Ae to CSS](https://medium.com/@ryan_brownhill/after-effects-to-css-79225c1d767e).


#### CSS to SMIL:
* `cy` property = `attributeName="cy"`
* `cy` value = `values`
* `@keyframes` animation % = `keyTimes`
* `animation-tmining-function` = `keySplines`


Things that don't translate from CSS to SVG animation are pre-defined cubic-bezier's. For example: `ease-in` in CSS = `cubic-bezier(0.47, 0, 0.745, 0.715)` in SVG. There is a great tool by [Lea Verou](http://cubic-bezier.com/#.17,.67,.83,.67) that does these calculations for you.



## Resources:
[Slide Deck](http://slides.com/sarasoueidan/styling-animating-svgs-with-css#/10)

[Where I found the solution to easing curves for svg's](https://msdn.microsoft.com/en-us/library/ms533119%28v=vs.85%29.aspx)
		
[CSS Tricks for SMIL animations](https://css-tricks.com/guide-svg-animations-smil/)

[SVG Animatable Attributes](http://www.w3.org/TR/SVG2/animate.html#AnimationAttributesAndProperties)

#### Other Notes:
#### `animation tag`
* Specify the target for the animation using `xlink:href`

#### `attributeName` & `attributeType`
* `attributeName` only takes one value 
	* This is where CSS has an advantage to SMIL

	* Optimizing SVGs
	* [Peter Collingridge's Tool](http://petercollingridge.appspot.com/svg-editor)
	* Standalone Tools
		* [SVG-O](https://github.com/svg/svgo) 
		* [SVG GUI](https://github.com/svg/svgo-gui)
		`<object type="image/svg+xml" data="mySVG.svg"><!--fallback--></object>`
		