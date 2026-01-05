
# Automate Customer Feedback Classification with AI, Google Sheets, and Slack Alerts

This workflow automates the process of collecting customer feedback from forms and emails, analyzes it using AI, classifies it by category and sentiment, logs it into Google Sheets, and routes it to the right communication channels like Slack or email.

It closes the feedback loop efficiently by ensuring every review is categorized, tracked, and acted upon.

---

## Who’s It For

* Product managers wanting structured customer insights
* Customer support teams needing fast issue routing
* Engineering teams who want to be alerted to bugs quickly
* Growth & UX teams tracking feature requests and usability feedback
* Any business managing customer feedback at scale

---

## How It Works

1. **Form Submission Trigger**
   Captures reviews submitted via customer feedback or review forms.

2. **Gmail Trigger**
   Listens for new feedback emails in a specified inbox or label.

3. **Extract Details (Code Node)**
   Parses sender details and extracts the actual review text.

4. **AI Node (LLM)**

   * Summarizes feedback
   * Detects sentiment (Positive / Neutral / Negative)
   * Classifies feedback (Bug, Feature Request, UX Issue, Other)

5. **Google Gemini (Optional)**
   Provides advanced classification or summarization if enabled.

6. **Google Sheets Node**
   Logs structured feedback for tracking and reporting.

7. **Switch Node**
   Routes feedback into different flows based on category.

8. **Slack Node**
   Instantly notifies teams about critical feedback (e.g., Bugs).

9. **Email Node**
   Sends feedback summaries to relevant stakeholders.

---

## How to Set Up

1. Import the workflow JSON into your **n8n** instance.
2. Connect credentials for:

   * **Gmail** (receiving and sending feedback)
   * **Google Sheets** (logging feedback)
   * **Slack** (real-time notifications)
3. Create a Google Sheet with the following columns:

   * Date
   * Reviewer
   * Sentiment
   * Category
   * Feedback
4. Adjust the **AI node prompt** to match your preferred feedback categories.
5. Configure:

   * Slack channels for alerts
   * Email recipients for reports
6. Activate the workflow.

---

## Requirements

* n8n (Cloud or Self-hosted)
* Gmail API access (OAuth2 configured in n8n)
* Google Sheets API access
* Slack Webhook or OAuth connection
* Optional: Google Gemini or another LLM provider

---

## How to Customize

* Modify the AI prompt to use custom categories such as:

  * Support Issue
  * Billing Problem
  * Performance Issue
* Extend the Google Sheet schema with:

  * Product version
  * Priority score
  * Tags
* Add a translation step for multilingual feedback.
* Replace Slack with Microsoft Teams or Discord.
* Integrate with Jira, Trello, or Asana to auto-create tasks.

---

## Add-ons

* **Sentiment-based alerts**
  Trigger Slack notifications only for negative feedback.

* **Monthly report generator**
  Automatically compile feedback into a PDF and email it.

* **CRM integration**
  Sync categorized feedback into HubSpot or Salesforce.

* **Auto-response emails**
  Send an acknowledgment email when feedback is received.

---

## Use Case Examples

* SaaS teams route all **Bug** feedback directly to an engineering Slack channel.
* UX teams receive only **UX Issue** feedback for design improvements.
* Marketing teams log **Feature Requests** for roadmap planning.
* Customer support sends automated thank-you emails for every submission.

---

## Common Troubleshooting

| Issue                    | Possible Cause                            | Solution                                          |
| ------------------------ | ----------------------------------------- | ------------------------------------------------- |
| Workflow doesn’t trigger | Gmail/Form node not authenticated         | Reconnect Gmail or check webhook/form integration |
| No data extracted        | Code node parsing wrong field             | Update regex/parsing logic to match email format  |
| AI classification fails  | Invalid LLM credentials or quota exceeded | Reconnect LLM node or check usage limits          |
| Feedback not logged      | Wrong Google Sheet ID or missing sharing  | Verify Sheet ID and grant access to the account   |
| Slack messages not sent  | Invalid webhook or channel not found      | Reconfigure Slack node with valid credentials     |
| Email reports fail       | Gmail OAuth token expired                 | Refresh Gmail credentials in n8n                  |

---

## Need Help?

Our n8n automation experts at **WeblineIndia** can help you:

* Fine-tune AI prompts for better classification accuracy
* Build custom dashboards from Google Sheets data
* Add multilingual feedback handling
* Integrate with ticketing systems like Jira, Trello, or Asana

---
