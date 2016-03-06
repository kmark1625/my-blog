---
title: Why use Middleman to build a static site?
date: 2016-03-03
tags: middleman
---

This blog post seeks to explain why you should use Middleman to generate your next static site. Middleman is an excellent tool which shares a lot of similarities with Ruby on Rails. In building a static site with Middleman, you are able to learn a lot of core concepts in Ruby on Rails or transfer your common workflows from Ruby on Rails to Middleman.

First of all, you might ask why should you use a static site instead of something like a Ruby on Rails site. A static site is much easier to host (doesn't require additional server/database overhead other than the files themselves) and often results in performance and security benefits. A static site generator helps in the creation of a static site by allowing you to write code in embedded ruby, use css preprocessors or markdown, and the static site generator will translate the code into base css/html.

There are many concepts with a Middleman site that is similar to rails. Middleman shares a similar asset pipeline along with file structure. In addition, you can continue to write embedded ruby into your files.

# Assets
Middleman brings with it an asset pipeline which is very similar to that of rails. We can bring in most of the relevant assets we need through the Gemfile, just as we would in rails.

# Partials and Embedded Ruby
We are able to split out parts of our code into partials. We can then use these partials in our html just as we would in a rails project. We can pass in variable values. Data can be stored in a database.yaml file which can be read in and easily updated with new information.