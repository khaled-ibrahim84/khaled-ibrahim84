# Merchant Pricing Configuration

## Product brief

Payment pricing often begins as commercial language but must end as deterministic system behaviour. This concept turns percentage, flat, hybrid and tiered pricing into rules that can be simulated, approved, activated and audited.

**My role:** product framing, workflow design, rule modelling and acceptance criteria. This demonstrates product and technical collaboration, not production software engineering.

## Users and needs

| User | Need |
|---|---|
| Commercial | Configure an agreed offer without ambiguous interpretation |
| Finance | Validate fees, tax treatment and expected revenue |
| Operations | Activate changes safely and resolve exceptions |
| Engineering | Receive explicit, testable rules and edge cases |
| Audit/Risk | Trace who changed what, why and when |

## Rule model

A pricing rule contains a market, currency, transaction type, channel, payment method, fee model, value, optional tiers and caps, tax treatment, effective period and status. Scope precedence must be explicit.

Supported models include percentage, flat, hybrid and tiered fees; minimum and maximum bounds; and market-defined tax treatment.

## Controlled lifecycle

Draft → Simulated → Submitted for review → Scheduled → Live → Expired or superseded

No draft changes a live merchant price. Activation requires effective dates, an approver distinct from the editor, and an immutable audit record.

## Example simulation

Illustrative inputs only:

| Input | Value |
|---|---:|
| Transaction amount | 1,000.00 |
| Percentage rate | 1.50% |
| Flat component | 0.50 |
| Minimum / maximum | 1.00 / 30.00 |
| Calculated fee before tax | 15.50 |

The simulator should show the matching rule, each calculation step, rounding behaviour and the final result before activation.

## Acceptance criteria

- A user can see which rule matched and why.
- Overlapping rules are rejected or resolved by documented precedence.
- A change cannot be backdated once transactions exist for the period.
- Simulation covers boundary values, refunds and zero or negative adjustments.
- Activation records editor, approver, timestamp and reason.
- Existing transactions retain the pricing version used at processing time.

## Success measures

- Pricing setup lead time
- Configurations returned for correction
- Billing disputes linked to configuration
- Manual overrides and emergency changes
- Time required to explain a charged fee

## Delivery approach

Start with one market, currency and transaction family. Validate the model against representative agreements, run finance-led simulations, then add tiering and market-specific tax rules. Integrations should use versioned contracts and idempotent change requests.

## Non-goals

This case study does not define accounting policy, disclose real commercial rates or reproduce an employer platform.
