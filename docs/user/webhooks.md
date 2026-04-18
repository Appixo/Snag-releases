# Discord Webhooks

Snag can post task lifecycle events to a Discord channel via a webhook. Useful for getting pinged the second a drop lands while you're away from the desk.

## Setting up the webhook

1. In Discord, open your server settings → **Integrations → Webhooks → New Webhook**. Pick a channel and copy the **Webhook URL** (starts with `https://discord.com/api/webhooks/`).
2. In Snag, open **Settings → Notifications**, paste the URL, click **Save**.
3. Click **Test Webhook** to confirm Discord receives the post.

![Webhook configuration](images/webhook-setup.png)

## Choosing which events fire

The **Discord Events** section controls which lifecycle moments trigger a post. All toggles are independent — turn off the noisy ones, leave on the ones you actually want pinged for.

| Event | Default | When it fires |
| --- | --- | --- |
| Task Started | Off | You click Start on a task |
| Stock Detected | On | A monitored product flips to in-stock |
| Checkout Started | Off | The bot begins the browser checkout |
| Payment Ready | On | The iDEAL URL is ready — open and pay |
| Task Failed | On | A task errors out (including expired auth) |
| Task Stopped | Off | You manually stop a running task |

The most useful pair is **Stock Detected** + **Payment Ready** — that's "drop incoming" + "pay now".

## Privacy

The webhook payload contains the product URL, task ID, and a short status line. It does not include your address, card data, or session cookies.
