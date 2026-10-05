---
name: sms-reports
description: Check SMS delivery, replies, campaign results, credit balance or usage in DataFlows SMS. Use when the user asks whether texts were delivered, who replied, how a campaign went, how many credits are left, or how much SMS they've sent.
---

Use the DataFlows SMS connector's read-only tools and summarise the answer rather than pasting raw results.

* **Balance and senders**: `get_sms_balance` for credits left, `list_sender_ids` for the senders on the account.
* **Delivery of messages sent from Claude**: `list_sent_messages`, filtered by phone number when the user asks about one person. It covers messages sent through this connector only, not texts sent from the DataFlows dashboard or other integrations.
* **Replies**: `list_sms_replies` for replies to messages sent through this connector. Replies only arrive on senders that can receive them, such as a dedicated number.
* **Campaign results**: `list_campaigns` for campaigns across the whole account, with delivered, failed (with the reason) and pending counts. It doesn't include message text.
* **Usage**: `get_usage_summary` for messages sent, credits used, delivery rate and top senders over a period.

When reporting failures, group them by reason and say what usually fixes each one, for example an invalid number or a sender ID that isn't registered. Keep the answer to the numbers the user asked for.
