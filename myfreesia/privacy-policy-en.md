# My Freesia Privacy Policy

**Last updated: 2026-10-27**
**Effective date: 2026-10-27**

> This is a translation. If it differs from the Korean version, the Korean version prevails.

---

## 1. Overview

My Freesia (마이 프리지아, "the app") is a planner for your to-dos, schedule, challenges and
mandala charts, together with your daily mood and diary. The app complies with the Personal
Information Protection Act of Korea and other applicable laws, and collects only what it needs to
provide the service.

This policy explains what information the app collects and why, where and how long it is kept, and
how you can delete it.

## 2. Sign-in and guest mode

### 2.1 Guest mode ("Browse")

If you use the app as a guest without signing in, **nothing is stored on our server.** Everything you
write stays on this device only and is removed when you delete the app or reset the device. Purchases
and syncing between devices are not available in guest mode.

If you later sign in, the records on this device move into that account and are saved on the server.

### 2.2 Social sign-in

To keep your records across devices or to buy Premium, sign in with one of the accounts below. Signing
in creates an account on our authentication server (Supabase Auth), and we receive the following from
the sign-in provider.

| Sign-in provider | What we receive |
|---|---|
| Apple (Sign in with Apple) | Apple user identifier, email address, name (only on the first sign-in, and only if you choose to share it). If you choose "Hide My Email", we receive only a **private relay address** created by Apple (@privaterelay.appleid.com). |
| Google | Google account identifier, email address, name, profile photo address (URL) |
| Kakao | Kakao account identifier, nickname. **We do not request your email or profile photo.** |

Under **Connected Accounts** in Settings you can link several social accounts to one account or unlink
them (at least one must remain). We receive the information in the table above for each account you link.

We use the email and name only to identify your account and show its connection status in Settings. We
do not use them for advertising or marketing, and we never show them to other users. The app has no
features for sharing records with other users.

**Revoking Sign in with Apple tokens:** if an Apple account is linked when you delete your account, the
app shows the Apple sign-in sheet once more, uses the one-time authorization code it returns to ask Apple
to disconnect the app (revoke the token), and then deletes the account. Neither the app nor our server
keeps Apple's tokens. If the revocation does not go through, for example because of a problem on Apple's
side or because you closed the sheet, the account is still deleted; in that case you can disconnect the app
yourself in iOS **Settings > Apple ID (your name) > Sign-In & Security > Sign in with Apple**.

## 3. Information we collect

### 3.1 Planner records you write

For signed-in users, records are saved on the device and also **synced to our server as a copy
(backup)**, so you can get them back after changing devices or reinstalling the app.

| Item | What is stored on the server |
|---|---|
| To-dos | Title, date, status (done, postponed, etc.), order, scheduled time |
| Events | Title, note, location, start and end time, color, repeat rule and repeat end date |
| Challenges | Title, length, reminder time, start and completion dates, sticker log (O, X or triangle per day) |
| Mandala charts | Board title, type and order; each cell's goal, note and progress |
| Notes | The day's one-line note (diary), weekly goals, daily challenge notes |
| Today's mood | Mood for each day (one of five levels) |
| D-days | Title, date, whether it is your featured D-day |
| Diary photo list | Identifiers of the photos attached to each day (the photos themselves: §3.2) |

These records are used only to provide the service (syncing across devices and backup). We do not read
them or use them for analytics or advertising (except to respond to lawful requests or to support
requests you make).

**Records you delete in the app:** when you delete a to-do, event, challenge, mandala chart, note, mood
or D-day, the server copy is not removed right away; it is **only marked as deleted**. This lets us
recover records lost to a device error or a faulty sync. Records marked as deleted are not shown in the
app, and they are **permanently deleted together with your account** when you delete it.

### 3.2 Diary photos

When you attach photos to a day's note (1 per day free, 3 per day with Premium), the app shrinks each
photo so its longer side is at most 1600 pixels, keeps it on this device and, if you are signed in,
uploads it to a **private storage area** on our server. Storage is separated by account so only you can
read and write your photos, and it cannot be opened through a public address.

The camera and photo library are used only when you tap to attach a photo, and the app does not access
any photos other than the ones you pick. When you delete a photo in the app, it is deleted from the
server as well.

### 3.3 Pet and carrots

Planner activities such as completing to-dos or logging your mood earn **carrots**, the pet's currency,
which you can spend on decorations for your pet's yard. For signed-in users, carrots are managed on the
server to prevent abuse, and we store:

- Carrot earning and spending records: type of activity (for example, completing a to-do), amount earned
  or spent, a key that prevents double crediting, the date on your device, and the time. When you get a
  decoration, which one.
- How decorations are arranged in your pet's yard

Carrots are not sold for money and cannot be exchanged for cash. The pet's growth is stored only on your
device (§3.7).

### 3.4 Purchase information

Premium and paid themes are bought through the App Store (sign-in required). To confirm a purchase is
genuine, the app sends the transaction information signed by the App Store to our server, which checks
the signature against Apple's certificates and then stores:

- Product, product type (subscription, lifetime or item), platform, the store's original transaction
  number, purchase time, subscription expiry time, and environment (real purchase or test)

When you start a purchase, the app also passes **your account identifier in the app** to Apple to link
the payment to your account. To keep your entitlements accurate when a refund, renewal or expiry happens
outside the app, we receive **App Store Server Notifications** from Apple and update or remove the records
above. **The app never receives or stores card numbers or other payment details**; Apple handles them
directly.

If you restore the same App Store purchase on a different account, the entitlement moves to the account
that restored it (one purchase applies to one account only).

### 3.5 Notifications

- **Event reminders (server push):** when you set a reminder on an event, our server sends it directly
  through the Apple Push Notification service (APNs) so it arrives on time even if you haven't opened the
  app for a while. For this, the server stores your **device's push token** (with platform and whether it
  is a real or test environment) and the **reminders to send** (notification title, event title, time to
  send, time sent). We do not use Firebase or any other push service.
  - The push token is removed from the server when you sign out, and tokens that Apple reports as no longer
    valid are removed too.
  - Records of sent reminders are deleted automatically **30 days after they are sent**. When you edit or
    delete an event, its unsent reminders are changed or deleted as well.
  - If you turn off notification permission on your device, Apple does not issue a token and server push
    is not used.
- **Challenge reminders and all other notifications** are **local notifications** scheduled on your
  device and do not go through our server. In guest mode, event reminders are local notifications too.

### 3.6 Information collected automatically

- **Access logs** — when the app talks to our server, access and error records such as IP address,
  request time and account identifier are kept in the logs of our server provider (Supabase). They are
  used only for security and troubleshooting and are deleted automatically when the provider's log
  retention period ends.
- **No analytics or advertising tools.** The app contains no analytics, crash reporting or advertising
  SDKs. It does not read the advertising identifier (IDFA) and does not track you.

### 3.7 Information stored only on your device

The following stays **on this device only** and is never sent to our server.

- **App lock passcode:** the four-digit passcode is not stored as is; only a transformed value (hash) is
  kept in the device Keychain.
- **Face ID / Touch ID:** iOS handles authentication. The app never accesses or stores face, fingerprint
  or other biometric data; it only learns whether authentication succeeded.
- **Data for Home Screen and Lock Screen widgets:** today's to-do titles, today's mood and your featured
  D-day are placed in a shared storage area on the device reserved for the app (App Group) so the widget
  can read them. If you add a widget, this content is shown on your Home Screen or Lock Screen and may be
  seen by anyone who can see your device.
- **Pet growth, focus timer records, app settings such as theme, font and time zone, and scheduled local
  notifications**
- **Sign-in state:** your sign-in session is kept securely in the device Keychain.

### 3.8 Export and sharing

The monthly **PDF diary** and **monthly recap card** are created on your device and go only where you
choose on the share sheet (Messages, Save to Files, etc.). The app does not send their contents to our
server. The recap card contains only your mood distribution and record counts, never your diary notes or
photos.

### 3.9 Looking up outside information

- **Public holidays:** to show holidays on the calendar, the app looks up Google Calendar's public holiday
  calendars. It sends no records or account information, only the country and year requested.
- **PDF fonts:** the first time you create a PDF diary in Japanese or Chinese, the app downloads a font
  file from Google Fonts.

In both cases your device's IP address may reach Google as part of the connection.

## 4. Permissions

| Permission | Why we need it | If you decline |
|---|---|---|
| Notifications | Sends event and challenge reminders | You won't receive reminders |
| Camera | Takes a photo to keep with today's diary | Only taking photos is unavailable |
| Photo library | Chooses a photo to keep with today's diary | Only picking from your library is unavailable |
| Face ID | Unlocks the app lock with Face ID (if you turn on app lock) | You unlock with the four-digit passcode |

**You can use the app even if you decline every permission**; only the related feature stops working. The
app does not ask for location, contacts, calendars, health data or ad tracking permission.

## 5. Third-party processing

We **do not sell or provide your information to third parties** (except when an investigative agency or
similar authority requests it through lawful procedures). We entrust processing to the companies below
only as far as needed to run the service.

| Processor | What they do | Privacy policy |
|---|---|---|
| Supabase Inc. | Authentication; storing planner records, diary photos, carrot records, purchase verification records, push tokens and reminders; running server functions | https://supabase.com/privacy |
| Apple Inc. | Sign in with Apple, token revocation on account deletion, delivering push notifications (APNs), App Store payments and server notifications | https://www.apple.com/legal/privacy/ |
| Google LLC | Google sign-in (if you choose it), public holiday lookup, fonts for PDFs | https://policies.google.com/privacy |
| Kakao Corp. | Kakao sign-in (if you choose it) | https://www.kakao.com/policy/privacy |

### 5.1 International transfers

Some processors handle personal information outside Korea. As required by law, we disclose the following.

| Recipient | Country | Items transferred | When and how | Retention |
|---|---|---|---|---|
| Supabase Inc. | Republic of Korea (stored in the Seoul region). The processor is a US company and may process or access data from outside Korea when needed to run server functions or handle incidents | Account identifier, sign-in provider information (email, name, profile photo address, nickname), planner records (including notes, mood and D-days), diary photos, carrot records, purchase verification records, push tokens and reminder content, access logs | Whenever you use the app, over an encrypted connection | Until you delete your account (except as noted in §6) |
| Apple Inc. | United States | (With Apple sign-in) sign-in authentication requests, token revocation request on account deletion, push tokens and reminder content (notification title, event title), account identifier on purchase | On sign-in, deletion, notification and purchase, over an encrypted connection | Per each company's policy |
| Google LLC | United States | (With Google sign-in) sign-in authentication information; IP address when looking up holidays or fonts | On sign-in and lookup, over an encrypted connection | Per each company's policy |

If you do not want your information transferred abroad, you can use guest mode (nothing is stored on the
server) or delete your account. In that case syncing between devices and purchases are not available.

## 6. Retention and deletion

- Account information and records synced to the server (including records you deleted in the app that are
  only marked as deleted) are kept **until you delete your account**.
- When you delete your account, your account information on the server (including linked social accounts),
  to-dos, events, challenges, mandala charts, notes, moods, D-days, diary photos and their list, carrot
  records and yard layout, purchase verification records, push tokens and reminders are **all deleted
  immediately**. Records left on this device are deleted as well.
- Diary photos you delete in the app are deleted from the server as well.
- Records of sent event reminders are deleted automatically 30 days after they are sent.
- Access logs are deleted automatically when the server provider's log retention period ends. A record of
  the account deletion (such as the deleted account's identifier) may remain in these logs until then.
- The payment history itself is kept by Apple, which processed the payment, under Apple's policies and
  applicable law.
- Guest-mode records and information stored only on the device are deleted when you delete the app or use
  **Reset All Data** in Settings.
- Electronic files are deleted in a way that cannot be recovered.

## 7. Your rights

You can do the following at any time.

- **Access and correct** — you can view and edit all your records directly in the app.
- **Delete** — delete your account and your records on the server in **Settings > Delete Account**. If you
  have already removed the app, you can ask by email as described in
  [Delete your account](account-deletion-en.md).
- **Withdraw consent** — turn off permissions in your device settings, sign out, or delete your account.
- You can also exercise these rights by emailing us below. We will reply with the result within **10 days**
  of receiving your request.

## 8. Children under 14

My Freesia does not accept sign-ins (account creation) from children under 14. Before signing in, you are
asked to confirm that you are 14 or older. The answer stays on your device and is never sent to our server.
If you answer that you are under 14, you cannot sign in and can use the app only in guest mode, which stores
nothing on our server. Guest records exist only on your device, so they are lost if you delete the app or
change devices.

If we nevertheless learn that personal information of a child under 14 was collected, we will delete it
without delay. A guardian can ask us to delete it by emailing us below.

## 9. Security

- All communication with our server is encrypted (HTTPS).
- The database uses row-level security (RLS) so **each user can access only their own records**. Purchase
  verification records and carrot records cannot be changed by the app directly; they are written only
  through server functions.
- Diary photo storage is private, and only you can access your account's folder.
- Your sign-in session and app lock passcode are kept in the device Keychain.

## 10. Changes to this policy

If this policy changes, we will let you know through an in-app notice or an update, at least 7 days before
the change takes effect. Changes that matter more to you, such as collecting new items, will be announced
30 days in advance.

## 11. Contact

- Privacy officer: Representative, 그이어 (GoWeAre)
- Email: go.we.are.official@gmail.com
- Response time: within 10 days of receipt
