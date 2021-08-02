# Boa RFCs

## What is an RFC?

A **R**equest **F**or **C**omments (RFC) is a proposal to change some aspect of Boa, for example by adding or removing a feature. It allows the team and the community to discuss the proposal and modify it before being accepted

Things like bug fixes and documentation improvements can be handled through regular GitHub pull requests, and do not need an RFC.

## Lifecycle of an RFC

RFCs have four stages:

- **Pending:** The RFC has been submitted as a PR.
- **Active:** The RFC PR has been merged and will be implemented.
- **Landed:** The proposed changes in the RFC have been shipped in a release.
- **Rejected:** The RFC PR has been closed.

## When to follow this process

You should create an RFC if you want to make a substantial change to the Boa ecosystem. This is not set in stone, and evolves with community norms. Substantial changes include, but is not limited to:

- Semantic or syntactic change to the language that is not a bugfix.
- Removing a feature.
- Adding a new module to the standard library.
- Substantially modifying an existing module in the standard library.

Some changes do not require an RFC:

- Modifications that do not impact behavior (refactoring, reorganizing, etc.)
- Additions that improve strictly objective, numeric criteria, such as:
	- Getting rid of warnings during compilation.
	- Speed improvements.
	- Better platform support.
- Additions that are invisible to end users of Boa.
- Bug fixes

## The process

Note: Your RFC will be licensed under the MIT license, found in the `LICENSE` file. If you are uncomfortable with this, you may turn around now.

1. Discuss your proposal in our [Discord server](https://discord.gg/42Mj2hbshu). This will help you see if your change is desired. If there is interest, continue.
2. Create your RFC.
	- Create a new branch, or fork the repo.
	- Copy `0000-template` to `active-rfcs/0000-my-feature.md`, replacing `my-feature` with a name for your RFC. Don't assign a number just yet, we will do that once the PR is merged.
	- Write your RFC. Put care into this step. If you're unmotivated, show a lack of understanding, or are disingenuous about drawbacks or alternatives, your RFC is more likely to be rejected. Feel free to read existing active RFCs to gain a better understanding of what is expected.
	- Once you're done, submit a pull request outlining the basics of your proposal.
	- Now that you've made a pull request, add a link to it at the top of the RFC.
3. Receive feedback.
	- You can modify your RFC based on feedback from the team and the community, and the team may request changes.
	- Once the team feels the RFC has been discussed thoroughly and that any appropriate changes have been made, a member may merge the PR and assign a number. The PR may also be closed if the RFC is deemed undesired.

## Active RFCs

Once an RFC becomes active, it may be implemented through a pull request. Becoming active does not say anything about the priority of the RFC, or whether anyone is currently working on it.

Modifications to active RFCs can be done through followup PRs. We strive to write each RFC such that it reflects the final design of the feature, however, new ideas and such may come up that warrant changing an RFC.

## Implementing an RFC

The author of an RFC is not obligated to implement it. Of course, they are welcome to, as is any other developer, once the RFC has been accepted.

An active RFC should have a link to its implementation PR if there is one. Feedback to the actual implementation should be given within this PR, rather than the RFC PR.

If you want to implement an RFC, but are unsure about whether or not someone is already working on it, you may ask in the RFC PR, though please check if someone has already asked and gotten an answer first.

## Reviewing RFCs

Members of the team may use GitHub's review feature to request changes, or approve the PR to signal that they believe the PR is ready to be accepted.

Once a team member decides to merge the PR, they should squash and merge so that the whole PR will become one commit, ensuring a clean commit history.

## Acknowledgements

This RFC process is heavily inspired by and based on that of [Vue](https://github.com/vuejs/rfcs) and [Rust](https://github.com/rust-lang/rfcs).