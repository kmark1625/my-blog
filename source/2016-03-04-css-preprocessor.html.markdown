---
title: What is a CSS Pre-Processor and why should you should use one?
date: 2016-03-04
tags: Bourbon, Neat, Bitters
---

This article seeks to explain what a CSS preprocessor is and why you should use it. In addition, I explain my own experience using Bourbon along with Neat and Bitters to style sites. These tools allow for an easy way to maintain modular code in your CSS as well as get a good-looking site off the ground quickly.

One of the main benefits of a CSS preprocessor is its ability to allow you to have more modular code for your CSS. You can have partials that apply to different parts of your application and then load them in with @import. In addition, you can use all of the normal features of CSS and pick and choose from mixins that are available. Mixins are a useful way to get a group of CSS stylings with minimal code. Another main feature is the ability to have variable names. This can be useful for font-stylings or other settings as you can apply a set of styles once and change it out on the fly easily.

There is not a good reason to not use a CSS pre-processor. Mostly because you can style it with your normal CSS but have additional features. A great way to keep your styles organized is with nesting. Sass allows you to nest your CSS styles which makes it a lot easier to keep a coherent grouping. This does not, however, offer any performance benefits but it is useful to reduce complexity of your CSS for large sites.

# Bourbon, Neat, and Bitters
Bourbon is a library built for Sass. It includes vendor prefixes and mixins that allow you to write CSS more concisely. Neat is a semantic grid framework for Sass. Bitters is a predefined set of styles and mixins for use with Bourbon. All three of these tools are open-source projects maintained by Thoughtbot.

I had a great time using these tools to style my blog website. The use of partials helped to keep my .scss files organized. It also gave me greater control to style different aspects of my website. The semantic grid system provided by Neat was easy to use to layout content on a page.