---
layout: post
title: "ECMAScript Development Process and TC39"
permalink: ecmascript-development-process
date: "2023-10-12 06:19:59 +0530"
tags: javascript
---

If we compare JavaScript from its early years and the present, they would be worlds apart. The language has evolved so much, that it looks like a brand new language from its beginning. To understand how the language has grown so much, it is important to know the workings of the committee that drove its evolution.

## TC39 - Development Process

TC39 is the committee that is responsible for and has driven the development of JavaScript features through their process which has solidified over the years.

### People

The members of ECMA Technical Committee 39 are actually organizations such as browser vendors and large companies who’ve invested heavily in the web like Microsoft, Google, Apple, Mozilla, Intel, eBay, and others. TC39 has regular meetings which is attended by "delegates" sent by the members and invited by experts. For the meeting, schedules refer <a href="https://github.com/tc39/agendas" target="_blank" rel="nofollow noopener">this</a>

### Process

Each feature addition or removal request goes through a process before it is finalized.

When a new proposal is created, that proposal has to go through certain stages before it becomes part of the official specification. It's important to keep in mind that in order for any proposal to move from one stage to another, a consensus among the TC39 must be met. This means that a large majority must agree while nobody strongly disagrees enough to veto a specific proposal.

Each proposal for an ECMAScript feature goes through the following *maturity stages*, starting with stage 0. The progression from one stage to the next one must be approved by TC39.

#### The vocabulary

**Proposal champion** - someone that worked on the feature proposal and specification directly.

**Implementer** - someone that works on implementing the proposal into a JavaScript engine, parser, runtime or embedding.

**ECMAScript Editor** - The editor is responsible for the overall structure and coherence of the ECMAScript specification. It is also the role of the editor to provide guidance and feedback to spec text authors so that as an addition matures, the quality and completeness of its specification improves. It is also the role of the editor to integrate additions which have been accepted as “finished” (stage 4) into a new revision of the specification.

**Community member** - someone (*you) *who is willing to contribute.

## Stages of TC39 Process

### Stage 0: Strawman

At this stage, it's just an informal submission of a new proposal. New proposals must be from either a TC39 member or someone who has registered as a TC39 contributor.

**Acceptance Criteria** (things to be done for the proposal to get accepted at this stage)

The proposal must be reviewed and then added to <a href="https://github.com/tc39/proposals/blob/master/stage-0-proposals.md" target="_blank" rel="nofollow noopener">this page.</a>

### Stage 1: Proposal

At this stage, the proposal is formally submitted for the review.

**Acceptance Criteria**

- A <span style="text-decoration: underline;">_champion_</span> is identified who will advance the proposal. ( champion must be a member of TC39 )
- Detailed description (prose outlining) the problem solved.
- Illustrative examples of the solution.
- High-level API
- Discussion of key algorithms, abstractions, and semantics Identification of potential <a href="https://stackoverflow.com/questions/23700540/cross-cutting-concern-example" target="_blank" rel="nofollow noopener">cross-cutting concerns</a> (i.e) when the impact is system-wide or affects interaction with other features of the language.
- Implementation challenges/complexity involved.
- Polyfills / Demos are also expected at this stage.

**Next?**

TC39 devotes time to examining the problem space, solutions and cross-cutting concerns

### Stage 2: Draft

Like the name suggests, this stage describes the draft version or the initial version of the proposal using formal spec language. At this point, an eventual inclusion of the feature in the standard is likely.

**Acceptance Criteria**

- Along with the stage 1 work, the proposal must include a complete description using the formal language of the ECMAScript specification.
- The draft spec included must cover all *major* semantics, syntax, and API. The description should be as complete as possible but todos, placeholders and editorial issues can be expected.
- Two experimental implementations of the feature are needed, but one of them can be in a transpiler such as Babel.

**Next?**

Only incremental changes are expected from now on.

### Stage 3: Candidate

This stage indicates that the proposal is ready for inclusion in the formal ECMAScript standard and now needs feedback from implementations and users to progress further.

**Acceptance Criteria**

- The spec text must be complete i.e all semantics, syntax, and API are described completely.
- <a href="https://github.com/tc39/test262" target="_blank" rel="nofollow noopener">Test262</a> acceptance tests have been written for mainline usage scenarios and merged
- Two compatible implementations which pass the acceptance tests
- Significant in-the-field experience with shipping implementations, such as that provided by two independent VMs.
- A pull request has been sent to <a href="https://github.com/tc39/ecma262" target="_blank" rel="nofollow noopener">tc39/ecma262</a> with the integrated spec text
- The ECMAScript editor has signed off on the pull request.

**Next?**

This signifies that the solution is complete and no further work is possible without implementation experience, significant usage, and external feedback.

### Stage 4: Finished

At this stage, as the name suggests, the proposal is ready to be included in the standard.

**Acceptance Criteria**

- <a href="https://github.com/tc39/test262" target="_blank" rel="nofollow noopener">Test262</a> acceptance tests have been written for mainline usage scenarios and merged.
- Two compatible implementations which pass the acceptance tests.
- Significant in-the-field experience with shipping implementations, such as that provided by two independent VMs.
- A pull request has been sent to <a href="https://github.com/tc39/ecma262" target="_blank" rel="nofollow noopener">tc39/ecma262</a>with the integrated spec text.
- The ECMAScript editor has signed off on the pull request.
- All changes as a result of implementation experience are integrated.

**Next?**

The proposal will be included in the ECMAScript specification as soon as possible. When the spec goes through its yearly ratification as a standard, the proposal is ratified as part of it.

## Conclusion

Getting to know the development stages of a language will help one understand how the language has evolved and how the language features are growing. If you want to keep track of the features in various stages you can become an active member and <a title="contributing to ecma262" href="https://github.com/tc39/ecma262/blob/master/CONTRIBUTING.md" target="_blank" rel="nofollow noopener">contribute</a> or just track it in the <a href="https://github.com/tc39/proposals" target="_blank" rel="nofollow noopener">proposals list</a> of the

## Sources

- <a href="https://tc39.github.io/process-document/" target="_blank" rel="nofollow noopener">Official TC39 Process </a>
- <a href="https://github.com/rwaldron/tc39-notes" target="_blank" rel="nofollow noopener">TC39 Meeting Notes</a>
- <a title="TC39" href="https://github.com/orgs/tc39/people" target="_blank" rel="nofollow noopener">Official ECMA TC39</a>
- <a href="https://tc39.github.io/process-document/" target="_blank" rel="nofollow noopener">ECMA TC39 Process Document</a>
- <a href="https://github.com/tc39/ecma262/blob/master/FAQ.md" target="_blank" rel="nofollow noopener">ECMA TC39 - FAQs</a>
