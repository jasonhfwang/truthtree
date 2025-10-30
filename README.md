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

- Should direct agent to investigate a single topic — e.g. chicken domestication
