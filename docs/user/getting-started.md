# Getting Started

Snag automates Bol.com checkouts: monitor a product, auto-cart it the moment stock drops, and hand you an iDEAL payment URL. You confirm the payment yourself.

This guide walks you through the four things you need to do before your first task can run.

---

## 1. Install Snag

Download the latest installer from the [Releases page](https://github.com/Appixo/Snag-releases/releases/latest) and run it. Snag is signed and updates itself in-place — once installed, future versions arrive automatically.

![Installer dialog](images/installer.png)

## 2. Link your Bol.com account

Open **Settings → Bol.com Account** and click **Log in**. A browser window opens on the bol.com login page. Enter your credentials normally — 2FA and CAPTCHA both work the way you expect, Snag does not touch them. When you land on your account overview, the window closes by itself and the indicator turns green.

Cookies are stored encrypted on disk. Details: [Account](./account.md).

![Bol.com Account section](images/account-linked.png)

## 3. Create a profile

A profile holds your shipping address, card details and iDEAL bank. Open **Profiles → Create Profile** and fill in the form. You can have many profiles for different addresses or cards. Details: [Profiles](./profiles.md).

## 4. Create your first task

Open **Tasks → New Task**, paste a Bol.com product URL, pick a profile and a polling mode, and click **Start**. Snag monitors the product and auto-checks out when stock lands. Details: [Tasks](./tasks.md).

## Optional: Discord notifications

Wire up a Discord webhook in **Settings → Notifications** to get pinged on stock detection, payment-ready, and failures. Details: [Webhooks](./webhooks.md).

---

Stuck? See [Troubleshooting](./troubleshooting.md).
