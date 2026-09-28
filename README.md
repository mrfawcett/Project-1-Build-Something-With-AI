# Project 1: Build Something With AI

**AP Computer Science A | Quarter 1 | 20 points | Individual**

*Every date for this project lives on Canvas: when the work day is, when the code is
due, and when you present. Check there.*

## The short version

Build a Java program that does something you actually want to exist. You pick what it is.
Use AI as a pair programmer the whole way: Claude, ChatGPT, Copilot, whatever you like.

Then present it to the class. You will run it, walk us through your own code on the
screen, and take questions about it.

That second part is the whole point. The program is how you get there. Half your grade is
whether you can explain what you built.

## Why it works this way

AI writes Java faster than any of us. Pretending otherwise would be silly, and banning it
would just teach you to hide it. What AI cannot do is stand in front of the room and
explain why line 34 uses a while loop instead of a for loop.

So use every tool you have. Then own every line that ends up in your file. If AI hands you
something you do not understand, your job is not to paste it. Ask the AI to explain it until
you do, or throw it out and write something simpler that you can defend.

## What you are allowed to build

Your program must be:

* **A console program.** Text in, text out. No windows, no graphics. We do not learn GUI
  programming until late October.
* **Interactive.** It asks the user something and responds. A program that prints a report
  and exits does not give us enough to talk about.
* **Built around a thing that has state.** At least one class that represents something
  (a player, a recipe, a route, a shift, a deck) with instance variables that change while
  the program runs.
* **Between about 120 and 250 lines**, spread across two to four classes.
* **Able to survive one bad input** without crashing. If it asks for a number and gets
  "banana", it should say something useful.

Your program must **not** be:

* A tutorial you followed. If searching a phrase from your program finds the source, it is
  not yours.
* A single calculator with no stored state. Converting units and printing the answer is a
  method, not a project.
* Pure chance with no decisions. Rolling dice and reporting the result is not enough.
* Dependent on files or the internet. No reading from disk, no downloading anything, no
  libraries outside `java.util`.
* Built on arrays or ArrayLists. See the language rule below.

## The language rule: no arrays, no ArrayLists

**You may use only what we have covered in class: classes, constructors, methods,
conditionals, loops, Strings, Scanner and the Math class. No arrays. No ArrayLists. No
exceptions.**

Here is the trap. AI does not know what we have covered, and it will reach for an
`ArrayList` within about nine seconds of you asking it for anything. When that happens,
tell it exactly this:

```
"Rewrite this using only classes, methods, loops, conditionals
 and Strings. No arrays or ArrayLists."
```

It will comply. Rewriting that code is not busywork, it is the assignment. Working out how
to hold your data without a list is the most interesting problem you will solve on this
project, and it is the part you will be proudest of explaining.

Code in your file that you cannot account for scores zero on that line. "The AI wrote that
part" is not an answer.

## How to hold your data without a list

This is the question everyone hits on day two. There are four good answers and you will
probably use more than one.

* **Separate instance variables.** If you have exactly six shifts, six variables is not
  elegant, but it is honest, it works, and you can explain every line of it.
* **One String holding everything**, with a separator you pick. `"Mon-8:00;Tue-9:30;Wed-4:15"`
  and then `indexOf` and `substring` to pull pieces back out. This is exactly what we did in
  2.3, and it is the most powerful option on this list.
* **An object that holds another object.** A `Schedule` that has a `Day`. A `Locker` that
  has a `Book`. Composition gives you structure without a list.
* **Do not store it at all.** Read one value, use it, move to the next. A running total, a
  current best, a count. If you never need to look back, you never need to keep it.

If you get truly stuck on storage, come find me. This constraint is deliberate, and working
inside it is worth more than working around it.

## Three rules that make this yours

These exist because a generic assignment produces generic AI output. Each of these makes
your project impossible to generate from this document alone.

### 1. Your program must use real data from your own life

Your program has to contain at least **six specific, real data points that I cannot look up
and AI cannot invent.** Your actual class schedule with room numbers. Your team's real
scores from this season. The exact quantities in a recipe your family makes. The real titles
and page counts of books on your shelf. Your actual practice times.

Not "Player 1, Player 2." Not `Math.random()` standing in for data. Real things, with real
values, that you can vouch for.

You will list all six in `REFLECTION.md` and say where each came from. During your
presentation I will pick one and ask you about it.

### 2. One method must be written with no AI at all

Pick a method. Write it completely yourself, no AI, no autocomplete suggestions accepted.
Put this comment directly above it:

```java
// NO AI: written entirely by me
```

It does not need to be the hardest method. It does need to be real: more than three lines,
with at least one conditional or loop in it. During your presentation I will ask why you
picked that one and what part of it gave you trouble.

### 3. Your commit history must show real work

Push to this repo as you go. I require **at least five commits across at least three
different days**, with messages that say what actually changed ("added the scoring method,"
not "update").

One enormous commit the night before the deadline tells me the whole program appeared at
once, and I will aim my questions at the parts you understand least.

## What to submit

Everything lives in this repo, pushed by the deadline on Canvas:

* Your `.java` files in `src/main/java/`
* `REFLECTION.md`, filled in (the template is already in this repo)
* Your commit history, which you build by working normally

## The presentation

About five minutes in front of the class, with your code on the screen. You drive. The
shape of it:

* Run it and show us what it does (about 1 minute)
* Walk us through one class: what it holds, what it does, and how you solved the storage
  problem without a list (about 1 minute)
* Walk us through the method you are proudest of, line by line (about 1 minute)
* Take questions from me and from the class (about 2 minutes)

You are not being graded on polish. No slides, no script, no rehearsed speech. Show us the
code and talk about it the way you would explain it to a friend sitting next to you.

Questions I will ask, so nothing is a surprise:

```
"What does this variable hold, and why is it private?"
"Why a while loop here instead of a for loop?"
"What happens if the user types a letter instead of a number?"
"Walk us through this method with the input 7."
"How are you storing that without a list?"
"What is this constructor doing, and what breaks if I delete it?"
"Where did this number come from?"
"Why did you pick this one as your no-AI method?"
"Where would you add a second kind of item? What would change?"
```

"I do not know, but here is how I would find out" is a real answer and earns partial credit.
Bluffing does not.

Watching everyone else present is part of the assignment. You will pick up more from five
classmates solving the storage problem five different ways than from anything I could put
on a slide.

## Grading, 20 points

| Category | Points | What earns full marks |
|---|---|---|
| **Presentation** | **12** | You explain every line asked about, in your own words. You can trace your own code out loud. You can account for your storage choice, your no-AI method and your data. |
| It works | 3 | Compiles, runs, does what `REFLECTION.md` says, survives one bad input. |
| Boundaries | 2 | Console, interactive, stateful class, 120 to 250 lines, no arrays or ArrayLists, nothing from the "must not" list. |
| Commit history | 1 | Five or more commits across three or more days, with messages that say what changed. |
| `REFLECTION.md` | 2 | All questions answered, six real data points listed with sources. |

Ambition is not graded. A small program you understand completely beats a large one you do
not. Every year somebody submits something enormous and loses most of the presentation
points, and it is painful for both of us.

## Stuck on what to build?

These are not project ideas. They are places to look for one. Every one of them forces you
into real data, which is the point.

* **Your actual week.** Something that takes your real schedule and answers a question you
  actually have. When am I free for 90 minutes? How many hours until my next free day?
* **A team, club or group you are in.** Real rosters, real scores, real attendance, real
  parts in the music.
* **A collection you own.** Books, cards, games, shoes, recipes, playlists. Real titles,
  real numbers, sorted and searched the way you would want.
* **Something you keep doing by hand.** A calculation you redo every week, a decision you
  make the same way every time.
* **Something at your job or in your house.** Chores and who owes what, a shift schedule,
  a shopping run with real prices from a real store.

Come talk to me if nothing here appeals. Having an idea you care about makes this project
dramatically better, and I would rather spend two minutes helping you find one than read
another generic grade calculator.

## Running your code

```
mvn compile -q          # compile everything
mvn exec:java -Dexec.mainClass=Main    # or just run Main from your IDE
```

Your IDE's green Run button is fine too. The pom is here so the project compiles the same
way on every machine.
