---
layout: post
title:  "Pair Programming with Github"
date:   2018-02-16 18:53:44 +0000
categories: pairing git github pair programming pear
author: morgan
---

In this post, I'll explore the tradeoffs of pairing, and how to make the best use of Github's new features when doing so.

{% include toc %}

## What is Pair Programming?

To quote the [wikipedia page](https://en.wikipedia.org/wiki/Pair_programming):

> Pair programming is an agile software development technique in which two programmers work together at one workstation. One, the driver, writes code while the other, the observer or navigator, reviews each line of code as it is typed in. The two programmers switch roles frequently.

These roles are actually quite important. It isn't just two people sat doing the work together, crucially the navigator:

* Doesn't write code.
* Ensures the working environment is set up for proper focus (Phones away, close slack, both parties are comfortable, snacks to hand, let's do this).
* Maps the course (What is our goal? Why? For who?)
* Maintains the focus on the task at hand (The goal or the failing test if you're doing TDD).
* Sets the direction on what do to next (What's the bigger picture?)
* Keeps track of new work that comes up as part of the coding exercise (e.g. refactoring, analytics, changes to dependencies).
* Reviews the work as it happens, challenging early where appropriate.
* Teaches the driver as they go, or conversely learns from the driver if they are less experienced.
* Get's stuck in if the pair reaches a blocker. Usually by asking stimulating open ended questions (What do we know? What can we test to find out more?)
* Removes blockers to the next task if more information is needed.

## What are the pros and cons of pairing?

Fundamentally, pairing is meant to increase the output of the programmers.  It does this through 
increasing code quality,
reducing the number of bugs,
and reducing interruptions.

It is also great for learning, both in terms of knowledge sharing and reducing your [bus factor](https://en.wikipedia.org/wiki/Bus_factor).

And I think most people overlook the benefits of a happy cohesive team of developers, in my opinion effective pairing really brings a bunch of developers together into a team.

These articles
[1](https://www.agilealliance.org/glossary/pairing/#q=~(filters~(postType~(~'page~'post~'aa_book~'aa_event_session~'aa_experience_report~'aa_glossary~'aa_research_paper~'aa_video)~tags~(~'pair*20programming))~searchTerm~'~sort~false~sortDirection~'asc~page~1))
 [2](https://blog.codinghorror.com/pair-programming-vs-code-reviews/)
 [3](https://raygun.com/blog/how-good-is-pair-programming-really/)
are also worth reading, they do a great job of explaining the pros and cons of pairing.

## Pairing at Nested

At my [current employer](https://nested.com/careers), we treat pairing as a tool, and we try and make best use of that tool whenever we can. Here is the process we follow:

1. You make sure you're ready and comfortable (food, drink, respond to loved ones, etc.)
2. The driver starts a timer for 25 minutes. We use [be focused](https://xwavesoft.com/be-focused-pro-for-iphone-ipad-mac-os-x.html).
3. The navigator states our goals, and which test we should start with.
4. We follow TDD, writing tests and then code until we meet the stated goal.
5. If we have reached our goal, we pick a new goal and return to step 3.
6. If the timer runs out, we take a 5 minute break, then swap seats and return to step 2.
7. In this break we actually take a break. No email, messenger or phones.
8. After each iteration of both members of the pair having been the driver, we take an extra 5 minute break to repond to messages.

We try and stick to these rules, because it gives us large periods of focus in which we can get stuff done.

This isn't the only way to do things though, perhaps one day we will try things like [ping pong pairing](http://wiki.c2.com/?PairProgrammingPingPongPattern).

## Git and pair programming

Git is a widely used and very popular version control system. It powers sites like Github or self hosted tools like Gitlab.

One of the major benefits of Git is that it keeps and documents a history of your codebase through [commits](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History).

Unfortunately when Git was created, pairing wasn't as popular as it is today, so Git doesn't have a lot of support for pairing.

What it does have is a concept of an author and a committer.
Which at first glance might seem a bit confusing (aren't they the same person?) but
[this answer on stackoverflow](https://stackoverflow.com/questions/18750808/difference-between-author-and-committer-in-git)
explains the difference quite well.

> The author is the person who originally wrote the patch, whereas the committer is the person who last applied the patch. So, if you send in a patch to a project and one of the core members applies the patch, both of you get credit — you as the author and the core member as the committer.

This doesn't quite cover our use case here though, as we have two authors and one committer.
We don't want to lose the history of who worked on the code, as this might be valuable at a later date. So how can we record both authors as we go?

## Introducing [`git-pairing-session`](https://github.com/sadir/git-pairing-session)!

Thankfully recently Github announced support for [multiple coauthors](https://help.github.com/articles/creating-a-commit-with-multiple-authors/)!

This means that while git itself doesn't support more than one author, Github can keep track of this for us through a commit convention.

This is great, and if you use Github desktop software then [it's pretty easy](https://stackoverflow.com/questions/48511133/how-to-create-github-commits-with-multiple-authors) to get started adding coauthors.

But if, like me, you prefer the command line to an external app then it could get pretty tedious typing out those commit messages each time.
Luckily, I've written [some convenience aliases](https://github.com/sadir/git-pairing-session) to help manage a list of coauthors and start and stop pairing sessions!

Check it out, and let me know if you have any feedback.

## Wrap up

Pairing is good.

Pairing with Git is better.

Pairing with Github and [`git-pairing-session`](https://github.com/sadir/git-pairing-session) is the best.
