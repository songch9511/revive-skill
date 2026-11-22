# Phase 3 — First payment path

Plan the shortest route to one payment from a stranger. Everything here is planning; the execution layer is still off.

## What the path contains

Write these into `state.md`.

- **What is sold.** One sentence, in English, saying what the customer gets. One customer group, English-speaking.
- **Price and payment method.** Price in US dollars. Start from the fastest method that can take money (see Payment rules below).
- **Minimum scope.** List what is needed for one payment, then list what is explicitly cut. Use `architecture.md`: every node not on the path to payment is a candidate to cut. Writing the cut list down matters, because unlisted features come back.
- **First customer candidates.** Specific people and specific places where the target customers already gather. "Post on social media" is not specific; a named community or ten named people is. Revive does not prescribe launch channels: pick them with the user from where their customers actually are.
- **Milestones.** Three to five, each with a finish condition and a target date.
  - The first milestone is the payment account application and a payment link. Approval takes time that you do not control, so it starts first.
  - The second is the demand test below, with a go/no-go date.
  - Building anything beyond what the payment link needs comes after the go/no-go.

## Check demand before building more

The agent's own optimism is not evidence, and neither is the user's. Demand is checked in two parts, because a payment link cannot exist until the user has a payment account.

**In this phase, before the path is approved:**

1. Search the product name and its main keywords. Record any existing product with the same name or the same promise.
2. Do not count the number of competitors as proof of demand.
3. Name the first people to contact. A path with no named candidates is not ready for approval.

**As the second milestone, before building more:**

4. Confirm willingness to pay in the cheapest way available. The default is a single payment link shown to real candidates before the product is finished.
5. Get the first ten customers by hand: direct contact, not broadcast. Write what they say, word for word, into `state.md` under customer quotes. Those sentences become the landing page copy later, and they are better than anything written from imagination.
6. On the go/no-go date, look at what came back. If nobody was willing to pay, say so plainly, set the execution layer to off and return to Phase 2. A changed verdict now is cheaper than a launch to no one.

## Payment rules

Revive assumes a seller on the global, US-baseline market.

### Default: Stripe

Start with a payment link, which needs no code. Integrate a checkout only when the product needs it (accounts that must be tied to a payment, for example).

### Alternative: a merchant of record

A merchant of record sells on the user's behalf and handles sales tax. Use this path when the user cannot open a Stripe account or wants the provider to handle tax. Consider Polar first, then Paddle.

### Order of questions

1. Ask the user whether they can open a Stripe account.
2. If not, go to the merchant-of-record path.
3. If that fails too, mention Freemius and Stripe Managed Payments as options, and say that Revive has not verified either.
4. If nothing fits, say this is outside what Revive covers and let the user choose their own payment method.
5. Record the answers and the chosen path in `state.md`.

### Cautions for the merchant-of-record path

Every merchant of record has reports of rejected applications and delayed payouts.

- Apply early. This is why the application belongs in the first milestone.
- A finished integration does not mean payments are ready. It is confirmed when the first payout arrives.

### What Revive does not do

- It does not open accounts, pass identity checks or connect payout bank accounts. Prepare what is needed and hand these to the user.
- It does not give tax advice. Explain that on Stripe the seller handles sales tax and on a merchant of record the provider does, and stop there.
- It does not cover country-specific payment processes outside these defaults. Users who need them arrange that themselves.

### Providers not offered

- **Lemon Squeezy:** scheduled to shut down.
- **Dodo:** on hold; there is a user report of a balance being held and then kept.
- **Creem:** on hold; almost no user evidence, and one report of it being invite-only.

### Skills

Use the provider's official skill when one is installed. These are not bundled with Revive because copies go stale quickly. `execution.md` has the routing and the install-offer rules. With no skill, read the provider's official documentation before implementing.

## Gate

The user approves the path. Record the approval, set the execution layer to on in `state.md`, and move to Phase 4.
