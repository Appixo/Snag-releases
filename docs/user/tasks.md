# Tasks

A **task** monitors one Bol.com product and auto-checks out when stock lands. Each task pairs a product URL with a profile (shipping + payment) and a polling mode.

## Creating a task

Open **Tasks → New Task** and fill in:

- **Product URL** — paste a Bol.com `/p/.../<id>/` URL.
- **Profile** — pick which address + card to ship to. Set a default in Settings if you want it pre-selected.
- **Polling mode** — see below.
- **Proxy group** *(optional)* — rotate through a proxy group instead of going direct.
- **Retry limit** / **delay** — how many checkout attempts before giving up.

Click **Start** to begin monitoring. Click again to stop.

![Tasks page](images/tasks.png)

## Polling modes

Snag polls the product page on a fixed cadence. Faster polling reacts sooner but uses more bandwidth and looks more bot-like to Akamai.

| Mode | Cadence | Use when |
| --- | --- | --- |
| **Poll10s** | every 10 seconds | Casual monitoring, low-priority drops |
| **Poll3s** | every 3 seconds | Standard for known drop windows |
| **Poll1s** | every 1 second | High-priority drops, short windows |

You can change the mode of a running task without stopping it.

## Checkout caps

To stop a single drop from firing a dozen payment URLs at you, Snag caps how many checkouts complete per profile and per group. Defaults: **1 per profile, 1 per group**. Configure both in **Settings → Checkout Limits**. Counters reset with the **Reset counters** button.

## Bulk actions

Select multiple tasks via the row checkboxes to start, stop, or delete them in one go.

## What happens after a successful checkout

Snag opens the iDEAL payment URL in your browser. Confirm the payment in your bank app. Snag does not handle the iDEAL step — that's intentional, since automating bank confirmation is both fragile and bad for your account standing.

## Errors

When a task fails it surfaces a typed error kind (e.g. `SessionExpired`, `OutOfStock`, `Blocked`). See [Troubleshooting](./troubleshooting.md) for what each one means.
