# Truth Tree

Truth Tree is an experiment where the "truth" (facts) are ascertained by appending knowledge, built additively and non-destructively. New pieces of information, connected to the graph via LLM, are added to the existing graph, and the probability of parent nodes being true goes up or down depending on conflicting children (evidence / information).

## Raw Notes

How do we actually update probabilities

- Maybe we can rate the "credibility" of a source, or use some sort of "I believe this" at the root voting mechanism with allocated money / tokens, etc.
- Similar to Kalshi / Polymarket, you vote with "money" aka allocated token set

How do we segment knowledge and prevent cycles in this graph

- Probably should divide things into supporting claims, neutral claims, and contrasting claims
- Basically have to figure out if things are parallel to the existing node (or same generation), parent (or one generation above), or child (or one generation down)
- Feels like you have to at least, in a large graph, know that the closer a node is to the "actual location" of any given node, the higher the value returned by the retrieval function, otherwise we could totally miss the node(s) that we need to attach to.

How do you actually extract a single node of information given a bunch of text / facts / inputs

- A single, standalone claim (give examples)
- What does it mean for something to be a single claim? There's going to be instances where single nodes have to be broken down / refederated into smaller nodes because the original claim was actually not atomic
- We basically new a ruleset (hard rules to allow this sort of split)

What is a good case study for the first thing to investigate

- Should direct agent to investigate a single topic — e.g. chicken domestication. Then produce a page with a list of notes, facts broken down, and then proposed hierarchy + how they fit in to the global scheme.

Architecture + product + approach

- Basically can be multiple layers of flow graphs. This would be the "editor" or "injector" mode. And then there's view mode, which is a completely different webpage.
- Research mode:
- Editor mode:
- View mode:

## Voice Transcript

Okay, so I'm thinking that for the Truth Tree project, there's going to be three different screens:

1. Research screen

2. Editor screen

3. View screen (which might be the same thing for now in the decimals of Newsroom)

The point is that research and editing are going to be basically generating as well as editing facts and their relationships to each other, and view is going to be just viewing the graph and sort of how we're determining truth or whatever.

And so this is super interesting. I would say that in general from an architectural perspective, what we're going to want is for the research as well as editing page to both be basically a box where you can type in what you want to research. It's good to send it off to an LLM degree, to go off and do some research. Get, find some webpages, gather some facts, and then break those webpages and information therein into actual concrete facts which roll up to some series of claims.

Basically, these facts can be related to each other or be independent. And if they're related to each other, they're sort of related through what I guess you could call conditional logic. So at, so there's no way to actually delete any information once it gets appended to the graph. It's append only.

And so what you want is for all of these things to basically be the concept of enriching knowledge through debate. Like even if people say contrasting things, they should all be on the graph of credence for credence against. You should be able to kind of verify the truth by gathering as much evidence as possible. Right? So essentially you're not trying to declare the truth; you're trying to declare a list of all possible positions and find reasons to support those.

From that perspective, the goal of all of this is basically to generate these claims and facts and sort of link them together. We're going to need ways to do that.

Like, so for instance, it should be: you have a box, you type in research, come up with a bunch of pages you can edit or delete certain pages or add new pages to interpret information from each of these pages. That's like one section.

And then from each of these pages or maybe the boxes section and then the pages are second section. The third section is the claims extracted from those pages. You kind of want to make sure that those claims are actually represented correctly or derived from the actual pages. And then that's step three.

And then, like, section four is how these claims can be related to each other, or if they're leaf nodes or if they're independent. Drawing relationships between them. And then, obviously, drawing relationships between these claims and the rest of the graph that already exists. Because you kind of want to tie it into a centralized knowledge base, right?

And I think a lot of this is going to be fine-tuning of the prompts to determine what is a claim, "quote unquote". And of course these claims can be arbitrary, there's like no such thing as an atomic level here. So you have arbitrary level of resolution. It's possible that your claim actually is in a composite claim, right? You have atomic claims or like atomic nodes as well as composite nodes and composite nodes are just comprised of multiple subclaims or whatever, right?

So you can kind of start to see where there's a graph here. Of how you can take an arbitrary piece of knowledge and break it down successfully into individual factual components of different levels of resolution, which are sort of like the hierarchy would be that the most composite or most abstract is at the high level and then the more narrow and sort of you could obviously continuously break those down to some true prior of some kind, right? And maybe you never know what is a true prior vs just they. But you can determine that sort of opportunistically.

And so that's basically the research and edit mode. I think maybe after you get the facts, we can preliminarily try to add them to the graph and then take people to edit mode where they can hear stuff a little bit more aggressively. So maybe we should keep them set because it seems like a lot could be wrong.

So basically, steps one, two, three are going to be research, and then edit mode would be rearranging things or breaking things down a bit more, like actually working on editing the graph itself as opposed to just reporting what research is. Then you have view mode, obviously, which is going to be you just have a massive graph, let's just render that, display that, and sort of understand how things all work together. This feels like a fractal problem, right? Also just physically graphical display problem for those actually super interesting. I'm not quite sure that specific UI here should be

There are a few other interesting ideas here:

• Categorizing relationships between different claims for the importance of claims based on how many things they are trying to support and the level of distraction that supports.
• If you enumerate this fully for any given topic, there's some set of priors that we can kind of figure out that are critical towards supporting something or determining the result or the "truth" in the main topic.
• I also think that there's some really interesting ideas around this being kind of like an "Asian truth" - so it's like, you can't know for certain if something's absolutely true or not, and everything rests on certain priors. All these notes just have to have some sort of way to resolve their probability. Like, either if this could be a voting mechanism - so it's like, if this note has 7 uploads and 3 downloads, and there's some related function that determines the crowd-sourced likelihood of this being true. This is basically a polymarket or prediction markets in general. Maybe we should use money or some allocated budget instead of just static votes because there's certain things that people care about very heavily. It's not just about the votes, there's a lot of interesting decision theory stuff that you can do here. I think that's one of the big points of this is not just to create this base of understanding but actually to provide a framework for us to kind of explore probabilistic true ideas or basic ideas, this and that.

I think because I have very limited time to do this, what I'm going to want is to actually only do the research and the editing side. In fact, I don't even need to do the research side in the sense that I don't need it and I can now do everything for me. What I can probably, well let's actually just use OpenPage.

Yeah, I think the most important part of this, from a practical perspective, is going to be just building front-end and React components. Mostly because I'm also partially preparing for an interview right now. A front-end interview. So I should actually manually write something to write some React just to re-familiarize myself with things. I think those are going to be my two primary goals in addition to just building out the research and editing functionality both.

From that perspective, I think anything that is the newest and most interesting sort of React technology should be the thing that I use just so I can familiarize myself with it a little bit. So, using things with Food Standard, there, I mean, not necessarily those things, but like Zoo Stand, and using Fun to compile, and I don't know, just things like that would be just keep everything TypeScript back in front-end. Yeah, it'd be fun to play with the new tech, new technologies, just so I'm aware.
