# CrawlBeast - Systems & Webhook Automation

To transition CrawlBeast from a simple report checker into **Programmable SEO Infrastructure**, we enable webhook triggers that users can plug into automated pipelines (n8n, Zapier, or custom cron scripts).

## 1. Webhook Trigger Schema
Configure the CrawlBeast crawling backend to send a `POST` request to the user's endpoint immediately upon crawl completion.

### POST Payload Example:
```json
{
  "event": "crawl.completed",
  "timestamp": "2026-06-04T12:00:00Z",
  "project_id": "proj_cb_987",
  "domain": "https://example.com",
  "summary": {
    "total_urls": 482,
    "status": "failed",
    "critical_errors": 14,
    "high_errors": 8
  },
  "critical_broken_links": [
    {
      "broken_url": "https://example.com/broken-page",
      "status_code": 404,
      "found_on_sources": [
        "https://example.com/blog/seo-tips",
        "https://example.com/about"
      ]
    }
  ]
}
```

## 2. Recommended Integration Pipeline (n8n / Zapier)
Outline the step-by-step guide for developers to auto-remediate issues:
1. **Trigger**: CrawlBeast sends the webhook payload when a crawl completes.
2. **Filter**: The pipeline checks if `critical_errors > 0`.
3. **Action (Ticket Creation)**: Create a task in Jira/Linear assigning the developer to fix the link graph broken connections, outputting the exact source pages.
4. **Action (Auto-Fix fallback)**: If the broken link matches a redirect rule, trigger a script on the host server to auto-update the DB link references.
