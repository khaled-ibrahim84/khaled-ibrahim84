# Unified Payments & Payouts Orchestration Simulator

## Product brief

Merchants want one predictable integration even when processing spans multiple providers, payment methods and markets. This simulator specification shows the product contracts needed to make routing, state changes, webhooks, reconciliation and settlement understandable.

**My role:** product architecture, journey and state modelling, API-oriented requirements and operational controls. This is a conceptual simulator, not a production processor.

## Payment journey

Create → Validate → Risk and compliance → Route → Provider → Authorize → Webhook → Reconcile → Settle

## Merchant-facing contract

A create request uses a merchant reference, amount, currency, payment method, return endpoints and an idempotency key. The platform returns its own payment identifier and current status. Provider-specific detail remains available for support, but does not leak into the core merchant contract.

## State model

CREATED → VALIDATING → PROCESSING → AUTHORIZED → CAPTURED → SETTLED

Alternative outcomes include REQUIRES_ACTION, DECLINED, FAILED, CANCELLED, PARTIALLY_REFUNDED and REFUNDED. Provider events are translated into this canonical model with the raw source retained for traceability.

## Routing inputs

- Market, currency and payment method support
- Merchant configuration and contractual eligibility
- Provider health and latency
- Cost and authorization performance
- Risk or compliance constraints
- Transaction history and retry safety

Routing must be explainable after the event. A retry never creates a second financial instruction unless the prior outcome is conclusively safe.

## Webhook controls

- Signed messages and timestamp validation
- Unique event identifiers and deduplication
- At-least-once delivery with backoff
- Out-of-order event handling
- Replay capability for authorized operators
- Merchant-visible delivery status and correlation identifiers

## Reconciliation and settlement

The platform compares internal instructions, provider reports and settlement movements. Differences become owned exceptions with reason categories, age and evidence. Operational dashboards distinguish processing status from settlement status.

## Acceptance criteria

- Repeating an idempotent create request returns the original result.
- Every external status maps to one documented canonical state.
- Routing decisions record the evaluated rules and selected provider.
- Duplicate or out-of-order webhooks do not regress payment state.
- Support can trace a payment across platform and provider identifiers.
- Reconciliation exceptions have an owner and resolution history.

## Success measures

- Authorization rate by route and payment method
- Provider latency and availability
- Duplicate-processing incidents
- Webhook delivery success and delay
- Unreconciled value and exception age
- Settlement timeliness and merchant support contacts

## Non-goals

This repository does not process money, connect to a provider or contain real API credentials, endpoints, merchant data or routing thresholds.
