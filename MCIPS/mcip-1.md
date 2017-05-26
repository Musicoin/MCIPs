    MCIP: 1
      Title: MCIP Purpose and Guidelines
      Status: Draft
      Type: Meta
      Author: Isaac Mao <im@berry.ai>
      Created: 2017-05-24

What is an MCIP?
--------------
This document describes the guidelines for MCIPs, adapted from MCIP1.

MCIP stands for Musicoin Improvement Proposal. An MCIP is a design document providing information to the Musicoin community, or describing a new feature for Musicoin or its processes or environment. The MCIP should provide a concise technical specification of the feature and a rationale for the feature. The MCIP author is responsible for building consensus within the community and documenting dissenting opinions.

MCIP Rationale
------------

We intend MCIPs to be the primary mechanisms for proposing new features, for collecting community input on an issue, and for documenting the design decisions that have gone into Musicoin. Because the MCIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For Musicoin implementers, MCIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the MCIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

MCIP Types
---------

There are three types of MCIP:

-   A **Standard Track MCIP** describes any change that affects most or all Musicoin implementations, such as a change to the the network protocol, a change in block or transaction validity rules, proposed application standards/conventions, or any change or addition that affects the interoperability of applications using Musicoin. Furthermore Standard MCIPs can be broken down into the following categories.
    -   **Core** - improvements requiring a consensus fork, as well as changes that are not necessarily consensus critical but may be relevant to “core dev” discussions.
    -   **Networking** - includes improvements to network protocol specifications of [whisper] and [swarm].
    -   **Interface** - includes improvements around client [API/RPC] specifications and standards.
    -   **Application** - application-level standards and conventions, including contract standards.

-   An **Informational MCIP** describes a Musicoin design issue, or provides general guidelines or information to the Musicoin community, but does not propose a new feature. Informational MCIPs do not necessarily represent Musicoin community consensus or a recommendation, so users and implementers are free to ignore Informational MCIPs or follow their advice.
-   A **Meta MCIP** describes a process surrounding Musicoin or proposes a change to (or an event in) a process. Process MCIPs are like Standards Track MCIPs but apply to areas other than the Musicoin protocol itself. They may propose an implementation, but not to Musicoin's codebase; they often require community consensus; unlike Informational MCIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in Musicoin development. Any meta-MCIP is also considered a Process MCIP.

MCIP Work Flow
-------------

The MCIP repository Collaborators change the MCIPs status. Please send all MCIP-related email to the MCIP Collaborators, which is listed under MCIP Editors below. Also see MCIP Editor Responsibilities & Workflow.

The MCIP process begins with a new idea for Musicoin. It is highly recommended that a single MCIP contain a single key proposal or new idea. The more focused the MCIP, the more successful it tends to be. A change to one client doesn't require an MCIP; a change that affects multiple clients, or defines a standard for multiple apps to use, does. The MCIP editor reserves the right to reject MCIP proposals if they appear too unfocused or too broad. If in doubt, split your MCIP into several well-focused ones.

Each MCIP must have a champion - someone who writes the MCIP using the style and format described below, shepherds the discussions in the appropriate forums, and attempts to build community consensus around the idea.

Vetting an idea publicly before going as far as writing an MCIP is meant to save the potential author time. Asking the Musicoin community first if an idea is original helps prevent too much time being spent on something that is guaranteed to be rejected based on prior discussions (searching the Internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where Musicoin is used. Examples of appropriate public forums to gauge interest around your MCIP include [the Musicoin subreddit], [the Issues section of this repository], and [one of the Musicoin Gitter chat rooms]. In particular, [the Issues section of this repository] is an excellent place to discuss your proposal with the community and start creating more formalized language around your MCIP.

Once the champion has asked the Musicoin community whether an idea has any chance of acceptance a draft MCIP should be presented as a [pull request]. This gives the author a chance to continuously edit the draft MCIP for proper formatting and quality. This also allows for further public comment and the author of the MCIP to address concerns about the proposal.

If the MCIP collaborators approve, the MCIP editor will assign the MCIP a number (generally the issue or PR number related to the MCIP), label it as Standards Track, Informational, or Meta, give it status “Draft”, and add it to the git repository. The MCIP editor will not unreasonably deny an MCIP. Reasons for denying MCIP status include duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the Musicoin philosophy.

Standards Track MCIPs consist of three parts, a design document, implementation, and finally if warranted an update to the [formal specification]. The MCIP should be reviewed and accepted before an implementation is begun, unless an implementation will aid people in studying the MCIP. Standards Track MCIPs must be implemented in at least three viable Musicoin clients before it can be considered Final.

For an MCIP to be accepted it must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

Once an MCIP has been accepted, the implementations must be completed. When the implementation is complete and accepted by the community, the status will be changed to “Final”.

An MCIP can also be assigned status “Deferred”. The MCIP author or editor can assign the MCIP this status when no progress is being made on the MCIP. Once an MCIP is deferred, the MCIP editor can re-assign it to draft status.

An MCIP can also be “Rejected”. Perhaps after all is said and done it was not a good idea. It is still important to have a record of this fact.

MCIPs can also be superseded by a different MCIP, rendering the original obsolete.

The possible paths of the status of MCIPs are as follows:

<img src=./mcip-1/process.png>

Some Informational and Process MCIPs may also have a status of “Active” if they are never meant to be completed. E.g. MCIP 1 (this MCIP).

What belongs in a successful MCIP?
---------------------------------

Each MCIP should have the following parts:

-   Preamble - RFC 822 style headers containing metadata about the MCIP, including the MCIP number, a short descriptive title (limited to a maximum of 44 characters), the names, and optionally the contact info for each author, etc.

<!-- -->

-   Simple Summary - “If you can’t explain it simply, you don’t understand it well enough.” Provide a simplified and layman-accessible explanation of the MCIP.

<!-- -->

-   Abstract - a short (~200 word) description of the technical issue being addressed.

<!-- -->

-   Motivation (*optional) - The motivation is critical for MCIPs that want to change the Musicoin protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the MCIP solves. MCIP submissions without sufficient motivation may be rejected outright.

<!-- -->

-   Specification - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Musicoin platforms (cpp-Musicoin, go-Musicoin, parity, MusicoinJ, Musicoinjs-lib, …).

<!-- -->

-   Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.

<!-- -->

-   Backwards Compatibility - All MCIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The MCIP must explain how the author proposes to deal with these incompatibilities. MCIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

<!-- -->

-   Test Cases - Test cases for an implementation are mandatory for MCIPs that are affecting consensus changes. Other MCIPs can choose to include links to test cases if applicable.

<!-- -->

-   Implementations - The implementations must be completed before any MCIP is given status “Final”, but it need not be completed before the MCIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of “rough consensus and running code” is still useful when it comes to resolving many discussions of API details.

MCIP Formats and Templates
-------------------------

MCIPs should be written in [markdown] format. Image files should be included in a subdirectory for that MCIP.

MCIP Header Preamble
-------------------

Each MCIP must begin with an RFC 822 style header preamble. The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

` MCIP: ` <MCIP number> (this is determined by the MCIP editor)

` Title: `<MCIP title>

` Author: `<list of author's real names and optionally, email address>

` * Discussions-To: ` <email address>

` Status: `<Draft | Active | Accepted | Deferred | Rejected | Withdrawn | Final | Superseded>

` Type: `<Standards Track (Core, Networking, Interface, ERC)  | Informational | Process>

` Created: `<date created on, in ISO 8601 (yyyy-mm-dd) format>

` * Replaces: `<MCIP number>

` * Superseded-By: `<MCIP number>

` * Resolution: `<url>

The Author header lists the names, and optionally the email addresses of all the authors/owners of the MCIP. The format of the Author header value must be

Random J. User &lt;address@dom.ain&gt;

if the email address is included, and

Random J. User

if the email address is not given.

Note: The Resolution header is required for Standards Track MCIPs only. It contains a URL that should point to an email message or other web resource where the pronouncement about the MCIP is made.

While an MCIP is in private discussions (usually during the initial Draft phase), a Discussions-To header will indicate the mailing list or URL where the MCIP is being discussed. No Discussions-To header is necessary if the MCIP is being discussed privately with the author.

The Type header specifies the type of MCIP: Standards Track, Meta, or Informational. If the track is Standards please include the subcategory (core, networking, interface, or ERC).

The Created header records the date that the MCIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

MCIPs may have a Requires header, indicating the MCIP numbers that this MCIP depends on.

MCIPs may also have a Superseded-By header indicating that an MCIP has been rendered obsolete by a later document; the value is the number of the MCIP that replaces the current document. The newer MCIP must have a Replaces header containing the number of the MCIP that it rendered obsolete.

Auxiliary Files
---------------

MCIPs may include auxiliary files such as diagrams. Such files must be named MCIP-XXXX-Y.ext, where “XXXX” is the MCIP number, “Y” is a serial number (starting at 1), and “ext” is replaced by the actual file extension (e.g. “png”).

Transferring MCIP Ownership
--------------------------

It occasionally becomes necessary to transfer ownership of MCIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred MCIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the MCIP process, or has fallen off the face of the 'net (i.e. is unreachable or not responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the MCIP. We try to build consensus around an MCIP, but if that's not possible, you can always submit a competing MCIP.

If you are interested in assuming ownership of an MCIP, send a message asking to take over, addressed to both the original author and the MCIP editor. If the original author doesn't respond to email in a timely manner, the MCIP editor will make a unilateral decision (it's not like such decisions can't be reversed :).

MCIP Editors
-----------

The current MCIP editors are

` * Isaac Mao (@isaac)`


MCIP Editor Responsibilities and Workflow
--------------------------------------

For each new MCIP that comes in, an editor does the following:

-   Read the MCIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to be accepted.
-   The title should accurately describe the content.
-   Edit the MCIP for language (spelling, grammar, sentence structure, etc.), markup (Github flavored Markdown), code style

If the MCIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the MCIP is ready for the repository, the MCIP editor will:

-   Assign an MCIP number (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this MCIP)

<!-- -->

-   Accept the corresponding pull request

<!-- -->

-   List the MCIP in [README.md]

<!-- -->

-   Send a message back to the MCIP author with next step.

Many MCIPs are written and maintained by developers with write access to the Musicoin codebase. The MCIP editors monitor MCIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on MCIPs. We merely do the administrative & editorial part.

History
-------

This document was derived heavily from [Bitcoin's BIP-0001] written by Amir Taaki which in turn was derived from [Python's PEP-0001]. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Musicoin Improvement Process, and should not be bothered with technical questions specific to Musicoin or the MCIP. Please direct all comments to the MCIP editors.

May 21, 2017: MCIP 1 was put in place and ready to serve future evolution.
