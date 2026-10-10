# Prompt Management — One-Page Pricing Strategy

**Product:** Prompt Management platform (versioning, environments, evaluation, deployment and observability for LLM prompts)
**Author:** Bob Keaveney · **Date:** 2026-10-10 · **Status:** Draft for review

## 1. Pricing principle

Price on the value we create, not on the team size we happen to see. Prompt management pays for itself by reducing bad releases and
model spend. The pricing should therefore scale with **how much production traffic runs through managed prompts**, with a small
per-seat component to monetize collaboration. Headline rule: **cheap to start, predictable to budget, expensive only when the
customer is clearly winning.**

## 2. Value metric

| Metric | Role | Why |
|---|---|---|
| **Managed prompt requests / month** (a prompt fetched or logged at runtime) | Primary usage metric | Tracks production value directly, grows with the customer, easy to meter |
| **Editor seats** | Secondary, paid tiers only | Monetizes collaboration (reviews, approvals, A/B tests) without punishing viewers |
| Prompts, environments, retention, SSO, audit | Packaging fences | Differentiate tiers without creating usage anxiety |

Viewers and API-only service accounts are always free. Overage is billed at a published rate, never cut off mid-month.

## 3. Tiers

| | **Free** | **Team** | **Business** | **Enterprise** |
|---|---|---|---|---|
| Price | $0 | **$49 / mo** + $15 / editor | **$299 / mo** + $25 / editor | From **$2,000 / mo**, annual |
| Included requests | 5,000 / mo | 100,000 / mo | 1,000,000 / mo | Custom, committed volume |
| Overage | n/a (hard stop) | $0.60 per 1,000 | $0.40 per 1,000 | $0.20–0.30 per 1,000, tiered |
| Editors included | 2 | 3 | 10 | Unlimited |
| Prompts / environments | 20 / 1 | Unlimited / 3 | Unlimited / unlimited | Unlimited |
| Retention | 14 days | 90 days | 1 year | Custom |
| Evaluations | Manual only | Datasets + batch evals | Online evals, A/B routing | + custom model judges |
| Security | — | — | SSO, RBAC, audit log | SCIM, BAA, VPC / self-host, SLA |
| Support | Community | Email | Priority + Slack | Named engineer, 99.9 % SLA |

**Why these points:** $49 undercuts the per-request plans and sits above Langfuse Core ($29) with more collaboration value. $299 is
the "one credit-card approval" ceiling for an engineering manager and matches the Braintrust Pro / PromptLayer Team price band.
The Enterprise floor is set by security and compliance scope, not by volume, so the sales team never discounts into Business territory.

## 4. Competitive anchors (public list prices, Oct 2026)

| Vendor | Model | Entry paid | Mid tier |
|---|---|---|---|
| Langfuse Cloud | Usage (units), no seats | $29 / mo | $199 / mo; Enterprise $2,499 / mo |
| PromptLayer | Flat + per-request | $49 / mo | ~$299–500 / mo |
| PromptHub | Per seat + requests | ~$12 / mo | ~$20 / user / mo |
| Braintrust | Flat, usage-driven | $249 / mo | Custom |

Positioning: **"Langfuse-level price, PromptLayer-level prompt workflow, enterprise controls without the $2.5k floor."**

## 5. Packaging and discount rules

- **Annual billing:** 2 months free (≈17 %). No other standing discounts below Enterprise.
- **Enterprise:** committed-volume tiers with a yearly true-up; up to 20 % discount for 2-year terms, approval required beyond that.
- **Startups / OSS / education:** Team plan free for 12 months, capped at 500k requests. Converts to paid automatically.
- **Upgrade triggers (in-product):** hitting 80 % of included requests, needing a third environment, requesting SSO. Each shows the price delta, not the full plan page.
- **Grandfathering:** price changes apply to existing customers after 12 months, with a 90-day notice.

## 6. Targets and guardrails

| Metric | Target (12 months) |
|---|---|
| Free → Team conversion | ≥ 4 % of active free workspaces |
| Team → Business expansion | ≥ 20 % within the first year |
| Net revenue retention | ≥ 115 % |
| Gross margin on overage | ≥ 80 % (metering and storage cost ≤ $0.08 per 1,000 requests) |
| Usage share of revenue | 35–50 % (keeps revenue predictable while still expanding with customers) |

Review prices quarterly against overage margin and conversion. Change list prices at most once per year.

## 7. Open questions

1. Should evaluation runs be a second metered unit, or stay bundled into requests? Recommend bundled for the first year to keep the bill simple.
2. Self-hosted Business tier: license fee vs. requiring Enterprise. Recommend Enterprise only until demand is proven.
3. Marketplace listings (AWS, Azure) for Enterprise procurement: target Q2 next year.
