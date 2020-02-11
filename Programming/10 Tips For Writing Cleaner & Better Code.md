# 10 Tips for Writing Cleaner & Better Code

 [Joel Lee](https://www.makeuseof.com/tag/author/joellee/)  July 12, 2016 10 minutes 

 [Without a doubt, programming is tough](https://www.makeuseof.com/tag/learn-programming-without-stress/) . It’s one thing to  [learn languages](https://click.linksynergy.com/deeplink?id=ygZRWO0LhtI&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Funderstandingc%2F)  and study  [algorithms](https://click.linksynergy.com/deeplink?id=ygZRWO0LhtI&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fautomate%2F) , but it’s a whole other beast trying to code a complex working application that doesn’t make you want to claw your eyes out.
 [How to Learn Programming Without All the Stress](https://www.makeuseof.com/tag/learn-programming-without-stress/)   [How to Learn Programming Without All the Stress](https://www.makeuseof.com/tag/learn-programming-without-stress/)  Maybe you’ve decided to pursue programming, whether for a career or just as a hobby. Great! But maybe you’re starting to feel overwhelmed. Not so great. Here’s help to ease your journey.  [Read More](https://www.makeuseof.com/tag/learn-programming-without-stress/) 
In a way, writing clean code is a lot like  [drawing, cooking, or photography](https://www.makeuseof.com/tag/creative-hobbies-will-make-happier-person/)  — it looks easier than it actually is. So why bother? Well, because the benefits are worth it:

* **Problems become easier to solve.** Once you start thinking in clean code, your approach to problem-solving changes. Instead of brute forcing solutions, your algorithms and software design become more elegant and intentional.
* **Less time is wasted on maintenance.** Clean code is easier to read and understand, so you spend less time trying to figure out what certain segments actually do and more time on fixing, revising, extending, etc.
* **Ideas are more clearly communicated.** If you’re working with other programmers, clean code reduces the likelihood of misunderstandings between all of you, which also means fewer bugs in the long run.
Here’s how YOU can start writing clean code.

## 1. Use Descriptive Names

What are variables, classes, and functions? There are many ways to answer that, but when you really think about it, those things are nothing more than the interface between a programmer and the underlying logic of an application.

So when you use unclear and non-descript names for variables, classes, and functions, **you’re essentially obfuscating the application logic from any programmer who reads the code**, including yourself.
“I’m not a great programmer; I’m just a good programmer with great habits.”
— Kent Beck

What does a variable named dxy actually mean? Who knows. You’d probably have to read the entire chunk of code to reverse engineer its meaning. On the other hand, the meaning of a variable like distanceBetweenXY is instantly recognizable.

The same is true for classes and functions. Don’t settle for CalcTan() when you can go for CalculateTangent() or CalcTangentAngle() instead.

## 2. Give Each Class/Function One Purpose

Have you ever peeked inside a function that was hundreds or even thousands of lines long? If you have, then you know how much of a pain it can be to browse, understand, and edit. Comments can help but only to a limited degree.
“Programming is breaking one big impossible task into several small possible tasks.”
— Jazzwant

**Clean code is broken down into atomic chunks.** Every function should aim to do one single thing and every class should aim to represent one particular concept. This is a simplification of course, but when in doubt, simpler is cleaner.

In practice, a complex calculation like GetCreditScore() may need to be broken into several helper functions like GetCreditReports(), ApplyCreditHistoryAge(), and FilterOutstandingMarks().

## 3. Delete Unnecessary Code

This bad habit is one that I still struggle with from time to time. It usually happens like this: I want to fix or optimize a chunk of code so I comment it out and do a rewrite just below it — and even though it works, I keep the old code there just in case.

“Is it possible that software is not like anything else, that it is meant to be discarded: that the whole point is to always see it as a soap bubble?”
— Alan J. Perlis

**Over time, I accumulate a whole lot of commented-out blocks of code that are no longer needed yet clutter up my source files.** 

And the funny thing is that in a lot of cases, the surrounding code has evolved so the commented-out code wouldn’t work even if restored.
The thing is, this practice of commenting out “backup code” was made obsolete by source control. If you aren’t using something like Git or Mercurial, you need to  [start using source control right away](https://www.makeuseof.com/tag/git-version-control-youre-developer/) . Cleaner code awaits you.

 [What Is Git & Why You Should Use Version Control If You’re a Developer](https://www.makeuseof.com/tag/git-version-control-youre-developer/)   [What Is Git & Why You Should Use Version Control If You’re a Developer](https://www.makeuseof.com/tag/git-version-control-youre-developer/)  As web developers, a lot of the time we tend to work on local development sites then just upload everything when we’re done. This is fine when it’s just you and the changes are small,…  [Read More](https://www.makeuseof.com/tag/git-version-control-youre-developer/) 

## 4. Readability > Cleverness

Too many programmers conflate “clean code” with “clever code”, as if compacting ten lines into one is somehow cleaner. Sure, it takes up less space on the screen, but is it actually easier to understand? Sometimes, maybe. But most of the time? No.

“Everyone knows that debugging is twice as hard as writing a program in the first place. So if you’re as clever as you can be when you write it, how will you ever debug it?”
— Brian W. Kernighan

I think programmers love clever code because it feels like a solved puzzle or riddle. They found a special and unique way to implement something — a “shortcut” if you will — and it almost acts as a validation of the programmer’s skills.

But to write clean code, you need to leave your ego at the door.
Always optimize code for the next person who’s going to read it, because in all likelihood that next person is actually going to be YOU and there’s nothing more shameful than being unable to read or understand your own cleverness.

## 5. Keep a Consistent Coding Style

I have  [nothing against good programming tutorials](https://www.makeuseof.com/tag/makes-good-programming-tutorial/) , but one of the downsides is that newbies end up picking up a wide variety of conflicting habits, especially as they pertain to coding style.

 [What Makes a Good Programming Tutorial?](https://www.makeuseof.com/tag/makes-good-programming-tutorial/)   [What Makes a Good Programming Tutorial?](https://www.makeuseof.com/tag/makes-good-programming-tutorial/)  Not all programming tutorials are made equal. Some benefit you and others end up wasting your time. Here’s what to look for in a quality programming tutorial.  [Read More](https://www.makeuseof.com/tag/makes-good-programming-tutorial/) 

I’m not here to declare that one style is any better than another. If you want braces on their own lines, go for it. If you want to precede method calls with spaces, fine. If you prefer tabs to spaces, don’t let me convince you otherwise.

**But whatever you do, stay consistent!**
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
— Tim Peters, *The Zen of Python*

If you’re going to use camelCaseNaming for variables, don’t adulterate it with underscore_naming. If you use GetThisObject() in one place, don’t go with FetchThatObject() somewhere else. And if you mix tabs and spaces, you deserve to have your keyboard taken away.

Decide what you’re going to do from the outset and stick with it through and through. Some languages, like Python and C#, have language-wide style guides that you may want to follow.

## 6. Choose the Right Architecture

There are many different paradigms and architectures that you can use to create your projects. Note how this tip is about selecting the **right** one for your needs, not about selecting the **best** one out there. There is no “best” here.

“Without requirements and design, programming is the art of adding bugs to an empty text file.”
— Louis Srygley

For example, the Model-View-Controller (MVC) pattern is very popular right now in web development because it helps to keep your code organized and designed in a way that minimizes maintenance efforts.

Similarly, the Entity-Component-System (ECS) pattern is very popular right now in game development because it helps modularize game data and logic in a way that makes upkeep easier, all while producing code that’s easier to read.

## 7. Master the Language’s Idioms

One of the difficulties in  [mastering a new programming language](https://www.makeuseof.com/tag/7-useful-tricks-mastering-new-programming-language/)  is learning the nuances that separate it from all other languages. These nuances can be the difference between ugly, convoluted code and beautiful, easy-to-maintain code.

 [7 Useful Tricks for Mastering a New Programming Language](https://www.makeuseof.com/tag/7-useful-tricks-mastering-new-programming-language/)   [7 Useful Tricks for Mastering a New Programming Language](https://www.makeuseof.com/tag/7-useful-tricks-mastering-new-programming-language/)  It’s okay to be overwhelmed when you are learning to code. You’ll probably forget things as quickly as you learn them. These tips can help you to better retain all that new information.  [Read More](https://www.makeuseof.com/tag/7-useful-tricks-mastering-new-programming-language/) 

Consider Python, Java, and JavaScript. They’re all extremely different from each other, to a degree that requires a **different way of thinking depending on which language you choose to use**.

“A language that doesn’t affect the way you think about programming is not worth knowing.”
— Alan J. Perlis

Whereas Python is all about compact code and duck typing, Java is more towards the side of verbosity and explicitness. Every language has idioms (such as list comprehensions in Python) that encourage a certain way of coding. You’d do well to learn them.

There are also “anti-patterns” to worry about, which are essentially sub-optimal design patterns that result in inefficient, unreliable, or otherwise bad code. Study and unlearn all of the common anti-patterns related to your language of choice.

## 8. Study the Code of Masters

If you want to write clean code, the best thing you can do is to see what clean code looks like and try to understand why it is the way it is — and there’s no better way to do this than by studying the source files of industry masters.

Obviously, you can’t just pop into Microsoft’s headquarters and peek at their projects, but you can always  [browse well-known open source projects](https://www.makeuseof.com/tag/how-to-view-edit-the-source-code-of-an-open-source-app/) . **Don’t know where to start? Try the   .** [showcased projects on Github](https://github.com/explore) 

 [How To View & Edit The Source Code Of An Open-Source App](https://www.makeuseof.com/tag/how-to-view-edit-the-source-code-of-an-open-source-app/)   [How To View & Edit The Source Code Of An Open-Source App](https://www.makeuseof.com/tag/how-to-view-edit-the-source-code-of-an-open-source-app/)  While going open source might be a good choice, you’ll also need to invest in the right community. GitHub is one of the best places to do this, not only because of the sheer amount…  [Read More](https://www.makeuseof.com/tag/how-to-view-edit-the-source-code-of-an-open-source-app/) 

“Any fool can write code that a computer can understand. Good programmers write code that humans can understand.”
— Martin Fowler, *Refactoring: Improving the Design of Existing Code*

After all, that’s one of the reasons  [why open source projects exist](https://www.makeuseof.com/tag/people-contribute-open-source-projects/) : so others can learn from them. And if you decide to contribute to such a project,  [it can accelerate the learning process](https://www.makeuseof.com/tag/5-project-ideas-help-learn-programming-faster/) .

 [Why Do People Contribute to Open Source Projects?](https://www.makeuseof.com/tag/people-contribute-open-source-projects/)   [Why Do People Contribute to Open Source Projects?](https://www.makeuseof.com/tag/people-contribute-open-source-projects/)  Open source development is the future of software. It’s great for users because open source software is usually available gratis and often safer to use. But what compels developers to contribute code for free?  [Read More](https://www.makeuseof.com/tag/people-contribute-open-source-projects/) 

Personally, the very first time I saw truly clean code is when I stumbled across a certain hobbyist’s open source Python project. The code was so overwhelming elegant that I nearly quit programming, but it ended up teaching me a lot.

## 9. Write Good Comments

“Write good comments” is the oldest piece of advice in the world of programming. In fact, as soon as newbies are introduced to comments, they’re pretty much encouraged to comment as often as they can.
But it almost feels like we’ve swung too far in the opposite direction. Newbies, in particular, tend to over-comment – describing things that don’t need to be described and missing the point of what a “good comment” actually is.

“Always code as if the guy who ends up maintaining your code will be a violent psychopath who knows where you live.”
— John Woods

**Here’s a good rule of thumb: comments exist to explain WHY a piece of code exists rather than WHAT the code actually does.** 

If the code is written cleanly enough, it should be self-explanatory as to what it does — the comment should shed light on the intention behind why it was written.

Comments can be good for warnings (i.e. “removing this will break A, B, and C”) but for the most part should uncover things that can’t be immediately gleaned from the code (i.e. “use this parameter because X, Y, and Z”).

## 10. Refactor, Refactor, Refactor

Just as editing is part of the writing process, refactoring is part of the coding process. An aversion to refactoring is the quickest way to end up with unmaintainable code, so in many ways this is actually the most important tip to consider.

**In short, refactoring is just a fancy term for cleaning up the code without impacting its actual behavior.**

“Whenever I have to think to understand what the code is doing, I ask myself if I can refactor the code to make that understanding more immediately apparent.”
— Martin Fowler, *Refactoring: Improving the Design of Existing Code*

One bit of wisdom that has stuck with me is the saying, “Don’t comment bad code. Rewrite it.” As Fowler explains in the quote above, if code ever feels confusing enough that you need to comment it, maybe you actually need to refactor it.

Furthermore, as you edit bits of code here and there throughout your project, **always leave the code in a better state than when you first found it**.

It may seem like a nuisance in the moment, but it will pay off in the long run ( [and can even stave off mental burnout](https://www.makeuseof.com/tag/programming-burnout-regain-lost-motivation/) ).
 [Programming Burnout: How to Regain Your Lost Motivation](https://www.makeuseof.com/tag/programming-burnout-regain-lost-motivation/)   [Programming Burnout: How to Regain Your Lost Motivation](https://www.makeuseof.com/tag/programming-burnout-regain-lost-motivation/)  Writing all those lines of code can be draining physically and emotionally. All you need to get back up is the awareness that motivation can be regained.  [Read More](https://www.makeuseof.com/tag/programming-burnout-regain-lost-motivation/)

## There’s Always Something New to Learn

A programmer who’s learning how to write clean code is akin to a novelist learning how to write clean prose: there isn’t a right way to do it per se, but there are plenty of wrong ways to do it, and it’ll take years to master.
Some people don’t have what it takes and  [eventually end up quitting programming for good](https://www.makeuseof.com/tag/6-signs-meant-programmer/)  — and that’s fine because there are plenty of  [other techy jobs that don’t involve coding](https://www.makeuseof.com/tag/coding-isnt-everyone-7-tech-jobs-can-get-without/) .

 [6 Signs That You Are Not Meant to Be a Programmer](https://www.makeuseof.com/tag/6-signs-meant-programmer/)   [6 Signs That You Are Not Meant to Be a Programmer](https://www.makeuseof.com/tag/6-signs-meant-programmer/)  Not everyone is cut out to be a programmer. If you aren’t completely sure that you’re meant to be a programmer, here are some signs that may point you in the right direction.  [Read More](https://www.makeuseof.com/tag/6-signs-meant-programmer/) 

But for everyone else, clean code is something that’s absolutely worth striving towards, even if it takes the rest of your life to get there.
**How important is clean code to you? What rules do you follow to keep your code clean and organized? Got any other bits of wisdom to share? Let us know in the comments below!**
