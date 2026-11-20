# Public Launch Requirements

This file records requirements that must be met before the first public release of the Oikumene Works service.

## Feedback and correction channel

**Status:** Accepted requirement (2026-11-20)

The first public release must provide an easy way to send feedback and corrections without creating an account.

The minimum public interface should include:

- a visible project email address, initially planned as `feedback@oikumene.works`;
- a simple feedback form available from every independent question unit and from the general site navigation;
- a required message field and an optional reply email address;
- an automatically included page/question identifier and interface language;
- a short privacy notice asking users not to include sensitive personal information;
- a clear success or failure response after submission;
- basic spam and abuse protection;
- a direct email link as a fallback if the form cannot be used.

The form should not require a user account. It should not include the player's selected theological answer by default. If that context is ever offered, the user must choose explicitly to include it.

The initial implementation should remain lightweight. A serverless endpoint may validate the submission and forward it privately to the project maintainer's inbox without introducing a user database or persistent public feedback store.

The exact hosting and mail-delivery implementation remains open until the Oikumene Works site is built.
