# CrawlBeast - Month 2 Product Skeleton Gate & Roadmap

## 1. Single Workflow Definition
CrawlBeast's core workflow is defined as:
**Input a target website URL $\rightarrow$ Concurrently crawl all pages $\rightarrow$ Map the internal link graph $\rightarrow$ Output broken link relationship trace details (what URL is broken and exactly what page it is found on).**

No advanced dashboards, onboarding, or custom profiles are included in the skeleton.

## 2. Month 2 Skeleton "Use Twice" Gate Audit
To unlock further feature development, we must track and confirm user engagement on the core workflow:
- **Rule**: At least **5 target testers** must run a website crawl and export link graph trace results at least **two separate times** in Month 2.

### Tracking Log Template:
| Tester ID | First Run Date | Second Run Date | Core Workflow Successful? | Tester Feedback |
|---|---|---|---|---|
| #01 | | | | |
| #02 | | | | |
| #03 | | | | |
| #04 | | | | |
| #05 | | | | |

*If WAU cohort churn exceeds 8% during this audit, freeze growth marketing campaigns and prioritize speed optimization and crawling fixes.*

## 3. Product Roadmap (Bridging to Programmable SEO)
Once the Skeleton Gate is passed, the builder is authorized to build the following three features to transition CrawlBeast from "another audit tool" to "SEO Infrastructure":
1. **Scheduled Crawling**: Enable users to schedule automated crawls (daily/weekly) to support continuous detection.
2. **Webhook Triggers**: Send a JSON payload to a user-configured URL (e.g., n8n, Zapier) when a crawl finishes and detects critical issues.
3. **Fix Context**: Output clear developer-grade explanations detailing *why* an issue matters and *where* in the source code it needs to be fixed.
