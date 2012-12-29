---
layout: post
title: "Introducing Project P"
description: "Introduction blog post to a Node.js application."
category: blog
tags: ['projects', 'node', 'JavaScript', 'Project P']
---
{% include JB/setup %}

I've been working on a little Node app lately. Since I don't plan on releasing it as open source in the immediate
future, and I don't want to announce it as a product, I'll simply refer to it as Project P.

Project P uses Express on the backend, relatively plain (albeit complex) JS on the front-end, and Socket.io to bridge
the gap between. This is the first Node project I've started on since adopting a more test-driven approach to design and
development.

I played around a bit with using just raw asserts. That seemed to work fairly well, except for the lack of test runner
with pretty output. Since my prior TDD experience is in Ruby/Rails, I wanted to look into what was out there for Node.
Mocha looked popular, so I gave it a try.

My Rails tests are all thoroughly RSpec based, so Mocha's support for that BDD style was a nice bonus. Added `mocha -R
spec` as my `test` script in my `package.json` and I was off to the races with `npm test`. Within a couple minutes of
getting things running, I found my first bonus feature: Global variable leak detection. Among my various refactorings,
I'd forgotten to add a declaration for one of my variables in one of my functions. Since Mocha couldn't see where I
declared it, it decided to warn me. Call me easy, but that was enough to convert me fully to the church of Mocha.

Project P has also given me yet another opportunity for some drive-by contributions to an open source project. In this
case I wanted to use google-diff-match-patch, but I wanted to have a dependency entry for it in my `package.json`. Turns
out somebody had already created a package for it called [googlediff](https://github.com/shimondoodkin/googlediff), but
it was a little out of date. Having an itch to scratch, I forked, updated, tested, and then submitted a [pull
request](https://github.com/shimondoodkin/googlediff/pull/3). Side note: `npm link` is an awesome way to test modules
during development. This seems to be my main mode of open source contribution, which is probably why just over half of
my github repos are forks.

I'll have to set aside some time soon to write about using [Browserify](https://github.com/substack/node-browserify) to
share code between the client and server. I've found this particularly useful for things like model testing, which isn't
browser dependent for the most part.