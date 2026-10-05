<img src="assets/icon.png" alt="DataFlows SMS" width="96">

# DataFlows SMS for Claude

Send, schedule and track business SMS from your DataFlows account by asking Claude in plain language. The plugin connects Claude to the DataFlows SMS connector and adds skills that guide Claude to confirm every send, preview cost and compliance warnings before contact group campaigns, and report delivery and replies clearly.

## What you need

* A [DataFlows](https://dataflows.com.au) account with SMS credits
* A sender ID or number on your account

## Use it

After you add the plugin, connect DataFlows SMS from the plugin's **Connectors** tab and sign in with your DataFlows login. Then ask Claude things like:

* "What's my DataFlows SMS balance and which sender IDs can I use?"
* "Send 'Your order is ready for pickup' to 0412 345 678 from DataFlows."
* "Preview a message to my Demo customers group saying 'We're closed on Monday for the public holiday', then send it once I confirm."
* "Schedule 'Reminder: your appointment is tomorrow at 10am' to 0412 345 678 for 9am tomorrow."
* "Did my messages today get delivered, and did anyone reply?"

Claude asks you to confirm before any message is sent. The same sender ID registration, opt-out and blocklist rules as the DataFlows dashboard apply.

## What's included

* **Connector**: the DataFlows SMS MCP server at `https://sms.dataflows.com.au/mcp/claude`, with tools to check your balance and senders, preview, send and schedule messages, and read delivery status, replies, campaign results and usage.
* **Skills**: `send-sms`, the confirm and preview workflow for sending and scheduling, and `sms-reports`, for delivery, replies, campaigns and usage.

## Data

The plugin itself stores nothing and runs no code. Everything goes through the DataFlows SMS connector at `sms.dataflows.com.au`, which acts only on the DataFlows account you sign in with, and only when you ask. It sends the phone numbers, message text, sender and send time you give it to DataFlows, and returns your balance, senders, contact group names and sizes, and the status and replies of messages sent through the connector. Messages are delivered by DataFlows' carrier partners. See the [DataFlows Privacy Policy](https://dataflows.com.au/privacy-policy), section "AI Assistant Connections".

## Support

Email [support@dataflows.com.au](mailto:support@dataflows.com.au) or see [dataflows.com.au/integrations/claude](https://dataflows.com.au/integrations/claude).
