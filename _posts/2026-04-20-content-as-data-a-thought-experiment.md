---
layout: post
title: "Content as data: a thought experiment"
category: Billets
excerpt_separator: <!--more-->
tag: Blog
lang: EN
ref: content-as-data
---

We keep running into the same problem with program and service content for the Government of Canada: a rule or an amount changes in a program, and five teams scramble to update five different things. A web page, a PDF, a call centre script, an internal tool, a chatbot, etc. So I spent a few evenings building a proof of concept to see what it would look like if the rules only lived in one place.

<!--more-->

The experiment uses 3 Government of Canada programs: the Canada Child Benefit, Employment Insurance, and Old Age Security. Each one is encoded as a single JSON file containing every threshold, rate, reduction bracket, and examples, in both English and French. Then I built a few things using the same "single source of truth".

Take a look: [GC rules API experiment](https://www.davidpepin.ca/gc-rules-api/webapp/)

<img class="img-fluid" style="border: 1px solid #ddd; border-radius: 4px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);" src="{{ site.baseurl }}/images/web_app_api.png" alt="Web page showing a hub to access several tools built with the same JSON files."/>


## Several tools, one source

The idea was to see if I could use a "rules as code" approach to important program information to populate different tools. Here's what I got.

- An [interactive estimator](https://www.davidpepin.ca/gc-rules-api/webapp/estimator.html) where you plug in your situation and get a calculated amount:
- Static [Canada.ca web content](https://www.davidpepin.ca/gc-rules-api/site/_site/en/canada-child-benefit/how-much.html), generated from the JSON file
- A local chatbot reading Markdown files generated from the JSON file, reducing hallucinations
- A [JSON editor](https://www.davidpepin.ca/gc-rules-api/webapp/editor.html) where a policy analyst could update parameters — income thresholds, benefit rates, age cutoffs — without ever opening a JSON file
- An [API explorer](https://www.davidpepin.ca/gc-rules-api/webapp/api.html), simulating how anyone could call the program information through an API.

Under all of it, the same JSON files.

We could further: secure applications, call center scripts, training material. All of it could in theory be derived from a single source of truth.

## Much more to explore

I want to be clear: this is a thought experiment, nowhere near production-ready. The real programs are way more complex than what these JSON files cover. Discretion, edge cases, appeals, exceptions for specific provinces — encoding all of that is a governance and policy challenge as much as a technical one. I haven't solved any of those problems with this experiment.

What I *have* done is made the idea tangible enough to start playing around with it. 

Can we imagine a world where accurate government content on programs and services is offered to anyone and any tool, thrugh an API?

The [repo is public on GitHub](https://github.com/quidampepin/gc-rules-api). Poke around, break things. Let me know what you find.

*Built with the help of Claude (Anthropic) for the coding and iteration. Inspired by [OpenFisca](https://openfisca.org/), New Zealand's [Better Rules](https://www.digital.govt.nz/showcase/better-rules-for-government-discovery-report/), and conversations with colleagues working on digital service delivery in the GC.*