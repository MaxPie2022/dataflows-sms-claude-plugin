---
name: send-sms
description: Send or schedule an SMS with DataFlows SMS. Use when the user asks to text, message or SMS someone, send a campaign or announcement to a contact group, or schedule a text for later.
---

Use the DataFlows SMS connector's tools for every step. A sent SMS can't be recalled, so confirm before sending.

## Before any send

1. Work out the recipients. Phone numbers can be in international format (+61412345678) or Australian local format (0412 345 678). For a contact group, call `list_contact_groups` if you don't know its exact name.
2. Work out the sender. If the user hasn't chosen one, call `list_sender_ids` and use the default. If the user expects replies, pick a sender marked as able to receive replies (a dedicated number). Business-name senders can't receive replies.
3. Check the message text with the user, and point out obvious typos before sending.
4. Call `preview_sms` when the message goes to a contact group, is long, contains emoji, or looks like marketing. Tell the user the recipient count, the number of SMS parts and the credits it will use, and act on any warnings it returns, such as a missing opt-out line on a marketing message or a blocked word.
5. Show the user exactly what will be sent: recipients or group, sender, message text and send time. Send only after they confirm.

## Sending

* To up to 10 numbers: `send_sms` with `to`, `message` and optionally `sender`.
* To a contact group: `send_sms_to_group` with `group`, `message` and `expected_recipients` set to the recipient count `preview_sms` returned and the user confirmed. If the count no longer matches, preview again and re-confirm instead of sending.
* To schedule: pass `send_at` to either tool, as a date and time in the user's time zone. `list_scheduled_messages` shows what is waiting, and `cancel_scheduled_message` cancels one before it sends.

## After sending

Report the result briefly: how many messages were queued, the sender and the credits used. If any recipient failed, give the reason the tool returned. Don't retry a failed send on your own; tell the user what happened and let them decide.
