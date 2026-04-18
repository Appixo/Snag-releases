# Troubleshooting

When a task fails Snag classifies the error into one kind and surfaces it in the Tasks list. Use this page as a recipe book.

## SessionExpired

Your stored Bol.com cookies are no longer authenticated.

**Fix:** Settings → Bol.com Account → **Log in** to re-link.

## Blocked

Akamai (bol.com's bot manager) flagged a request and refused to serve the response. Usually caused by polling too aggressively or by a low-reputation proxy IP.

**Fix:** drop the task to **Poll10s** for a while, switch the proxy group, or run a few minutes without proxies to let the IP's reputation recover.

## OutOfStock

The product was out of stock at the moment of checkout. Not a bug — the bot kept polling and will retry on the next stock event.

**Fix:** none, this is expected. The task remains active.

## ProductNotFound

The Bol.com URL no longer resolves to a product page (delisted, region mismatch, expired SKU).

**Fix:** check the URL in a normal browser. If the page is gone, delete the task.

## ProfileMissing

The profile attached to this task was deleted or the linked iDEAL bank is empty.

**Fix:** open the task, pick a valid profile, and start it again.

## CheckoutFailed

The checkout reached the payment step but the iDEAL redirect did not return a usable URL. Often a transient bol.com hiccup.

**Fix:** retry. If it fails twice in a row, file an issue.

## NetworkError

DNS, TLS, or socket failure — almost always your network or your proxy.

**Fix:** check your connection, test your proxies in **Proxies → Test**.

## Unknown

Snag could not classify the error.

**Fix:** copy the error text into a GitHub issue so we can add it to the taxonomy.

---

## Application won't start

Delete `%APPDATA%\Snap\` and relaunch — that resets local state without touching your license. You will need to re-link Bol.com and re-import profiles.

## Updates not arriving

Check **Settings → Account → Check for Updates**. If the check itself errors, your firewall is probably blocking the GitHub releases endpoint.
