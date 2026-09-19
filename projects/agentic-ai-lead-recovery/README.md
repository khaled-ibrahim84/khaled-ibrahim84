# Agentic AI Call Center / WhatsApp Lead Recovery

## Product brief

This concept uses a conversational AI agent to re-engage and qualify leads through messaging, with a path toward voice. The key product question is not simply what the model can say, but what it is allowed to decide and when it must hand control to a person.

**My role:** use-case framing, conversation workflow, guardrails, human handover and success measures. Integrations described here are conceptual.

## Target journey

Consent-based outreach → Identify intent → Ask approved qualification questions → Recommend next step → Book or record follow-up

At any point, low confidence, user request or policy boundaries trigger human handover with a concise context summary.

## Autonomy boundaries

| Agent may | Agent must not |
|---|---|
| Answer from approved knowledge | Invent product, price or eligibility information |
| Ask defined qualification questions | Infer sensitive attributes |
| Offer pre-approved next steps | Commit the business to unapproved terms |
| Capture stated preferences | Continue after opt-out |
| Summarize for a human | Hide uncertainty or failed tool calls |

## Handover triggers

- The user asks for a person.
- Intent, identity or language confidence is below threshold.
- A complaint, vulnerability signal or sensitive request appears.
- Negotiation leaves approved parameters.
- A required system is unavailable or returns inconsistent data.
- Repeated misunderstanding reaches the retry limit.

The handover package includes the user's stated goal, verified facts, unanswered questions, actions attempted and the precise reason for escalation.

## Conversation and tool controls

- Approved knowledge is versioned and attributable.
- System actions require typed inputs, permission checks and idempotency.
- Personally identifiable information is minimized and masked in logs.
- Prompts and policies are tested against multilingual and adversarial cases.
- Opt-out is immediate and persists across channels.
- Voice expansion requires explicit consent, disclosure and market-specific review.

## Acceptance criteria

- The agent identifies itself as automated.
- It never presents an unverified statement as confirmed.
- Every system action is visible in an audit trail.
- Handover preserves context without forcing the user to repeat the conversation.
- A failed action produces a safe explanation and recovery path.
- Quality evaluation includes Arabic and English scenarios.

## Success measures

- Qualified-lead and next-step conversion rates
- Human handover rate and reason distribution
- Opt-out and complaint rates
- Unsupported-answer rate
- Time to human response after escalation
- Evaluation pass rate across accuracy, policy and tone

## Non-goals

This case study does not claim a live WhatsApp or telephony deployment. It includes no phone numbers, conversation data, credentials, vendor configuration or employer playbooks.
