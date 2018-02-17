---
layout: post
title:  "Pair programming and Github coauthors"
date:   2018-02-16 18:53:44 +0000
categories: pairing git github pair programming pear
author: morgan
---

In this post, I'll explore pair programming, the roles, the tradeoffs, and how Github's coauthors compliment the pairing workflow.

{% include toc %}

## What is Pair Programming?

To quote the [wikipedia page](https://en.wikipedia.org/wiki/Pair_programming):

> Pair programming is an agile software development technique in which two programmers work together at one workstation. One, the driver, writes code while the other, the observer or navigator, reviews each line of code as it is typed in. The two programmers switch roles frequently.

It's about a lot more than just reviewing code though!

## The Navigator Role

In the dynamic duo that is pair programming, the navigator is the 'Q' to the drivers '007'. :cop:

...The 'operator' to the drivers 'Morpheus'... :sunglasses:

...The 'micro' to the drivers 'punisher'... :skull:

...i need to get out more.

Anyway you get the point, the navigator does other things and works as an enabler. The navigator provides:

### Context :earth_africa:

The navigator maps the course, they provide context around the goal of exercise,
why the pair is about to write code, who this change is for and why, how it fits
into the bigger picture. They set direction on what do to next and keep track
of new work that comes up as part of the coding exercise like refactoring, analytics or changes to dependencies.

### Focus :eyes:

The navigator ensures the working environment is set up for proper focus.
They ensure phones are away, that slack is closed.
They maintain the focus on the task at hand, on the goal or the failing test if you're doing TDD.

### A blocker removal service :tractor:

Similar to the principles of servant leadership, the navigator leads the pair by removing blockers.
They get stuck in if the pair one, by asking stimulating open ended questions
like what do we know? Or what can we test to find out more? They collect information
if more is needed or will be soon.

### Coaching :clipboard:

The navigator reviews the work as it happens, challenging early where appropriate.
The discussions this creates helps both parties improve. The navigator teaches
the driver as they go, or conversely learns from the driver if they are less experienced.

## What are the pros and cons of pairing?

Fundamentally, pairing is meant to increase the output of the programmers.  It does this through 
increasing code quality,
reducing the number of bugs,
and reducing interruptions.

It is great for learning, both in terms of knowledge sharing and reducing your [bus factor](https://en.wikipedia.org/wiki/Bus_factor).

Also, most people overlook that effective pairing really brings a bunch of developers together into a cohesive team.

These articles
[1](https://www.agilealliance.org/glossary/pairing/#q=~(filters~(postType~(~'page~'post~'aa_book~'aa_event_session~'aa_experience_report~'aa_glossary~'aa_research_paper~'aa_video)~tags~(~'pair*20programming))~searchTerm~'~sort~false~sortDirection~'asc~page~1))
 [2](https://blog.codinghorror.com/pair-programming-vs-code-reviews/)
 [3](https://raygun.com/blog/how-good-is-pair-programming-really/)
are also worth reading, they do a great job of explaining the pros and cons of pairing.

### Common pitfalls [1](https://www.agilealliance.org/glossary/pairing/#q=~(filters~(postType~(~'page~'post~'aa_book~'aa_event_session~'aa_experience_report~'aa_glossary~'aa_research_paper~'aa_video)~tags~(~'pair*20programming))~searchTerm~'~sort~false~sortDirection~'asc~page~1))

>both programmers must be actively engaging with the task throughout a paired session, otherwise no benefit can be expected

>a simplistic but often raised objection is that pairing "doubles costs"; that is a misconception based on equating programming with typing - however, one should be aware that this is the worst-case outcome of poorly applied pairing

>at least the driver, and possibly both programmers, are expected to keep up a running commentary; pair programming is also "programming out loud" - if the driver is silent, the navigator should intervene

>pair programming cannot be fruitfully forced upon people, especially if relationship issues, including the most mundane (such as personal hygiene), are getting in the way; solve these first!

### Pairing vs Code Reviews [2](https://blog.codinghorror.com/pair-programming-vs-code-reviews/)

> I can't help wondering if pair programming is nothing more than code review on steroids. 

> But code reviews aren't a panacea, either, as Marty Fried pointed out: My experience with code reviews has been a mixed bag. One of the problems seems to be that nobody wants to spend the time to really understand new code that does anything non-trivial, so the feedback is usually very general.

> The advantage of pair programming is its gripping immediacy: it is impossible to ignore the reviewer when he or she is sitting right next to you. Most people will passively opt out if given the choice. With pair programming, that's not possible. 

> Each half of the pair has to understand the code, right then and there, as it's being written. Pairing may be invasive, but it can also force a level of communication that you'd otherwise never achieve.

### When to pair and when not to [3](https://raygun.com/blog/how-good-is-pair-programming-really/)

> Since pair programming will/should increase the concentration for both, it may not always be the case. Many tasks may not be suitable for a pair. Simple tasks for example. What is a simple task depends on the experience. For a difficult task, either a solo senior could solve it or a pair of juniors. Or maybe it’s touching a core feature so having a senior – junior combination might be a good opportunity to strengthen the junior skills and knowledge.

## Pairing at [Nested](https://nested.com)

At my [current employer](https://nested.com/careers), we treat pairing as a tool, and we try and make best use of that tool whenever we can. Here is the process we follow:

1. You make sure you're ready and comfortable (food, drink, respond to loved ones, etc.)
2. The driver starts a timer for 25 minutes. We use [be focused](https://xwavesoft.com/be-focused-pro-for-iphone-ipad-mac-os-x.html).
3. The navigator states our goals, and which test we should start with.
4. We follow TDD, writing tests and then code until we meet the stated goal.
5. If we have reached our goal, we pick a new goal and return to step 3.
6. If the timer runs out, we take a 5 minute break, then swap seats and return to step 2.
7. In this break we actually take a break. No email, messenger or phones.
8. After each iteration of both members of the pair having been the driver, we take an extra 5 minute break to repond to messages.

We try and stick to these rules, because it gives us large periods of focus in which we can get stuff done and helps maximise the benefits we went over earlier.

This isn't the only way to do things though, perhaps one day we will try things like [ping pong pairing](http://wiki.c2.com/?PairProgrammingPingPongPattern).

## Git and pair programming

Git is a widely used and very popular version control system. It powers sites like Github or self hosted tools like Gitlab.

One of the major benefits of Git is that it keeps and documents a history of your codebase through [commits](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History).

[Chris Beams](https://chris.beams.io/posts/git-commit/) does a great job of explaining why good git commits are important.

When pairing, we want to extend the priciples Chris explains in his article. Unfortunately when Git was created, pairing wasn't as popular as it is today, so Git doesn't have a lot of support for pairing.

Git only has concepts of an author and a committer,
which at first glance might seem a bit confusing (aren't they the same person?) but
[this answer on stackoverflow](https://stackoverflow.com/questions/18750808/difference-between-author-and-committer-in-git)
explains the difference quite well.

> The author is the person who originally wrote the patch, whereas the committer is the person who last applied the patch. So, if you send in a patch to a project and one of the core members applies the patch, both of you get credit — you as the author and the core member as the committer.

This doesn't quite cover our use case here though when pairing, as we have two authors and two committers.

We don't want to lose the history of who worked on the code, as this might be valuable at a later date. So how can we record both authors as we go?

## Introducing [`git-pairing-session`](https://github.com/sadir/git-pairing-session)!

Thankfully recently Github announced support for [multiple coauthors](https://help.github.com/articles/creating-a-commit-with-multiple-authors/)!

This means that while git itself doesn't support more than one author, Github can keep track of this for us through a commit convention.

This is great, and if you use Github desktop software then [it's pretty easy](https://stackoverflow.com/questions/48511133/how-to-create-github-commits-with-multiple-authors) to get started adding coauthors.

But if, like me, you prefer the command line to an external app then it could get pretty tedious typing out those commit messages each time.
Luckily, I've written [a little repo](https://github.com/sadir/git-pairing-session) to help manage a list of coauthors and start and stop pairing sessions!

Here's how it works. Assuming you've followed the setup in the repo, you can start recording coauthors by handing in the initials of your colleague.

```
pairing_with ms
```

With every commit made after that, you and your coauthor are automatically recorded in the commits as per the convention.

When you're done, you can just stop the session and stop recording coauthors.

```
no_longer_pairing
```

If you forgot to set up your pairing session, you can just add coauthors to the whole branch instead.

```
paired_with ms
```

Either way, when you're done, your commits in Github will end up looking like this.

![github coauthored commit screenshot](https://i.imgur.com/2Yu1IdT.png)

Much better!

## Wrap up

Pairing is good, when you use it properly. The better you understand it's tradeoffs, the better use you'll make of it as a tool.

There are plenty of ways you can pair, find a way that works for you and your team.

Pairing with Github and [`git-pairing-session`](https://github.com/sadir/git-pairing-session) is the easiest way to follow commit best practices.
