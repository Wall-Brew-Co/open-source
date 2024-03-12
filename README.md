# Open Source

At Wall Brew, we've done our best to extract as much useful functionality from our stack and make it available to the public.
This repository documents how we work to provide high-quality software and our guidelines and expectations for contributors and maintainers alike.

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Libraries](#libraries)
  - [Beer and Brewing](#beer-and-brewing)
  - [Utility](#utility)
- [Philosophy](#philosophy)
  - [Community Standards](#community-standards)
  - [Worse is Better](#worse-is-better)
  - [The Developer Experience](#the-developer-experience)
- [Requirements](#requirements)
  - [Software Documentation](#software-documentation)
  - [Community Documentation](#community-documentation)
    - [Code of Conduct](#code-of-conduct)
    - [Contributor Guidelines](#contributor-guidelines)
    - [Licensing](#licensing)
- [Preferences](#preferences)
  - [Template Community Documents](#template-community-documents)
  - [Automating Opinions](#automating-opinions)
  - [An Indexed Community](#an-indexed-community)
  - [Get It For Free](#get-it-for-free)
- [Suggested Reading](#suggested-reading)
- [Implementation](#implementation)
- [License](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Libraries

### Beer and Brewing

- [brew-bot:](https://github.com/Wall-Brew-Co/brew-bot "The brew-bot repository") A clojure(script) library designed to generate random beer recipes.
- [brewtility:](https://github.com/Wall-Brew-Co/brewtility "The brewtility repository") A clojure(script) utility library for algorithmic brewing.
- [common-beer-data:](https://github.com/Wall-Brew-Co/common-beer-data "The common-beer-data repository") A clojure(script) library containing common ingredients used in brewing.
- [common-beer-format:](https://github.com/Wall-Brew-Co/common-beer-format "The common-beer-format repository") A clojure(script) library containing a clojure.spec implementation of the [BeerXML specification](http://www.beerxml.com/ "The BeerXML Beer Recipes Exchange Standard").

### Utility

- [clj-xml:](https://github.com/Wall-Brew-Co/clj-xml "The clj-xml repository") A clojure library designed to make conversions between EDN and XML a little easier.
- [keg:](https://github.com/Wall-Brew-Co/keg "The keg repository") A clojure library library to unobtrusively log functions.
- [lein-sealog:](https://github.com/Wall-Brew-Co/lein-sealog "The Sealog repository") - A [Leiningen](https://leiningen.org/ "Leiningen is a clojure build tool") plugin for managing your changelog.

### Deprecated

- [strawpoll-client:](https://github.com/Wall-Brew-Co/strawpoll-client "The strawpoll-client repository") A clj-http client library to interact with the [StrawPoll API](https://strawpoll.com/ "The StrawPoll home page")

## Philosophy

Our open-source philosophy describes our fundamental beliefs and values and why we value them.
Since philosophy tends to be abstract, this section is intended to be educational more than it is a means of handling concrete situations.
We do not expect every member to personally hold the same beliefs or perspectives as we do; however, we have derived many of our practices and standards from our philosophy.
Therefore, we believe it is important to share with our open-source community.

### Community Standards

Human interaction is complex and subject to many different lenses of personal, contextual, and cultural influence.
Every individual has their own perception of what they consider to be helpful, harmful, professional, and casual conduct.
Differences in these perceptions can leady to unhealthy or harmful conflicts of opinion, which can cascade into real harm against a person's emotional, physical, and/or mental well-being.
Within a community, it is important to ensure that differences in opinion may be held without adversely impacting any community member.

However, we each individually hold our own perceptions of what a community is and ought to be.
Enforcing any communal rules or standards requires a shared understanding of what is and is not considered acceptable behavior and language.
Without a shared context for a community, fair and even judgement, remediation, and enforcement of community rules and standards is impossible.

Therefore, it is important to be explicit on what boundaries exist and what territory may be adjacent to those boundaries.
Those fostering communities must not only communicate their expectations clearly, but also take care to consistently and promptly enforce those expectations.
In some cases, that requires explicitly removing bad faith members of a community.

### Worse is Better

Software often abstracts many real-world problems; instead of self-imposed problems of software engineering.
However, all abstractions are lossy- and software abstractions are consumed by humans.
This often leads to uncertainty during development on what conceptual needs are most important.

- Is it more important to effectively represent reality or to keep the abstraction clean?
- Should software support every real world corner case, regardless of how common it may be?
- What interface should exist between engineers and the tools they use?

With these questions in mind, we believe the most important relationship to consider is that between the abstraction and the engineer.

For that reason, our design philosophy holds these four concepts in a strict order of preference as outlined in the _Worse is Better_ philosophy:

- **Simplicity** - The simplicity of design and interface is the most important consideration
- **Correctness** - The design should be correct; however, if a tradeoff is to be made, simplicity is slightly preferable
- **Consistency** - Consistency is an import means to ensure simplicity; however, it is better to remove parts of a design steeped in inconsistency than to introduce complexity
- **Completeness** - Designs should cover the most important and common cases, and any further cases which may be practical without sacrificing any other attribute.

### The Developer Experience

Software is largely written and consumed by humans.
Developing software is an acquired skill that requires considering many different tradeoffs at once.
A common difficulty individuals find while developing software is the cognitive overload of remembering and thoughtfully considering the number of options, tradeoffs, and implementations available at any given point in time.
Many of these tradeoffs and considerations are self-imposed by the tools, programming languages, and libraries we use.

As the primary authors and consumers of our work, we are uniquely situated to make tools, languages, and libraries that are easy and simple to consume without inflicting cognitive overload on others.
Therefore, our work must have a focus on how other engineers will refer to and leverage the tools we make.
A failure to do so is not only a disservice to ourselves, but to our peers.

## Requirements

Several of our philosophies manifest as concrete requirements that every Wall Brew library and maintainer must uphold.
These are policies and practices which cannot be superseded, ignored, or violated except in the most extreme of situations.
Maintainers are expected to kindly and professionally reinforce our requirements, and to help contributors make the adjustments necessary to meet them as well.
Consistent, intentional, or bad-faith violations of these requirements may be grounds to remove, edit, or reject comments, commits, code, wiki edits, issues, and other contributions, or to ban temporarily or permanently any contributor or maintainer.

### Software Documentation

Software is written and consumed by humans; machine code is written and consumed by machines.
Since our open-source presence provides software libraries, we should build them to be consumed by humans.
However, this belief is neither equally supported nor held across all programming communities.
While code literacy is an important skill for programmers, it should not be a barrier to entry to using open-source libraries.
Every effort should be made to make the use of Wall Brew open source offerings as straightforward as possible.

It is required that:

- Every piece of functionality intended for consumption as part of a public API is documented in a format which renders to a human-readable implementation (e.g. Markdown, HTML)
- Functions, namespaces, etc are annotated with docstrings and metadata which will render in common development tools
- Real-life examples, with results, are provided to consumers
- Every releasable change comes with a human readable description of the changes made (e.g. CHANGELOG.md, annotated git tags)

It is recommended that:

- All assertions within a test suite describe the goal of the test case
- Docstrings point consumers to similar and related functionality
- Domain-specific knowledge relevant to functionality is described in a human-friendly narrative context

It is not sufficient to:

- Point consumers to the implementation unless absolutely critical
- Require consumers to read the implementation to discover functionality
- Require consumers to read to implementation to perform root-cause analysis
- Refer to the implementation as self-documenting

### Community Documentation

Wall Brew is committed to providing a safe, welcoming, and productive community for our software projects.
To that end, we believe setting explicit, up-front boundaries helps set the tone and expectations for our community.
Therefore, all open-source projects released under the Wall Brew umbrella must provide full text copies of or links to the standard collection of community documents outlined below.
These outline recommendations, rules, and requirements for participating in our open source ecosystem at multiple levels.
It is expected that all contributors hold themselves to these standards, and it is required that all maintainers reinforce these basic contracts.

#### Code of Conduct

All community members should have a clear and shared understanding of what is considered acceptable and unacceptable behavior.
To prevent ad-hoc or just-in-time rule setting, we have explicitly outlined our expectations and rules in text.
Our [Code of Conduct](https://github.com/Wall-Brew-Co/rebroadcast/blob/master/sources/community/CODE_OF_CONDUCT.md "The minimum behavioral standards we expect from the community") strives to meet three goals:

- Welcome contributors and participants
- Define basic standards and rules for community participation
- Outline procedures for handling abuse and violation of said rules and standards

At a minimum, we expect all contributors and maintainers:

- Use welcoming and inclusive language that respects the names, pseudonyms, and pronouns individuals select for themselves
- Respect differing viewpoints and experiences
- Accept constructive criticism and suggestions gracefully
- Focus on what is best for the community
- Show empathy towards other community members
- Act in a professional manner

Additionally, we explicitly prohibit:

- The use of sexualized language, sexualized imagery, and any sexual attention or advances
- Trolling, insulting/derogatory comments, and personal attacks of any variety
- Discrimination of any kind
- Threats in any form against an individual's mental, emotional, or physical safety
- Public or private harassment
- Publishing others' private information, such as a physical or electronic address, without explicit permission
- Other conduct which could reasonably be considered inappropriate in any setting

Maintainers are expected to remove, edit, or reject any contribution that does not meet these standards.
Further, any maintainer or contributor found grossly in violation, intentionally in violation, or repeatedly in violation of these guidelines may be banned temporarily or permanently at the sole discretion of Wall Brew.

Violations of these guidelines may be reported publicly by tagging any Wall Brew Maintainer or in private by emailing contact [at] wallbrew [dot] com.

#### Contributor Guidelines

Wall Brew strives to make contributions as simple as possible while ensuring our software consistently meets our standards.
Our expectations for external contribution are outlined in our [contribution guidelines.](<https://github.com/Wall-Brew-Co/open-source/blob/master/templates/CONTRIBUTING.md> "The minimum technical standards we expect from contributors")
This document aims to:

- Provide basic instructions and guidelines for contribution
- Inform contributors of the actions/requests that Wall Brew maintainers and automated entities may take
- Explicitly outline that all contributions must adhere to any applicable intellectual property laws and the open source license in each repository.
- Explicitly outline that all contributions must adhere to the Code of Conduct

#### Licensing

Wall Brew libraries are generally provided in accordance with the [MIT License.](https://opensource.org/licenses/MIT "OpenSource.org references to the MIT License")
Exceptions to this rule are generally only supported in instances where Wall Brew does not have the authority to select the applicable license; for example, a fork of a repository explicitly covered by the [GNU GPL](https://www.gnu.org/licenses/gpl-3.0.en.html "The GNU GPL v3.0 license's full text")

## Preferences

More commonly, our philosophies manifest as preferences.
We state them here to be explicit and to help ourselves stay as consistent as possible.
Preferences are explicitly weaker than requirements, and may be bypassed in some circumstances.
Maintainers will endeavor to point out our preferences, but they are not strict requirements of contributors.

### Template Community Documents

Since all Wall Brew libraries are beholden to the same standards, community documents (e.g. a Code of Conduct) ought to be templated- requiring only the repository name, relevant URLs, etc to be updated per-instance.
Full text copies of our community documents may be found in the [`rebroadcast`](https://github.com/Wall-Brew-Co/rebroadcast "Our source-of-truth for template documents and repository configuration") repository.

Occasionally, sections of these documents may not reasonably apply to certain repositories.
Other repositories may require additional considerations not accounted for in the basic template.
In either of these cases, maintainers may amend the community documents to a repository's specific needs.
The community documentation of a repository will generally supersede the analogous template- barring extreme circumstance.

Pragmatically, these updates are made in a single source-of-truth and then rebroadcast to all relevant repositories.
This minimizes the chance for transpositional errors (e.g. linking to the wrong repository's License within a Code of Conduct), and errors of omission (e.g. forgetting to update all impacted repositories when the Security Policy is updated)

### Automating Opinions

The field of software engineering is filled  with many conflicting opinions that do not impact what code is executed.
For example:

- Style and formatting conventions
- The definition of "clean code"
- Useful annotations on code

Individual preferences largely sway how we write code, but this can lead to a haphazard and inconsistent project when split across multiple individuals.
These conventions generally do not impact the ability for users to write code in the IDE of their choice or with the tools they desire or need.
Individual conventions may only incrementally improve upon any other convention, and there is a real cognitive cost to inconsistency.
Therefore, we maintain standard conventions and format preferences across our repositories.

We do not maintain that our conventions, style, or formats are any better than any other alternative; however, we do maintain that they should be consistent across all of our offerings.
Human enforcement of these patterns is occasionally required (e.g. for consistent naming standards); however, humans make mistakes and may miss items that should be addressed.
Therefore, Wall Brew has automated as much enforcement of a canonical style as is reasonable.

### An Indexed Community

Many open source communities have evolved to include communities on Discord, Slack, IRC, etc.
In practice, this can be a fast way to receive help or to organize activity; however, it does come at a cost.
Even on free platforms, there are few guarantees on how long messages will exist for consumption.
Additionally, these platforms require third party tooling to persist messages permanently in a state that can be indexed by search engines.

Since search engines are a common and instinctive tool in a software engineer's toolkit, we believe it is better to communicate changes, aid community members in bug analysis, and discuss future changes on a platform that is regularly indexed and also canonically connected to our projects.
We believe this creates an easy, searchable, and simple interface to find any information about any of our offerings.

To that end, we leverage GitHub as our primary point of communication and interaction- and will selectively broadcast updates that refer back to this central hub.

### Get It For Free

For every point we've outlined in this document, we could select from many implementations to fulfill our needs and preferences.
There are many companies and resources which exist to fulfill each of these needs, and they each come with their own tradeoffs, paradigms, and cognitive overhead.
Some of these options require payment, some require plugins or third-party extensions, and all come with some cost of maintenance and implementation.

The maintenance cost of our suite of tools must be set in balance against the value they provide.
We seek to use as few tools as possible and to get as much out of those tools as possible.
For example, GitHub has built-in tools and support for autonomous code review, linting, etc.
There are several other companies which offer these features that can integrate with GitHub; however, it would require supporting multiple platforms and experiences within the context of a single pull request.

## Suggested Reading

- Software Engineering Philosophy
  - [The Rise of Worse is Better](https://www.dreamsongs.com/RiseOfWorseIsBetter.html "The core design philosophy of Wall Brew libraries")
  - [The Twelve-Factor App](https://12factor.net/ "An application framework which promotes simplicity and consistency between development and deployment")
- Community Standards
  - [Building Community](https://opensource.guide/building-community/ "GitHub's documentation on fostering an Open Source Community")
  - [Moderator Academy](https://discord.com/moderation "Discord's community resources and classes for moderation")
  - [Contributor Covenant FAQ](https://www.contributor-covenant.org/faq/ "Questions frequently asked about the Contributor Covenant the Wall Brew Code of Conduct is derived from")
  - [The Paradox of Tolerance](https://en.wikipedia.org/wiki/Paradox_of_tolerance "Why enforcing social limits is important to maintaining a tolerant community")

## Implementation

- [rebroadcast](https://github.com/Wall-Brew-Co/rebroadcast "Our source-of-truth for template documents and repository configuration")
- [clojure-lint-action](https://github.com/nnichols/clojure-lint-action "An automated tool that reports clj-kondo findings to relevant Pull Requests")

## License

Copyright © [Wall Brew Co](https://wallbrew.com/ "Wall Brew's Home page")

This documentation is provided for free, public use as outlined in the [MIT License](https://github.com/Wall-Brew-Co/open-source/blob/master/LICENSE "A full-text copy of the MIT License")
