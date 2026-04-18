# Bol.com Account

Snag places orders under your real Bol.com account. To do that, it needs your session cookies — the same things your browser stores after you log in. You authenticate once, Snag remembers the session, and subsequent checkouts run without re-prompting you for credentials.

## Why we need it

The checkout flow on bol.com requires an authenticated session. Anonymous carts cannot complete an iDEAL payment redirect. Snag opens a real browser window so you log in normally — your password never passes through Snag's code.

## Linking your account

1. Open **Settings → Bol.com Account**.
2. Click **Log in**. A browser window opens on the bol.com login page.
3. Enter your email and password. Handle 2FA and CAPTCHA as you would in any browser — Snag does not interfere.
4. When the window closes by itself, you are linked. The indicator turns green and shows the timestamp.

![Linked indicator](images/account-linked.png)

## Where cookies live

Cookies are stored AES-256-GCM encrypted on disk in your app data directory. The encryption key lives in the OS keyring, separate from the rest of your secrets. Nobody other than your local user account can decrypt them.

## Re-linking when the session expires

Bol.com sessions eventually expire. On every app launch Snag silently checks the stored session against bol.com; if it has gone stale, the indicator flips to **Session expired, please re-link**. Click **Log in** again and walk through the same flow.

You can force a check at any time with **Check session**.

## Logging out

**Log out** wipes the stored cookies. The next checkout will fail until you re-link.

## Ban-risk note

Running automated checkouts is a violation of bol.com's Terms of Service. Snag minimises detection risk (real browser, real cookies, conservative polling) but bans are still possible. Use a separate account if this matters to you.
