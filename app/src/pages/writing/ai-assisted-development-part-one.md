---
title: "Hello World"
pubDate: 2026-07-10
description: "How I currently use AI to be a better programmer."
author: "Chisomo Chiweza"
image:
url: ""
alt: ""
tags: ["ai, software-engineering"]
---

# AI Assisted Software Development Part 1

Published on: 2026-05-01

When I had graduated from university and decided to pursue programming as a career - I thought deeply about the type of programmer I wanted to be.

I might have refined and rephrased what that’s meant over the years but my ‘manifesto’ so to speak has always been something along these 3 axioms:

> 1.  I was going to be a problem solver first.
> 2.  I was going to invest in the craft of writing good code in order to solve problems using software as effectively as possible.
> 3.  Every tool I conscientiously adopt would be in service of these goals.

If it is not already evident - **I love programming**.

I enjoy reading it, writing it and learning more stuff about it. For me - there is as much satisfaction derived from the process of writing software as there is from creating the final product because much of programming is an exercise in problem solving.

It comes as no surprise then; that at first, it was a little difficult for me to find a meaningful use-case to incorporate AI systems into my software engineering toolkit.

[Many of the popularized reasons for AI-assisted development solved problems I did not think I had](https://newsletter.pragmaticengineer.com/p/when-ai-writes-almost-all-code-what). I don't mind putting in the time to learn how something works. I don't mind writing lots of code. I don't mind debugging programs. I don't mind poring over old codebases and coming up with creative strategies to solve problems amidst existing technical constraints.

Not to mention that I already felt like many of the purported problems like coding throughput could be solved by either having a team of strong engineers with excellent synergy and/or just well optimized engineering processes.

Nevertheless, as I gained experience writing _professional_ software - the reality of trying to write good code whilst trying to meet stringent deadlines meant that I began to _at least_ appreciate some of the sentiment behind why people still pined after some sort of silver bullet to quickly solve their problem [despite the pervasive knowledge that such a solution technically doesn't exist](https://en.wikipedia.org/wiki/No_Silver_Bullet).

As you'll learn reading this article; AI does not magically remove many of the root problems that make writing good software that is shipped fast difficult.

> Software engineers will have to grapple with the fact that tools are just that - tools. We will always need to make and be accountable for the inevitable trade-offs brought about by the outcomes of our tools. We cannot run away from this and must embrace it.

**But it does help to make the process a little easier**.

In fact, to illustrate my point, allow me to recount my earliest memory utilizing an AI tool.

It was evening and I was trying to figure out how to use a publicly available API whose behavior conflicted with the documentation available (probably due to it not being updated). I'd previously spent time navigating support chat forums and even attempted to reverse-engineer the payload by modifying JSON properties and observing the output until I got what I wanted. It was frustrating work and to make matters worse - I needed an endpoint to work for a project that was due soon.

I recall at some point, in desperation; I asked a relative if he had some knowledge of how to solve the problem I was facing. I remember him going to my browser, signing me up for [Gemini](https://gemini.google.com/app) and prompting the LLM with my specific problem. I had been skeptical; I didn't think there was anything the LLM could tell me that would solve my problem that the docs couldn't and sure enough it provided me with a bunch of responses that had little to do with my problem. Or so I thought.

Sure, it didn't solve my immediate problem; but one of the responses gave me an idea about **_what could_** solve my problem and when I tested the solution later - surprisingly it worked. This persistent trend would inform my use of AI later on as I explored it's abilities to either streamline or quicken several processes within my engineering workflow.

For the rest of the article, I'll talk about 3 ways utilizing AI tools have been useful to me in my efforts to be a better programmer - in **research**, **design** and **refactoring**. My current tool of choice is [Google’s Gemini](https://gemini.google.com/app) but you could apply this to almost any other popular AI tool.

## Research

Programmers are lifelong learners.

When investigating a bug, you might typically have to spend time learning how a codebase works. Likewise when implementing a software component, you might have a tab referencing a library you're utilizing in your code. And if you're designing a large software system, you might have various papers, documentation and videos to help inform you on what is the most effective way to solve the problem you are attempting to solve.

When I was first starting out professionally, one of my biggest bottlenecks definitely had to be the pace at which I could take in all the information I felt I needed to know. Don’t get me wrong - I pick most things up, particularly things I am interested in - pretty well. Nevertheless, for someone starting out in software engineering, especially with time constraints and the current age of information overload; it's not strange to feel a little overwhelmed sometimes.

> Optimizing this bottleneck traditionally meant figuring out how best you learn, having a good retrieval and archiving system, developing good intuition over what was useful information and importantly, developing good learning habits (like setting aside time to weekly to actually learn).

With AI tooling though, there was a way to make this process a little bit faster.

You see, one thing I love about these new types of systems **definitely has to do with the novel way with which one can now interact with vast amounts of information**. In my opinion, **AI has enabled us to get the closest we've ever been to a truly accessible semantic search experience**. Because of this, I feel l the friction between my initial train of thought and the information I would like to find is heavily reduced.

To illustrate, Let's say I was curious about the justification behind a design decision - let's take why [Golang](https://go.dev/) has no [try-catch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch) for example.

Previously, I might search up how Go handles try-catch in the language, discover forums, blogs and maybe articles talking about it and if I hadn't inferred over why Go does not implement try-catch by then - would have probably hopefully landed on some official statement as to why it is designed that way.

On the other hand, compare that with a quick prompt to an LLM instead:

![](https://cdn.hashnode.com/uploads/covers/693a6b134ef16aeef0cdbf34/ba8056d9-a02e-4a02-94b7-14cfd4901769.png align="center")

Not only is the information returned didactic in nature, but the way information typically scattered across the internet is also condensed here is quite impressive.

> This is possible because today's AI systems typically involve interaction with either a [Large Language Model](https://en.wikipedia.org/wiki/Large_language_model) or collection of Large Language Models. These type of models are a type of [computational model](https://www.ibm.com/think/topics/machine-learning) that is designed to predict sequences in natural language using [machine learning techniques](https://www.ibm.com/think/topics/machine-learning) (which is a combination of mathematics, statistical modelling and computation), . It might sound like a humble idea but scaled to the level that the companies behind popular AI systems build these systems at, means you can get legible sounding sentences with information that is accurate enough for translation systems, conversational agents and even code generation.

Add some inventive product development into the mix and you get interfaces like the one above with different components of the entire AI system working together to return information that is not only intuitive to consume but also ready to immediately test and manipulate if you wish.

**Yeah I think Large Language models are a bit a neat.**

The biggest caveat however is that **they're not inherently designed to verify information - they're designed to predict the next word**. As a result whilst, the output simulating a response from an expert might be somewhat sufficient for the task at hand, it is not an actual response from an expert - but rather an _approximation_ of an expert's response. Nothing is stopping the LLM from injecting a wrong or non-existent reference in it's response in it's efforts to return the best approximation.

But honestly, as an engineer - I'm lowkey like meh.

Sure, hallucinations exist but if I can figure my way around a blog post from 2007 detailing how to implement a feature using the version of a library that is no longer in support, I can figure my way around a system that generates correct answers 90% of the time.

I might have a few suggestions on how current AI systems could be integrated into digital tooling that effectively streamlines pedagogy ([a great place to start is with this fantastic article!](https://hazelweakly.me/blog/stop-building-ai-tools-backwards/)). I'd also probably re-architect the system if possible to utilize the models less as as a final source of information and more as an interactive doorway to other sources of information. And maybe I'd anthropomorphize the models less. Not to mention all of the concerns surrounding how ethically their training data is sourced and the energy costs of either training or running them.

Otherwise?

With today's version of Gemini - I absolutely love how I can do deep dives on technologies I am interested in without sacrificing too much time spent shipping stuff. If I need to learn something - I no longer need to sacrifice weekends, I just need pen, paper, Gemini and some hours to come up with a plan of attack. If someone says, hey do you know this? Instead of dismissing something because of the potential steepness of the learning curve, I can prompt an LLM to quickly get a general picture of said concept.

I once spent a few hours learning about observability enough to proceed to integrate OpenTelemetry instrumentation in an existing API (on test!) before proceeding to observe how the ensuing data is collected and visualized by installing Grafana, Prometheus and Loki on a Linux server. I was completely new to almost all of the technologies and whilst I am somewhat confident in my ability to 'figure things out' - I still feel a bit empowered that I have yet another tool to help me learn all I want to learn.

I can finally be distracted by rabbit holes _and_ still be productive lol.

Jokes aside - if you're also starting out professionally, particularly in Malawi, you can become a better programmer quickly by utilizing LLM's to help you learn pretty much anything you want to.

**It is a wonderful time to be a nerd.**

![](https://cdn.hashnode.com/uploads/covers/693a6b134ef16aeef0cdbf34/033ebe80-bdbf-4299-a14a-6054d7c163a7.png align="center")

## Design

Here are a few ways software engineers either learn or build design intuition.

> Note: When I mean design intuition - I'm not talking about frontend things like visual hierarchy, composition and color. I'm talking about the design of the structure of code and software as a whole. [Linus Torvalds might call it taste](https://youtu.be/78Y17hAo96I), I call it design intuition.

1.  By listening in on and participating in design workshops when architecting a new project.
2.  By looking at good code and software written and built by "senior" engineers.
3.  By being guided through code reviews on good practices and trade-offs to consider before merging new code.
4.  By being forged in the flames of that one edge-case that fails in production or by having to maintain _that_ legacy application.

Out of curiosity, as a Malawian software developer - **what was the primary way you began to build design intuition**? If you're like me - well ... let's just say it wasn't always fun.

I enjoy design.

Done right, I believe it can be a powerful tool that aids in the construction of robust software. Nevertheless, because of how inherently abstract the thinking is - it's not always intuitive and sometimes it can be downright hard to seamlessly adopt or teach the skill across teams.

One way though, at least the one that has helped me so far, is by utilizing the method craftsmen of different disciplines have used for millennia on the path to mastery - intentional **iteration**.

There is this quote I think about that is attributed to [Andrew Hunt's The Pragmatic Programmer](https://www.amazon.com/Pragmatic-Programmer-Journeyman-Master/dp/020161622X):

> “Rather than construction, software is more like gardening—it is more organic than concrete. You plant many things in a garden according to an initial plan and conditions. Some thrive, others are destined to end up as compost.”

Design intuition for me is best developed through **frequent experimentation** and by **testing my initial assumptions**. When I get a problem, I like to brainstorm ideas on paper before taking them through a process of questioning and refinement - often as I am simultaneously implementing the solution as well. My background is [computer science](https://en.wikipedia.org/wiki/Computer_science) and whilst we have an entire field [attempting to systemize this process using mathematics](https://en.wikipedia.org/wiki/Formal_methods) (For the sake of the length of this article, I will only [urge you to check out this guy if interested in the idea](https://youtu.be/rkZzg7Vowao)), practically - I mostly let my current knowledge and intuition guide the process.

Whilst I personally find this process intellectually rewarding - finding ways to effectively do this whilst shipping fast was a bit tricky difficult for me. Before, I would sometimes be tempted to just limit how far I would iterate on a design or even cut out the process altogether if the solution was needed immediately. Not to mention the difficulty that comes from trying to strike a balance between pursuing an elusive perfection and shipping something that 'works'. What counts as 'good enough' in software engineering?

Still - **design is important**.

As I grew from being an intern to a developer taking ownership for projects; **pressure or no pressure during development, it was my responsibility to explain why certain architectural decisions which led to negative outcomes were made**. Even if your environment does not value the time it takes to factor in design, the costs associated with implementing bad design will always heavily outweigh them.

_How does an early-stage developer with limited time, resources and influence then streamline this important process?_

Enter AI.

Even though I previously touted Large Language Models as useful for querying information, one thing I've found them immensely helpful for is ironically what they were originally created for - **conversation**. Today's LLM's, as previously said, are excellent at predicting natural conversation and so one of the ways I used these LLM-based AI systems was by using it as a fast way to question my assumptions and test my ideas long before I implement my code.

A lot of my saved chats with Gemini are essentially this - **the back and forth relay of ideas as I tried to refine the design of a system I was building**. I start with an initial idea, prompt it for it's thoughts on the potential trade-offs as well as information about different components before reviewing the output to see what generated ideas it will bring.

As you can imagine, it's also a bit fun. Through it, I've discovered glaring flaws in my initial thought process, learnt new things and learnt to appreciate perspectives I otherwise wouldn't have. Every response from the AI is an opportunity for me to pause, reflect and question it back in turn until I am satisfied I understood the problem well and the final design is sufficient.

Still - inevitable caveats.

Sometimes Gemini would hit the limits of the data it was trained on (or face an overloaded context window) and would suggest ideas that when I test them would not solve my problem or be even more convoluted than my assumptions. [There's also the problem of AI of sometimes trying too hard to please the prompter](https://www.law.georgetown.edu/tech-institute/research-insights/insights/tech-brief-ai-sycophancy-openai-2/) which you can guess is not helpful if you're trying to clinically interrogate a proposed design. And **whilst I got a bit of a high engaging in this back and forth with this tool designed to simulate human conversation, it was nothing compared to the palpable exchange of ideas when I later ran a design with a fellow programmer and we subsequently had a back and forth**.

This is why I emphasize that **the value gained from using AI here was in quickening the questioning process rather in somehow magically leading you to a perfect design**. I still think having dedicated design workshops, code reviews and pair programming sessions is a better builder of this _design muscle_ than querying the AI system alone.

Nevertheless, not all developer environments (especially in Malawi) are resourced enough to have senior programmers who are free enough to transmit knowledge to teams. In these cases, it can still be helpful to still utilize the AI system in this fashion to at least screen out the most flawed of ideas or to do basic research about systems - even if you still need further guidance past the AI system to cement your burgeoning _design intuition_.

Moreover, even if you do have access to these senior programmers - I still think it's nice, particularly for junior programmers, to at least get into the practice of reasoning first about their proposed solution _on their own_ before presenting a problem to a senior programmer. If this was difficult for you before, utilize the AI system to brainstorm ideas and research the implications of your design. Your subsequent conversations with your senior will be better informed and richer as a result.

## Refactoring

Here is one thing I do not understand about the [vibe-coding crowd](https://en.wikipedia.org/wiki/Vibe_coding).

> If you have a tool that can generate legible code more than half the time, why don't you use it to make your existing code better instead of fenagling your way to a brand new codebase with AI?

**I'm talking about refactoring**.

Remember that quote by Andrew Hunt about software codebases being a garden? Well think of refactoring as something like performing maintenance tasks like weeding or pruning. **In software, there is always something that can be fixed**. You might notice several functions that share behavior and clean it up by extracting that into a single abstraction those functions and future functions might use. You might decide a chunk of code is not performant and rewrite it. You might remove lines somewhere because you discovered logic that contributed to a memory leak somewhere.

It sounds like common sense but the truth is that in practice; it's not always feasible. Apart from taking time away from building in time-constrained environments; it is difficult to enforce initiatives like the [boy scout rule](https://dev.to/anton9/boy-scout-rule-and-its-limitations-5404) because there are a matter of personal principle rather than easily recognizable financial benefit. Not to mention, different members of a team can have different ideas over what counts as an 'important' refactor.

Nevertheless, like design; **whilst people may not immediately see the benefit of refactoring a codebase now - they will definitely feel the impact of having to wade through a large gnarly codebase later when users inevitable change and request new features**.

Still - how can one mindfully refactor without ending up like this guy?

![](https://cdn.hashnode.com/uploads/covers/693a6b134ef16aeef0cdbf34/207864e8-c21d-4e71-bb89-30e4085b6f5f.png align="center")

Well, first - **by gaining** **experience** but optionally - copy a chunk of the code you want to refactor, remove all information that could pose as a security risk, paste in a prompt box to an LLM and tell it to do whatever you wanted it to do. Had an idea to shorten the function? Articulate your strategy to the LLM and review the generated output. Wanted to make it faster? Prompt the LLM to generate ways the function could be re-designed to be performant and pick one. Not only does it save time, but it leaves the codebase cleaner, more robust and easier to manage for the next person.

**Refactoring is a lot of work and a lot of non-functional code**.

Sometimes when implementing a system, I could have ideas to extract out some functionality or realize there is a way to simplify logic across different parts of the codebase. Whilst I am more than motivated to do this by hand, sometimes AI systems can help with the grunt work of implementing this in a fraction of the time so I can focus in either cleaning up other parts or working on functionality.

As always, let's talk about the caveats.

From experience, LLMs work best with smaller chunks of code at a time and some review is still needed as they can sometimes generate output in an outdated style or with older language features unless explicitly directed not to. I also just find it easier to articulate to LLMs exactly what I need for a smaller scope like a function or class than an entire feature. I also have not had as much success with language rewrites as these still require some form of architectural consideration before outsourcing work to an LLM. Of all the features I've mentioned so far - generated code from an LLM is not the most seamless for me but it's an okay feature to take advantage of.

All I'm saying is - **if there are tools that lower the barriers to producing code now so why not use those tools to generate better code**?

Think about it.

**And that's it for this article.**

There are other ways I'd like to experiment with AI systems in my engineering workflow. For one, I'm looking to see how well it can assist in the generation of tests so that I can better adopt a test driven approach to my development process.

Until next time,

**Your favorite Malawian programmer.**
