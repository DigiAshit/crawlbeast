# CrawlBeast - Pricing & Revenue Model

## 1. Target B2B Pricing Strategy
To attract high-commitment prosumers (growth engineers and technical SEO agencies) and minimize support costs, we implement a B2B pricing plan:
- **Price Point**: **$49 per month** (or $399 billed annually for a 30% discount).
- **Core Value Metric**: Number of crawled URLs per month.
- **Plan Limits**:
  - **Free Tier (Gated)**: Up to 100 URLs per crawl. Requires a credit card to activate the trial.
  - **Pro Tier ($49/mo)**: Up to 10,000 URLs per crawl. Priority queue processing.
  - **Agency Tier ($99/mo)**: Unlimited concurrent crawling, custom webhook integrations, and API access.

## 2. Gated Free Trial Integration
- **Stripe Setup**: Configure Stripe Billing to require a credit card upfront for the 7-day free trial.
- **Churn Reduction**: If a user cancels during their trial, prompt them with a 1-question cancellation survey (JTBD-aligned) to capture pushes/anxieties.

## 3. Financial Metrics & Upsell Triggers
- **SaaS Metric Targets**:
  - **LTV / CAC**: Target $> 3$.
  - **Cohort Churn**: Target $< 8\%$. If churn rises above 8%, freeze traffic campaigns and review crawl failure logs.
- **In-App Upsell Trigger**:
  - Track url consumption in the crawl log.
  - Display a warning modal when a user reaches **80% of their URL limits** (e.g. at 8,000 URLs crawled on the Pro plan).
  - Block new crawls at 100% and redirect to Stripe checkout for the Agency tier.
