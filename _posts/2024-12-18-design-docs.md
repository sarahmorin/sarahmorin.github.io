---
layout: distill
title: Design Documentation
description: The software engineer's nemesis
date: 2024-12-18
tags: documentation software-engineering
categories:
giscus_comments: true

authors:
    - name: Sarah Morin

toc:
    - name: Purpose
    - name: Common Pitfalls
    - name: Anatomy of Good Design Documents
    - name: Imparting Style
    - name: More Resources
---

Most developers hate writing design documents. Why? The instructions sound simple: just take the
design you have in mind and write it down. Unfortunately, writing *good* documents proves rather
difficult. More often than not, we end up with bad (and I mean terrible) documents that are
difficult to read, impossible to maintain, and ultimately useless.

> Faced with the overwhelming pile of unintelligible design documents, how could one not become
soured to the idea of writing them? 

Luckily, writing good design documents is possible. We simply need to learn how.

# Purpose

When thinking about good vs. bad documentation, it’s important to remember why we write these
documents. 

* **Record of ideas** -- Write the design. I promise, once you start the project (especially
    if it’s complex or long-term), you will forget something. Write it down. Your future self
    will thank you.
* **Identify problems early** -- Working through the details of the design on paper makes it
    easier to spot mistakes and bugs. It’s better to find them before you write thousands of
    lines of code.
* **Team consensus** -- A written document is a good way to make sure everyone agrees before
    development begins. Assuming everyone is on the same page won’t cut it (and we all know what
    they say about assuming).
* **External collaboration** -- Communicating your design with people outside your immediate team
    (managers, other feature teams, on-boarding team members, etc.) is markedly easier when you
    can simply share a document.

There's also my (somewhat) cynical take on writing good documentation: fewer annoying questions!
If you have to answer the same question more than once, you might as well write it down and point
people to a doc. It’s just makes life easier.

## Common Pitfalls

While there are infinitely many versions of the "bad design doc", a few varieties are particularly
common because they are easy to write. Don't fall into the trap!

* **Stream of Conciousness** — The free-form word dump. Is this a reasonable first draft to get
    ideas from brain to page? Yes. Is it acceptable to share as a final version? No. 
* **The Everything Page** — Stuff everything (background, design, API specs, test plan,
    development schedule) into one page. Great, right? I mean…all the information is there. Wrong.
    These are hard to read and nearly impossible to maintain as the design evolves and you work
    on the project.
* **Depth-First Design** — Details first, context later! This is the document I find most often.
    You’ve been working on a problem for a while and dive into the details of your design almost
    immediately. Unfortunately, you’ve forgotten most of your audience isn’t working on this
    project and needs a lot of context before they can understand any of what you just said.

# Anatomy of Good Design Documents

How do we write good design documents? Structure.

> Separate the design from its development.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/design_docs.svg" title="Anatomy of Good Design Docs" class="img-fluid rounded z-depth-0" %}
    </div>
</div>

 
Although closely related, the design and the development plan are distinct pieces of information. 
Yes, we often make design choices based on time and effort of implementation (i.e. the schedule)
and the design itself informs which developers work on each task; however, we need to focus on the
reader’s perspective. Consider a senior engineer who needs to approve the design of a new feature.
Do they really need to see the full-schedule or do they just want to read the design? Similarly, a
manager might want to understand the task breakdown and schedule without getting into the weeds of
technical details.

Another major benefit to organizing information this way is ease of updates. Schedules change
constantly and sifting through the full design to update the project schedule is a pain. Breaking
the design into manageable pieces (rather than the ominous Everything Document) is better for both
author and reader.

### The High Level Summary

The high level summary should gradually introduce readers to the project by giving context to the
problem, highlighting goals, briefly describing the solution, and discussing potential concerns. Be
careful not to dive into the details here (we don't want a depth first design) and make sure to keep
any design information very high-level. This document should be easily digestible for anyone
unfamiliar with the project.


{% details Example Structure %}
1. Problem Summary and Background
1. Requirements, Goals, and Non-Goals
1. Solution Summary
1. Diagrams and Workflows
1. Trade-offs, Performance, and Concerns
{% enddetails %}


### Component Details

After the high-level summary, we can get into the meat of the design. The number of these types of
pages varies from project to project, but a good rule of thumb is one detailed design page per
component. It is reasonable to assume that the reader is familiar with the project or has at least
read the high-level summary, so avoid redundancy. In addition to the detailed design, the doc
might include more specific requirements, API specifications, performance impacts, potential future
improvements, etc. 


{% details Example Structure %}
1. Component Summary (background if we are modifying an existing component)
1. Specific Requirements
1. Design Details
1. API Specs
1. Performance Impact Analysis
1. Future work
{% enddetails %}

### Development Plan

Once we have the design, we can flesh out implementation logistics in the development plan docs.
Most projects need two docs: the task breakdown/schedule and the test plan. I feel these are fairly
intuitive documents, so my only advice is this: keep it simple. It is highly likely you will be
updating these documents constantly, so make them easy to revise.


# Imparting Style

Everything I've outlined so far is just a starting point. Every project is different and the design
documents should reflect that. Ultimately, we just want the document to be both useful and easy to
digest. Writing good documentation takes practice and patience, yes, but it shouldn't be devoid of
any creativity. As long as the docs are still effective, impart your own style, especially if that
helps motivate you to write them.

---

# More Resources

This post is inspired by a mini-lecture I presented to the GWU Senior Design class of 2024 while
serving as one of their alumni mentors.
See the full [slides]({{ site.url }}/assets/pdf/design_docs_pres.pdf)<d-footnote>If you would like a watermark free copy of these slides, reach out and let me know :)</d-footnote>.

[How to write an effective design document - Rina Artstain](https://rinaarts.com/how-to-write-an-effective-design-document/)

[Design Docs at Google](https://www.industrialempathy.com/posts/design-docs-at-google/)

[Writing Design Docs - Oppia](https://github.com/oppia/oppia/wiki/Writing-design-docs)
