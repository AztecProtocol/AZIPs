| azip | title | description | author | discussions-to | status | category | created |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  | AZIP Process and Guidelines | A process to specify and update the Aztec protocol. | Josh Crites (@critesjosh), Charlie Lye (@charlielye) | https://discourse.aztec.network/t/proposal-aztec-improvement-proposal-azip-process/289 | Idea | Informational | 2023-06-02 |

## Abstract

AZIP stands for Aztec Improvement Proposal. An AZIP is a design document providing information to the Aztec community, or describing a new feature for Aztec or its processes or environment. AZIPs are tracked in a dedicated GitHub repository and are considered the source of truth for protocol features and standards. When relevant, an AZIP should provide a concise technical specification of the feature and a rationale for the feature. The AZIP author is responsible for building consensus within the community and documenting dissenting opinions. 

## AZIP Rationale

We intend AZIPs to be the primary mechanisms for proposing new features, for collecting community technical input on an issue, and for documenting the design decisions that have gone into Aztec. Because the AZIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For Aztec implementers, AZIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer will list the AZIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

We lean heavily on copying how Ethereum manages its EIPs, but instead adopt the name of AZIPs, or AZtec Improvement Proposals.

## AZIP Status Terms and Flow

A successful AZIP will move through the following stages on its way to finalization: 

Idea &rarr; Draft &rarr; Review &rarr; Final

An AZIP may be moved to `Cancelled` at any point after it has been accepted as `Draft`.

The AZIPs status does not enforce when development of a particular piece of work should begin, for example work may start as soon as drafted, but the work is heavily subject to change. Aztec engineers will likely be developing a reference implementation of the system, before an AZIP reaches `Final` status. External developers working on their own implemenatations, will likely wait for finality.

- **Idea** - An idea that is pre-draft. This is not tracked within the AZIP Repository and will be proposed, discussed and tracked in the [Aztec forum](https://discourse.aztec.network), most likely in the [Aztec Category](https://discourse.aztec.network/c/aztec/5).
- **Draft** - The first formally tracked stage of an AZIP in development. An AZIP is merged by an AZIP Editor into the AZIP repository when properly formatted. An AZIP will be assigned a number by an Editor once it has been accepted as `Draft`.
- **Review** - An AZIP Author marks an AZIP as ready for and requesting Peer Review. An AZIP must have clear buy-in from the community and should be well-specified before moving to `Final`. If a code change is needed, an implementation should be provided.
- **Final** - This AZIP represents the final standard. A `Final` AZIP exists in a state of finality and should only be updated to correct errata and add non-normative clarifications. An AZIP marked `Final` may be updated by a future AZIP.
- **Cancelled** - The AZIP author(s) or editors have cancelled the proposed AZIP. This state has finality and can no longer be resurrected using this AZIP number. If the idea is pursued at later date it is considered a new proposal.


## AZIP Categories

1. **Informational** - Provide general guidelines or information to the Aztec community, but does not propose a new feature. Includes high level descriptions of the system, architecture, etc.
2. **Core** - Core System AZIPs, including improvements to e.g. Public, Private, Sequencer and Prover clients, networking protocols or client API/RPC interfaces.
3. **Standards** - application layer AZIPs, e.g. defining standards for contracts written in Noir etc.

## What belongs in a successful AZIP?

Each AZIP should have the following parts:

- **Preamble** - Headers containing metadata about the AZIP, including the AZIP number, a short descriptive title (limited to a maximum of 44 characters), a description (limited to a maximum of 140 characters), and the author details. Irrespective of the category, the title and description should not include AZIP number. See below for details.
- **Abstract** - Abstract is a multi-sentence (short paragraph) technical summary. This should be a very terse and human-readable version of the specification section. Someone should be able to read only the abstract to get the gist of what this specification does.
- **Motivation** (optional) - A motivation section is critical for AZIPs that want to change the protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the EIP solves. This section may be omitted if the motivation is evident.
- **Specification** (required for `Core` and `Standards` AZIPs) - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations.
- **Rationale** - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale should discuss important objections or concerns raised during discussion around the AZIP.
- **Backwards Compatibility** (optional) - All AZIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their consequences. The AZIP must explain how the author proposes to deal with these incompatibilities. This section may be omitted if the proposal does not introduce any backwards incompatibilities, but this section must be included if backward incompatibilities exist.
- **Test Cases** (optional) - Tests should either be inlined in the AZIP as data (such as input/expected output pairs, or included in `../assets/azip-###/<filename>`.
- **Reference Implementation** (optional) - An optional section that contains a reference/example implementation that people can use to assist in understanding or implementing this specification. This section may be omitted for all AZIPs.
- **Security Considerations** (required for `Core` and `Standards` AZIPs) - All `Core` and `Standards` AZIPs must contain a section that discusses the security implications/considerations relevant to the proposed change. Include information that might be important for security discussions, surfaces risks and can be used throughout the life-cycle of the proposal. E.g. include security-relevant design decisions, concerns, important discussions, implementation-specific guidance and pitfalls, an outline of threats and risks and how they are being addressed. AZIP submissions missing the “Security Considerations” section will be rejected. An AZIP cannot proceed to status `Final` without a Security Considerations discussion deemed sufficient by the reviewers.
- **Copyright Waiver** - All AZIPs must be in the public domain. The copyright waiver MUST link to the license file and use the following wording: `Copyright and related rights waived via [CC0](/LICENSE).`

## AZIP Formats and Templates

AZIPs should be written in [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) format. There is a [template](/a8Pyfd-pTuW_LM8rtzvjqw) to follow.

## AZIP Header Preamble

Each AZIP must begin with a header preamble. The headers must appear in the following order.

|||
| -------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `azip`               | AZIP number (this is determined by the AZIP Editor when it is accepted as a Draft).                                                                      |
| `title`              | The AZIP title is a few words, not a complete sentence.                                                                   |
| `description`        | Description is one full (short) sentence.                                                                                 |
| `author`             | Comma separated list of the author's. Example: `FirstName LastName (@GitHubUsername)`, `FirstName LastName <foo@bar.com>` |
| `discussions-to`     | The URL pointing to the official discussion thread in the [Aztec forum](https://discourse.aztec.network).                                                                       |
| `status`             | `Draft`, `Review`, `Final`, or `Cancelled`                                             |
| `category`           | `Informational`, `Core`, or `Standards`                                    |
| `created`            | Date created on, in ISO 8601 (yyyy-mm-dd) format.                                                                         |

Headers that permit lists must separate elements with commas.

Headers requiring dates will always do so in the format of ISO 8601 (yyyy-mm-dd).

### `author` header

The `author` header lists the names, email addresses or usernames of the authors/owners of the AZIP. Those who prefer anonymity may use a username only, or a first name and a username. The format of the `author` header value must be:

> Random J. User &lt;address@dom.ain&gt;

or

> Random J. User (@username)

if the email address or GitHub username is included, and

> Random J. User

if the email address is not given.

It is not possible to use both an email and a GitHub username at the same time. If important to include both, one could include their name twice, once with the GitHub username, and once with the email.

At least one author must use a GitHub username, in order to get notified on change requests and have the capability to approve or reject them.

### `discussions-to` header

While an AZIP is a draft, a `discussions-to` header will indicate the URL where the AZIP is being discussed (in the [Aztec forum](https://discourse.aztec.network)).

## Linking to External Resources

Links to external resources **SHOULD NOT** be included. External resources may disappear, move, or change unexpectedly.

## Linking to other AZIPs

References to other AZIPs should follow the format `AZIP-N` where `N` is the AZIP number you are referring to. Each AZIP that is referenced in an AZIP **MUST** be accompanied by a relative markdown link the first time it is referenced, and **MAY** be accompanied by a link on subsequent references. The link **MUST** always be done via relative paths so that the links work in the GitHub repository, forks of this repository, the main AZIPs site, mirrors of the main AZIP site, etc.

## Auxiliary Files

Images, diagrams and auxiliary files should be included in a subdirectory of the `assets` folder for that AZIP as follows: `assets/azip-N` (where **N** is to be replaced with the AZIP number). When linking to an image in the AZIP, use relative links such as `../assets/azip-1/image.png`.

## Transferring AZIP Ownership

It occasionally becomes necessary to transfer ownership of AZIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred AZIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the AZIP process, or has fallen off the face of the 'net (i.e. is unreachable or isn't responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the AZIP. We try to build consensus around an AZIP, but if that's not possible, you can always submit a competing AZIP.

If you are interested in assuming ownership of an AZIP, send a message asking to take over, addressed to both the original author and the AZIP editor. If the original author doesn't respond to the email in a timely manner, the AZIP editor will make a unilateral decision.

## AZIP Editors

The current AZIP editors are:

- Charlie Lye (@charlielye)
- Michael Connor (@iAmMichaelConnor)
- Zac Williamson (@zac-williamson)
- Josh Crites (@critesjosh)
- Joe Andrews (@joeandrews)

## AZIP Editor Responsibilities

For each new AZIP that comes in, an editor does the following:

- Read the AZIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to get to final status.
- The title should accurately describe the content.
- Check the AZIP for language (spelling, grammar, sentence structure, etc.), markup (GitHub flavored Markdown), code style.

If the AZIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the AZIP is ready for the repository, the AZIP editor will:

- Assign an AZIP number (generally the PR number, but the decision is with the editors)
- Merge the corresponding pull request
- Send a message back to the AZIP author with the next step.

Many AZIPs are written and maintained by developers with write access to the Aztec codebase. The AZIP editors monitor AZIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

## Style Guide

### Titles

The `title` field in the preamble:

- Should not include the word "standard" or any variation thereof; and
- Should not include the AZIP's number.

### Descriptions

The `description` field in the preamble:

- Should not include the word "standard" or any variation thereof; and
- Should not include the AZIP's number.

### AZIP numbers

When referring to an AZIP by number, it should be written in the hyphenated form `AZIP-X` where `X` is the AZIP's assigned number.

### RFC 2119 and RFC 8174

AZIPs are encouraged to follow [RFC 2119](https://www.ietf.org/rfc/rfc2119.html) and [RFC 8174](https://www.ietf.org/rfc/rfc8174.html) for terminology and to insert the following at the beginning of the Specification section:

> The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as  described in RFC 2119 and RFC 8174.

## History

This document was derived heavily from [Ethereums EIP-001](https://eips.ethereum.org/EIPS/eip-1), which in turn was derived from [Bitcoin's BIP-0001](https://github.com/bitcoin/bips) written by Amir Taaki which in turn was derived from [Python's PEP-0001](https://peps.python.org/). In many places text was simply copied and modified. Do not bother the authors of these ancestor works with technical questions specific to Aztec or the AZIP. Please direct all comments to the AZIP editors.

## Copyright

Copyright and related rights waived via CC0.
