# Profiles

A **profile** is one shipping address plus one payment method. Tasks attach to a profile, and the checkout uses whatever address and card the profile carries.

You can have as many profiles as you want — one per delivery address, one per card, one per "secondary buyer in the same household". Profiles do not affect each other.

## Creating a profile

Open **Profiles → Create Profile**. Fill in:

- **Shipping** — first/last name, email, phone, full address, country.
- **Payment** — cardholder name, card number, expiry, CVV.
- **iDEAL bank** — pick the bank you'll confirm payment from. Required, since the checkout redirect is iDEAL-based.

The form validates everything inline. Card brand (VISA / MC / AMEX) is detected from the number; CVV length adjusts accordingly.

![Profile create form](images/profile-create.png)

## Duplicating a profile

The common case is "same person, different address" or "same address, different card". Click **Duplicate** on any profile card to open the form pre-filled with that profile's data — the new row gets a default label of `Copy of <source name>`. Edit only the fields you want to change and **Save**. Editing the duplicate does not affect the original.

## iDEAL banks

Snag supports the standard iDEAL bank list (ABN AMRO, ING, Rabobank, bunq, ASN, etc.). At checkout the iDEAL redirect URL pre-selects this bank — you confirm the payment in your bank's app.

## Importing / exporting profiles

Use the **Import** / **Export** buttons in the header. JSON and CSV are both supported. Card data is exported in clear, so handle the file accordingly.

## Where data lives

Profiles are AES-256-GCM encrypted on disk; the key lives in the OS keyring. CVV and card number are never logged.
