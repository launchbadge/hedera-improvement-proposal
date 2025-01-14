- hip: 1
- title: Hedera Improvement Proposal Process
- author: Ken Anderson (@kenthejr)
- type: Process
- status: Draft
- created: 2021-02-11
- discussions-to: https://github.com/hashgraph/hedera-improvement-proposal/discussions/54
- updated: 2021-05-12

## What is a HIP?

HIP stands for Hedera Improvement Proposal. A HIP is intended to provide information or initiate engineering effort to update Hedera functionality. The HIP should be technically clear and concise. HIPs should be as granular as possible. Small targeted HIPs are more likely to reach consensus and result in a reference implementation. This may require breaking a bigger idea into smaller components.

HIPs are intended to be the primary mechanism for proposing new features, for collecting community input, and for documenting the design decisions that have gone into Hedera Hashgraph. The HIP author is responsible for building consensus within the community and documenting dissenting opinions.

Because the HIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

HIPs are not meant to address *bugs* in implemented code. Bugs should be addressed using issues on the implementation's repository.

## HIP Types

There are three kinds of HIP:

1. A **Standards Track** HIP describes a new feature or implementation for Hedera. It may also describe an interoperability standard that will be supported outside of the official Hedera node software stack. The Standards Track HIP abstract should include which part of the Hedera ecosystem it addresses. Standards Track HIPs require a specification and a reference implementation:

    **a. Core:** This includes proposals addressing the Hashgraph algorithm, peer-to-peer networking, etc. These types of features are implemented on Hedera consensus nodes.

    **b. Service:** Hedera services sit on top of the Core node software and provide the functionalities that are accessed by users. These currently include the File Service, Consensus Service, Token Service, and Smart Contract Service. This type of proposal should be used to add to or improve the service-layer of Hedera. These types of features are implemented on Hedera consensus nodes.

    **c. API:** The primary interface for Hedera is called the Hedera Application Programming Interface, or “HAPI” for short. HAPI is a gRPC interface for client software to interact with the Hedera service-layer. The serialization protocol for HAPI is protocol buffers, also known as “protobuf”. These types of features are implemented on Hedera consensus nodes.

    **d. Mirror:** A mirror node runs software designed to retrieve all or some of the records generated by the Hedera consensus nodes and make those records available to users in a way that is meaningful, reliable, and trustworthy.

    **e. Application:** Application standards may be used to standardize software in the Hedera ecosystem that aren’t mirror or consensus nodes. This includes application network software, external contract validators, multi-sig oracles, persistence mechanisms, enterprise software plugins, etc. An example of an Application standard would be the Stablecoin Contract and Non-fungible Token Contract written in Java as a layer-2 solution using the Hedera Consensus service to maintain trust.

2. An **Informational** HIP describes a Hedera design issue, or provides general guidelines or information to the Hedera community, but does not propose a new feature. Informational HIPs do not necessarily represent a Hedera community consensus or recommendation, so users and implementers are free to ignore Informational HIPs or follow their direction.

3. A **Process** HIP describes a process surrounding Hedera, or proposes a change to a process. Process HIPs are like Standards Track HIPs but apply to areas other than the node and ecosystem software codebases. They may propose an implementation, but not to Hedera’s codebase; they often require community consensus; unlike Informational HIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, and changes to the decision-making process. Any meta-HIP is also considered a Process HIP.

## HIP Workflow

### Hedera Council

The Hedera Council or “the Council” is made up of large organizations who participate in decisions related to the technical development roadmap, treasury management, and general governance. The Council has the final say on Core, Service, API, and Mirror node Standards Track HIPs.

### Hedera Core Developers

Hedera Core Developers or “core developers” include those who are tasked with development of any part of the Hedera platform or ecosystem; this includes employees of Hedera, contractors hired by Hedera directly, and community developers who have received grants to develop and maintain a project.

### HIP Editors

The HIP editors or “editors” are individuals responsible for managing the administrative and editorial aspects of the HIP workflow. HIP editorship is by invitation of the current editors or by assignment by the Council.

### Start with an idea for Hedera

The HIP process begins with a new idea for Hedera. It is highly recommended that a single HIP contain a single key proposal or new idea. The more focused the HIP, the more successful it tends to be. Hedera collaborators and maintainers reserve the right to reject a HIP if it appears too unfocused or too broad. If in doubt, split your HIP into several well-focused ones.

Each HIP must have a champion -- someone who writes the HIP using the style and format described below, shepherds the discussions in the appropriate forums, and attempts to build community consensus around the idea. The HIP champion (a.k.a. Author) should first attempt to ascertain whether the idea is HIP-able. Circulating the idea in Hedera’s Discord server (https://hedera.com/discord) or in an issue in the Hedera HIP Github Repository (https://github.com/hashgraph/hedera-improvement-proposal) is the best way to do so.

Vetting an idea publicly before going as far as writing a HIP is meant to save the potential author time. Asking the community first if an idea is original helps avoid too much time being spent on something that may be rejected based on prior discussions. It also helps to make sure the idea is applicable to the entire community and not just the author. The ideal place to vet ideas is in the GitHub Discussions "Ideas" category (https://github.com/hashgraph/hedera-improvement-proposal/discussions/categories/ideas).

Authors should:

1. Create a new discussion with the category of "Ideas".
2. Ensure that the title of the Idea is your proposed title for the HIP.
3. Fill out as much of the HIP template as the initial discussion comment.
4. Update the initial comment with any updates that have received consensus.

The goal is that once the Idea has been fully vetted, it should be relatively trivial to submit a formal HIP.

Once the champion has discovered with the Hedera community the acceptability of the idea, the proposal should be submitted as a draft HIP via a Github pull request. The draft must be written in HIP style as described below, else it will fail review immediately (although minor errors may be corrected by the editors).

### Submitting a HIP

The standard HIP workflow is:

* You, the HIP author, fork the HIP repository, and create a file named hip-0000-my-feature.md (where “my-feature” is descriptive) that contains your new HIP. Use 0000 as your draft HIP number. This file should be created from the HIP template.

* In the “Type” header field, enter “Standards Track”, “Informational”, or “Process” as appropriate, and for “Status” field enter “Draft”.

* Push this to your Github fork and submit a pull request.

* The HIP editors review your PR for structure, formatting, and other errors. Approval criteria are:

    * It is sound and complete. The ideas must make technical sense. The editors do not consider whether they seem likely to be accepted.

    * The title accurately describes the content.

    * The HIP’s language (spelling, grammar, sentence structure, etc.) and code style should be correct and conformant.

    Editors are generally quite lenient about this initial review, expecting that problems will be corrected by the reviewing process.

    If the HIP isn’t ready for approval, an editor will send it back to the author for revision, with specific instructions.

* Once approved, editors will assign your HIP a number and merge your PR into the main branch.

HIP editors will not unreasonably deny publication of a HIP. Reasons for denying HIP status include duplication of effort, being technically unsound, or not providing proper motivation.

Developers with git push privileges for the HIP repository may claim HIP numbers directly by creating and committing a new HIP. When doing so, the developer must handle the tasks that would normally be taken care of by the HIP editors. This includes ensuring the initial version meets the expected standards for submitting a HIP. Alternatively, even developers should submit HIPs via pull request.

After a HIP number has been assigned, a draft HIP may be discussed further in the Hedera Developer Discord server or in issues referencing the HIP.

HIP authors are responsible for collecting community feedback on a HIP before submitting it for review.

### HIP Review & Resolution

Once authors have completed a HIP, they may request a review for style and consistency from the HIP editors.

However, content review and final acceptance of the HIP must be requested of the core developers, which may include community developers responsible for the codebase being proposed for improvement.

For a HIP to be accepted, it must meet certain minimum criteria. It must be a clear and complete description of the proposed improvement. The improvement must represent a net value-add. The proposed implementation, if applicable, must be solid and must not complicate the network unduly.

Once a HIP has been accepted, the reference implementation must be completed. When the reference implementation is complete and incorporated into the main source code repository, the status will be changed to “Final”. A Standards Track HIP must include a specification and a reference implementation in order to be considered for a "Final" status. For Process HIPs and Standards Track HIPs that introduce protocol standards, once the process or protocol has been implemented and recognized as official by a combination of the community, core developers, and the Council, the status will be changed to “Final”.

To allow gathering of additional design and interface feedback before committing to long term stability, a HIP may also be marked as “Provisional”. This is short for “Provisionally Accepted”, and indicates that the proposal has been accepted for inclusion, but additional user feedback is needed before the full design can be considered “Final”. Unlike regular accepted HIPs, provisionally accepted HIPs may still be Rejected or Withdrawn even after the related changes have been implemented.

Wherever possible, it is considered preferable to reduce the scope of a proposal to avoid the need to rely on the “Provisional” status, as this status can lead to version compatibility challenges in the wider Hedera ecosystem.

A HIP can also be assigned the status of “Deferred”. The HIP author or an editor can assign the HIP this status when no progress is being made on the HIP. Once a HIP is deferred, a HIP editor can re-assign to draft status.

A HIP can also be “Rejected”. Perhaps, after all is said and done, it was not a good idea. It is still important to have a record of this fact. The “Withdrawn” status is similar - it means that the HIP author themselves has decided that the HIP is actually a bad idea, or has accepted that a competing proposal is a better alternative.

When a HIP is Accepted, Rejected or Withdrawn, the HIP should be updated accordingly.

HIPs can also be superseded by a different HIP, rendering the original obsolete. This is intended for Informational HIPs, where version 2 of an API can replace version 1.

The possible paths of the status of HIPs are as follows:

![HIP States](../assets/hip-1/hip-states.jpg)

Some Informational or Process HIPs may also have a status of “Active” if they are never meant to be completed. An active HIP may be made "Inactive" or "Replaced" by another HIP.

### HIP Maintenance

In general, Standards track HIPs are no longer modified after they have reached the Final state. Once a HIP has been completed, the Hedera codebase becomes the formal documentation of the expected behavior.

If changes based on implementation experience and user feedback are made to Standards track HIPs while in Provisional state, those changes should be noted in the HIP, such that the HIP accurately describes the state of the implementation at the point where it is marked Final.

Informational and Process HIPs may be updated over time to reflect changes to the development practices and other details. The precise process followed in these cases will depend on the nature and purpose of the HIP being updated.

## What belongs in a successful HIP?

Each HIP should have the following parts/sections:

1. Preamble -- RFC 822 style headers containing meta-data about the HIP, including the HIP number, a short descriptive title (limited to a maximum of 44 characters), the names and, optionally, the contact info for each author, etc.

2. Abstract -- a short (~200 word) description of the technical issue being addressed.

3. Motivation -- The motivation is critical for HIPs that want to change the Hedera codebase or ecosystem. It should clearly explain why the existing specification is inadequate to address the problem that the HIP solves. HIP submissions without sufficient motivation may be rejected outright.

4. Rationale -- The rationale fleshes out the specification by describing why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages.

    The rationale should provide evidence of consensus within the community and discuss important objections or concerns raised during the discussion.

5. User stories -- Provide a list of "user stories" to express how this feature, functionality, improvement, or tool will be used by the end user. Template for user story: “As (user persona), I want (to perform this action) so that (I can accomplish this goal).”

6. Specification -- The technical specification should describe the syntax and semantics of any new features. The specification should be detailed enough to allow competing, interoperable implementations for at least the current Hedera ecosystem.

7. Backwards Compatibility -- All HIPs that introduce backward incompatibilities must include a section describing these incompatibilities and their severity. The HIP must explain how the author proposes to deal with these incompatibilities. HIP submissions without a sufficient backward compatibility treatise may be rejected outright.

8. Security Implications -- If there are security concerns in relation to the HIP, those concerns should be explicitly addressed to make sure reviewers of the HIP are aware of them.

9. How to Teach This -- For a HIP that adds new functionality or changes interface behaviors, it is helpful to include a section on how to teach users, new and experienced, how to apply the HIP to their work.

10. Reference Implementation -- The reference implementation must be complete before any HIP is given the status of “Final”. The final implementation must include test code and documentation.

11. Rejected Ideas -- Throughout the discussion of a HIP, various ideas will be proposed which are not accepted. Those rejected ideas should be recorded along with the reasoning as to why they were rejected. This both helps record the thought process behind the final version of the HIP as well as preventing people from bringing up the same rejected idea again in subsequent discussions.

    In a way, this section can be thought of as a breakout section of the Rationale section that focuses specifically on why certain ideas were not ultimately pursued.

12. Open Issues -- While a HIP is in draft, ideas can come up which warrant further discussion. Those ideas should be recorded so people know that they are being thought about but do not have a concrete resolution. This helps make sure all issues required for the HIP to be ready for consideration are complete and reduces people duplicating prior discussions.

13. References -- A collections of URLs used as references through the HIP.

14. Copyright/license -- Each new HIP must be placed under the Apache License, Version 2.0 -- see [LICENSE](../LICENSE) or (https://www.apache.org/licenses/LICENSE-2.0)

## HIP Formats and Templates

HIPs should be written in markdown format. There is a template to follow.

### HIP Header Preamble

Each HIP must begin with a header preamble in list format. The headers must appear in the following order. Headers marked with “*” are optional and are described below. All other headers are required.

- hip: HIP number (this is determined by the HIP editor)
- title: HIP title
- author: a list of the author’s or authors’ name(s) and/or username(s), or name(s) and email(s).
- type: <Standards Track | Informational | Process>
- \* category: <Core | Service | API | Mirror | Application>
- status: <Draft | Active | Inactive | Provisional | Deferred | Rejected | Withdrawn | Final | Replaced >
- created: date created on
- \* discussions-to: a URL pointing to the official discussion thread
- \* updated: comma separated list of dates
- \* requires: HIP number(s)
- \* replaces: HIP number(s)
- \* superseded-by: HIP number(s)

Headers that permit lists must separate elements with commas.

Headers requiring dates will always do so in the format of ISO 8601 (yyyy-mm-dd).

#### `author` header

The author header lists the names, email addresses or GitHub usernames of the authors/owners of the HIP. Those who prefer anonymity may use a username only, or a first name and a username. The format of the author header value must be:

Random J. User <address@dom.ain>

or

Random J. User (@username)

if the email address or GitHub username is included, and Random J. User

if email or username are not given.

It is not possible to use both an email and a GitHub username at the same time. If important to include both, one could include their name twice, once with the GitHub username and once with the email.

At least one author must use a GitHub username in order to be notified on change requests and have the capability to approve or reject them.

#### `discussions-to` header

While a HIP is a draft, a discussions-to header will indicate the URL where the HIP is being discussed. Examples of places to discuss your HIP include an issue in this repo or in a fork of this repo, the Hedera Developer Discord, or Reddit r/hashgraph.

No discussions-to header is necessary if the HIP is being discussed privately with the author.

As a single exception, discussions-to cannot point to GitHub pull requests.

#### `type` header

The Type header specifies the type of HIP: Standards Track, Informational, or Process. If the track is Standards, the HIP must include the category header.

#### `category` header

The category header specifies the HIP category (Core, Service, API, Mirror, Application). This is required for Standard Track HIPs only.

#### `created` header

The created header records the date that the HIP was assigned a number. This header should be in ISO 8601 format (yyyy-mm-dd), e.g. 2019-09-16.

#### `updated` header

The updated header records the date(s) when the HIP was updated with “substantial” changes. The header is only valid for HIPs of Draft and Active status. This header should be in ISO 8601 format (yyyy-mm-dd), e.g. 2019-09-16.

#### `requires` header

HIPs may have a requires header, indicating the HIP numbers that this HIP depends on.

#### `superseded-by` and `replaces` headers

HIPs may also have a superseded-by header indicating that a HIP has been rendered obsolete by a later document; the value is the number of the HIP that replaces the current document. The current document must change status to “Replaced” once the superseding HIP is changed to “Final” status. The newer HIP must have a replaces header containing the number of the HIP that it rendered obsolete.

### Linking to other HIPs

References to other HIPs should follow the format HIP-N where N is the HIP number you are referring to. Each HIP that is referenced in an HIP MUST be accompanied by a relative markdown link the first time it is referenced, and MAY be accompanied by a link on subsequent references. The link MUST always be done via relative paths so that the links work in this GitHub repository, forks of this repository, the main HIPs site, mirrors of the main HIP site, etc. For example, you would link to this HIP with [HIP-1](./hip-1.md).

### Auxiliary Files

Images, diagrams, and auxiliary files should be included in a subdirectory of the assets folder for that HIP as follows: assets/hip-N (where N is to be replaced with the HIP number). When linking to an image in the HIP, use relative links such as ../assets/hip-1/image.png.

## Reporting HIP Bugs, or Submitting HIP Updates

How you report a bug, or submit a HIP update depends on several factors, such as the maturity of the HIP, the preferences of the HIP author, and the nature of your comments. For early draft stages of the HIP, it’s probably best to send your comments and changes directly to the HIP author. For more mature, or finished HIPs you may want to submit corrections as a GitHub issue or GitHub pull request so that your changes don’t get lost.

When in doubt about where to send your changes, please check first with the HIP author and/or a HIP editor.

## Transferring HIP Ownership

It occasionally becomes necessary to transfer ownership of HIPs to a new champion. In general, it is preferable to retain the original author as a co-author of the transferred HP, but that’s really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the HIP process, or has fallen off the face of the ‘net. A bad reason to transfer ownership is because the author doesn’t agree with the direction of the HIP. One aim of the HIP process is to try to build consensus around a HIP, but if that’s not possible, an author can always submit a competing HIP.

If you are interested in assuming ownership of a HIP, you can also do this via pull request. Fork the HIP repository, make your ownership modification, and submit a pull request. You should mention both the original author and the HIP editors in a comment on the pull request. If the original author doesn’t respond in a timely manner, the HIP editors will make a unilateral decision.

## HIP Editor Responsibilities

For each new HIP that comes in, an editor does the following:

- Read the HIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don’t seem likely to get to Final status.
- The title should accurately describe the content.
- Check the HIP for language (spelling, grammar, sentence structure, etc.), markup (GitHub flavored Markdown), and code style.

    If the HIP isn’t ready, the editor will send it back to the author for revision, with specific instructions.

    Once the HIP is ready for the repository, the HIP editor will:
- Assign a HIP number (generally the PR number)
- Merge the corresponding pull request
- Send a message back to the HIP author with the next step.

Editors don’t pass judgement on the HIPs. We merely do the administrative & editorial part.

## Style Guide

When referring to a HIP by number, it should be written in the hyphenated form HIP-X where X i

## History

This document was derived from Bitcoin’s BIP-0001 written by Amir Taaki, Ethereum’s EIP-1 written by Martin Becze and Hudson Jameson, and Python’s PEP-0001 written by Barry Warsaw, Jeremy Hylton, David Goodger, and Nick Coghlan. In many places text was simply copied and modified. The authors of the text from which this document was derived are not responsible for this document's use in the Hedera Improvement Proposal process, and should not be bothered with technical questions specific to Hedera or the HIP.

## Copyright
This document is licensed under the Apache License, Version 2.0 -- see [LICENSE](../LICENSE) or (https://www.apache.org/licenses/LICENSE-2.0)
