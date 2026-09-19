# Merchant Onboarding & KYB

## Product brief

A merchant onboarding journey must collect enough evidence for a defensible decision while remaining understandable and recoverable for the applicant. This concept separates data collection, verification, review, remediation and activation.

**My role:** journey design, product requirements, operating-model alignment and acceptance criteria.

## Design principles

- Ask only for information required for the merchant type and market.
- Explain why information is needed and what happens next.
- Save progress and preserve a clear application state.
- Separate automated checks from human decisions.
- Make missing or rejected evidence actionable.
- Record consent, declarations and decision history.

## Journey

Account and OTP → Business profile → Owners and UBOs → Documents → Declarations and consent → Automated checks → Operational review → Settlement and activation

Applications needing more evidence move to remediation and return to checks. Material or uncertain cases move to enhanced human review.

## Application states

DRAFT → SUBMITTED → CHECKS_IN_PROGRESS → ACTION_REQUIRED → UNDER_REVIEW → APPROVED → ACTIVATED

Exceptional states include REJECTED, WITHDRAWN and EXPIRED. Every transition has an allowed actor, reason and timestamp.

## Adaptive requirements

Requirements vary by legal form, operating market, regulated activity, ownership structure and expected payment activity. The interface presents the shortest valid path, while the rules service retains the rationale for each requested field or document.

## Review and exception controls

- Automated matches produce evidence, not unexplained final decisions.
- Potential matches route to trained reviewers with source and reason visible.
- Applicants receive specific remediation requests without exposing screening logic.
- Material changes after approval trigger risk-based re-review.
- Access to identity and ownership data follows least-privilege roles.

## Acceptance criteria

- The merchant can resume without losing completed steps.
- Required documents update when company type changes.
- A reviewer can identify the source and status of every check.
- A remediation request names the item, reason category and due date.
- Activation is impossible until mandatory review and settlement fields are complete.
- Consent and agreement versions remain retrievable.

## Success measures

- Start-to-submit conversion
- Median time to submit and time to decision
- First-time-right submission rate
- Manual review and remediation rates
- False-positive review rate
- Activation completion and early-life support contacts

## Non-goals

This is not legal advice or a complete jurisdictional compliance policy. It contains no real applicant information, screening configuration or vendor integration detail.
