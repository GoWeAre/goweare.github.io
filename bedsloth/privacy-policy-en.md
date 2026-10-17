# BedSloth Privacy Policy

**Last updated: 2026-10-18**
**Effective date: 2026-10-18**

> This is a translation. If it differs from the Korean version, the Korean version prevails.

---

## 1. Overview

BedSloth ("the app") is an "anti-pedometer": you set a daily step limit, and the
app lets you know when you go over it. We care about your privacy and collect only
the minimum information needed to run the app.

This policy explains what information the app collects and why, how long it is
kept, and how you can delete it.

## 2. No sign-up required

The app **does not collect identity information such as your name, email address,
phone number or date of birth.** (The exception is the email address and related
information stored if you choose to link a Google or Apple account, as described below.)

When you first open the app, our server creates a random identifier (an anonymous
account) to store your records. This identifier does not reveal who you are and is
used only to keep your records together inside the app.

**Linking an account (optional) — Google and Apple sign-in:** If you want to keep your
records when you change phones, you can link a Google account or an Apple account
(Sign in with Apple) in Settings. Signing in is never required, and you can use every
feature of the app without linking. When you link, the following is stored by our
authentication provider (Supabase Auth) and linked to the anonymous identifier above.

| Sign-in provider | What we store |
|---|---|
| Google (Android, iOS) | Google account identifier, email address (and the name and profile photo URL Google sends at sign-in) |
| Apple (iOS, Android) | Apple user identifier, email address — if you choose "Hide My Email", we only receive the **private relay address** Apple creates (@privaterelay.appleid.com). We do not request your name. |

We use the email address only to show the link status in Settings and to restore your
records; it is never shown to other users or used for marketing.

**Keeping and revoking the Apple sign-in token:** When you link an Apple account, we keep
the **refresh token** Apple issues in a separate server-side store so that we can ask
Apple to revoke it when you delete your account. The app and other users cannot read this
store; only server administration access can. When you delete your account, we first ask
Apple to revoke the token and then delete the token together with your account (if the
revocation fails on Apple's side, your account is still deleted, and you can remove the
link yourself in iOS **Settings > Apple ID > Sign-In & Security > Sign in with Apple**).

## 3. Information we collect

### 3.1 Information you enter

| Item | Purpose | Visible to other users? |
|---|---|---|
| Nickname | Shown in the ranking, to friends and in parties | Yes — ranking (top 100), friends, party members, people you invite to a party, people you tuck in (including neighbors shown in the ranking) |
| Daily step limit | Threshold for "limit exceeded" notifications. Each day's limit is stored on the server with that day's steps | Yes — friends and party members |

You start with an automatic nickname ("침대늘보", Korean for "BedSloth", followed by the
first 6 characters of your random account identifier) and can change it in Settings
(1–20 characters). Your first change after sign-up is free; after that, each change needs one
**Nickname Pass** (see §3.3). Resetting to your default sign-up nickname in Settings is always free and uses
no pass, so if you put personal information in your nickname you can remove it this way. Your nickname is **visible to other users**, so please don't use
your real name, contact details or anything that could identify you.
Nicknames containing words on the operator's blocklist (such as slurs) are not saved.

The character (avatar) currently uses the same default for every user and cannot be
changed. This default is shown in the ranking.

### 3.2 Step count

This is the core of the app. We read it in two ways:

- **Device step sensor** — Android's step sensor, iOS motion data
- **Health data** — Health Connect on Android, HealthKit on iOS

The app **reads step count only.** It never requests or reads other health
information such as heart rate, sleep or weight, and it **never writes anything**
to your health data.

Our server stores **only your daily step totals** (and that day's step limit). We do not collect routes or
location (the app does not even request location permission).

Along with each step total we store **which source it came from** (device sensor
or health data). This is used to prevent ranking manipulation.

**Background upload:** Even if you do not open the app, whenever the app checks your steps in the background (roughly every 1–2 hours on Android; at the operating system's discretion on iOS), it periodically sends today's step total, its source and that day's step limit to our server. The kinds of data are the same as when you open the app; only the timing differs. For this, each device creates an **upload key** (a random value) that is kept on the device, and our server stores **only a hash** of it, not the key itself. The upload key is used only to upload step counts, each user can have up to 5, and they are deleted together with your account.

**Weekday limits stored on the server:** The step limit you set for each weekday is also stored on our server. This lets the server trim the limit attached to each day's step record so it never exceeds your own setting, so that success and failure are judged fairly by the same standard, and it is also used to restore your limits when you reinstall the app or continue on another device. We keep only a small per-day count of how many times the server trimmed a limit, for **30 days**. This information is deleted together with your account.

**Filling missed days:** When you open the app, it re-reads up to the last 6 days of step counts from your health data (Health Connect / HealthKit) to fill in daily totals missing on the server. Only daily totals are sent. When the app shows hourly step counts (the hourly chart in the blanket journal), it reads your health data on the device only and does not send it to our server.

### 3.3 App usage records

| Item | Purpose |
|---|---|
| Streak records and badges | Providing features |
| Postpone passes / Streak Savers owned and used | Providing features |
| Today's exemption record (date, whether it came from a postpone pass or an ad, and for an ad the step count at that moment) | Judging streaks and party streaks |
| Achievement unlocks (achievement, time unlocked) | Achievements and their rewards |
| Sloth Diary progress (story chapters you finished, time) | New-chapter notices and the diary view in the Sloth Diary (the in-app picture-book story) |
| Story rewards (chapter, decoration or amount of fluff received, time) | Giving each story reward only once, calculating your fluff balance |
| "Not-to-do" quest completions (date, quest) | Calculating fluff rewards |
| Records of fluff received again by watching an ad (date, amount, ad reward transaction ID, time) | Calculating your fluff balance, preventing double rewards |
| Decoration purchases (item, fluff spent, time), including party chat phrase packs you get | Decoration feature, checking which phrase packs you can use in party chat, fluff balance |
| Fluff purchase records (payment notification event ID, store transaction ID, product, amount of fluff, time, and the time it was taken back if refunded) | Delivering purchased fluff, calculating your fluff balance, preventing double delivery, taking fluff back on refund |
| Nickname wallet (number of Nickname Passes held (up to 5), number of passes refunded after being used, pieces collected, whether the one free change has been used) | Nickname change feature, taking passes back on refund |
| Records of Nickname Pass pieces received by watching an ad (ad reward transaction ID, date, time) | Giving pieces (up to 5 a day), preventing double rewards |
| Records of story bonus fluff received by watching an ad (chapter, amount, ad reward transaction ID, time) | Calculating your fluff balance, giving the bonus only once per chapter |
| Records of decorations tried on for a day by watching an ad (decoration, date, end time, ad reward transaction ID) | Showing the one-day try-on (once a day), preventing duplicates |
| Equipped decorations | Shown in your room and **to your friends and party members** |
| Push token, app language, time zone, whether to receive party chat notifications (if friend updates are on) | Delivering friend update and party chat notifications |

Your fluff (in-app points) balance is not stored; it is calculated from these records
(including fluff purchase records) and invite reward records. Fluff can also be bought
with an in-app purchase (see §3.4), but it cannot be exchanged for money. If purchased fluff
is refunded, that amount is removed from your balance; if you have already spent it, your
balance can go below zero.

#### Information stored only on your device

Your weekday step limits, the last date you opened the app (for reminders to users who
haven't opened it for a while), notification history, whether the app has
asked you for a rating, which "Not-to-do" settlements you have seen, how many times you have sent each party chat quick phrase, and today's steps for the home-screen widget are stored **only on your device**
and are not sent to our server. They are excluded from cloud backup and device transfer
and are deleted when you uninstall the app. If you add the Android home-screen widget,
today's steps and limit appear on your home screen and may be seen by anyone who can see
your device.

### 3.4 Information collected automatically

- **Crash reports (Firebase Crashlytics)** — When the app crashes or an error
  occurs, the device model, OS version and where the error happened are sent. Used
  only to fix the app.
- **Usage statistics (Firebase Analytics)** — Aggregate information such as which
  screens are used and how often.
- **Advertising identifier (Google AdMob, Firebase)** — To show ads, prevent invalid
  clicks and measure ad performance, your device's advertising ID (Android advertising
  ID; on iOS, the IDFA only if you allow tracking) and an approximate region inferred
  from your IP address are sent to Google. Firebase Analytics may also use the
  advertising ID. You can reset or delete the advertising ID, or limit tracking, in your
  device settings.
- **Purchase records (RevenueCat)** — If you make an in-app purchase, **your app
  account identifier** is sent to RevenueCat and linked to your purchase history so we
  can check purchase and subscription status. For Streak Savers and postpone passes, RevenueCat notifies
  our server after payment, and the server records that notification (event ID, store transaction ID,
  product, account identifier, time) to prevent double delivery. Fluff packs and Nickname Passes are
  delivered the same way, and on a refund the server matches the same transaction ID to take them back (see §3.3
  for fluff purchase records and the nickname wallet). For Premium, the server stores **when your subscription is valid until and when you last received the weekly skip pass**, so it can give subscribers one skip pass every week. **The app never
  receives or stores card numbers or other payment details**; Google/Apple process
  payments directly.
- **Access logs** — When the app communicates with our server, access records such as
  your IP address and request time are logged by our server provider (Supabase). They
  are used only for security and troubleshooting and are deleted automatically after
  **7 days**.

- **Friend update notifications (Firebase Cloud Messaging)** — To let you know when a friend
  tucks you in, saves your day with a skip pass, invites you to a blanket party, or talks to you in party chat, we store
  **your device's push token, app language, time zone, and whether to receive party chat notifications** on our server. Notifications are
  delivered through Google (Firebase Cloud Messaging) and, on iOS, Apple (APNs). The
  notification text contains only **the sender's nickname** (no step counts or account
  identifiers). If you turn off "Friend updates" in Settings or turn off the device
  notification permission, the token is removed from our server the next time you open the
  app; it is deleted when you delete your account, and automatically after 90 days without
  opening the app.
  Party chat notifications also **carry no message content** — only the sender's nickname — and are sent
  once until you read the chat (at most once a day). They are not sent between 11 p.m. and 8 a.m. You can
  turn them off separately with "Party chat" in settings.

Step limit alerts, quest reminders, report alerts, and come-back check-ins are **local
notifications created on your device** and do not go through a server.

### 3.5 Special notice on health data (Health Connect / HealthKit)

- The app requests **read-only access to step count (Steps)** from Android
  **Health Connect** and iOS **HealthKit**. It does not request write access.
- Step counts read from health data are used **only to provide app features**
  (limit-exceeded notifications, streaks, ranking, showing step counts to friends and
  party members). We do not use them for
  advertising, marketing, credit decisions or any other purpose, we do not sell or
  transfer them to third parties, and no person reads them (except where required by
  law or to handle an inquiry you make).
- Use of information received from Health Connect adheres to the Limited Use
  requirements of the [Health Connect Permissions policy](https://support.google.com/googleplay/android-developer/answer/12991134).
  HealthKit data is handled in line with Apple's
  [App Store Review Guideline 5.1.3](https://developer.apple.com/app-store/review/guidelines/#health-and-health-research).
- HealthKit data is not stored in iCloud.
- On Android, tapping "privacy policy / why this app uses your data" on the Health
  Connect permission screen opens an **in-app step data explanation screen**, from
  which you can open this full policy.

### 3.6 Ads and consent (AdMob, ATT, Google consent message)

- After the first screen appears, and **before** the ad SDK starts, the app asks for
  any required consent:
  1. In regions where consent is legally required, such as the EEA, the UK and
     Switzerland, the **Google consent message (UMP)** asks whether you consent to
     personalized ads.
  2. On iOS, Apple's **App Tracking Transparency (ATT)** prompt asks whether the
     advertising identifier (IDFA) may be used.
- You can use every feature of the app without consenting. In that case you may see
  non-personalized ads or, depending on your region, no ads.
- **Watching an ad to postpone today (rewarded ads):** when you use this feature, the app
  stores today's date and your step count at that moment **directly on our server** and
  receives a random verification code. To confirm you watched the whole ad, **only this
  code** is passed to Google (AdMob); your step count and account identifier are not sent
  to Google. To prevent double rewards, the server stores the verification record (ad
  reward transaction ID, date, step count, result, time).
- **Watching an ad to receive fluff again (rewarded ads):** you can watch an ad to receive
  the previous day's "Not-to-do" fluff one more time. Here too the app leaves the target
  date **directly on our server** and receives a random verification code, and **only this
  code** is passed to Google (AdMob). Your step count is not used for this feature. The
  server stores the record (date, amount, ad reward transaction ID, time).
- **Watching an ad to collect Nickname Pass pieces (rewarded ads):** each ad you watch to the end
  gives one piece (up to 5 a day), and 10 pieces become one Nickname Pass (you do not collect
  pieces while you hold a pass). Here too the app leaves the date **directly on our server** and receives a
  random verification code (the server stores your account, the date and this code), and **only this code** is
  passed to Google (AdMob). Your step count and account identifier are not sent to Google. The server stores the
  record (ad reward transaction ID, date, time).
- **Watching an ad for story bonus fluff, or to try on a decoration for a day (rewarded ads):** in the Sloth Diary you can
  get bonus fluff once for each chapter whose story reward you received, and once a day you can try on a decoration you
  do not own for 24 hours. Here too the app leaves the chapter or decoration and the date **directly on our server** and
  receives a random verification code, and **only this code** is passed to Google (AdMob). Your step count and account
  identifier are not sent to Google. The server stores the record (chapter or decoration, date, end time, ad reward
  transaction ID, time). A try-on is only drawn on screen, so the decorations you bought and what you have equipped do not change.

### 3.7 Friends, blocking, "Tuck in" blankets, blanket parties and invites

Each user has one 6-character **friend (invite) code**. When you give your code to
someone and they enter it in the app, you become **friends** (up to 30). We store who is
friends with whom and when.

Your friends can see: **your nickname, your most recent day's step count and that day's
step limit, when that record was last updated, your sloth's decorations, and whether you
tucked them in with a blanket today.** If your steps came from a source we cannot verify
(e.g. manual entry), friends see "couldn't measure" instead of the number.

**"Tuck in" blankets:** you can send each friend one blanket per day. We store the
sender, recipient, date and time, and when the recipient saw it. The recipient sees the
sender's nickname.
You can also tuck in up to 3 neighbors a day — people shown in the ranking who are not your friends — and
the recipient sees your nickname on their screen and in the notification. If you do not want this, you can
block or report that person.

**Rescuing with a postpone pass:** you can use one of your own postpone passes to rescue a
friend or a member of your party who went over their step limit that day. We store who
rescued whom, the date concerned, the time, and when the rescued person saw it, and that
day is recorded as exempt for the rescued person. The rescuer's nickname is shown on the
rescued person's screen. If the rescuer deletes their account, only the rescuer is removed
from that record.

**Removing and blocking:** you can remove or block a friend at any time. Doing so deletes
the friendship and any unseen blankets between you; blocking also deletes pending party
invitations between you. A block record (who blocked whom) is kept until account deletion
so the two accounts cannot become friends again; the other person is not notified.
People you block are hidden from your ranking screen, and only you can see your block
list. If you are in the same blanket party, you remain visible to each other in the party
until one of you leaves. In party chat, however, you and a person you blocked do not see each other's messages.

To prevent code guessing, we count failed code entries and code regenerations **per day
only** and delete older counts.

**Blanket party:** 2–5 friends can join one "party" (one party per person). We store the
party, its members and when they joined, and who created it. Members of the same party
can see each other's **nickname, most recent day's steps and step limit, and
decorations**; the party streak (consecutive days everyone stayed under their limit) is
calculated from these records when needed and is not stored separately. Accepting an
invitation and joining a party is your agreement to share this with the party; you can
leave at any time. A party is deleted when its last member leaves.
When a member leaves or is removed, we keep **their membership period (the days they joined and left),
how they left (on their own or removed), and their step count and step limit on the day they left** with that
party, so the days they were a member still count toward the party streak. This record is not shown to other
members, is used only to calculate the party streak, and is deleted 92 days after the day they left or when the
party no longer exists.
When a member deletes their account, the party keeps only **anonymous per-day success/failure marks** (with no identifier)
for up to 92 days so the party record stays fair, and the remaining members see a one-time notice that does not say who left
(the notice record is deleted once shown or after 7 days).
The party's host can remove other members. When a member is removed, the party chat messages
they wrote are deleted, just as when they leave on their own, and we keep the fact that they
were removed (the time only; we do not store who removed them) so the app can tell them once.
This record is deleted as soon as it is shown or the person joins a party again; otherwise it is
no longer shown after 7 days and is deleted within a day after that. If the host has no step records for more than 30 days, the
host role passes to the next member.

**Party invitations:** when you invite a friend to a party, we store the inviter, invitee
and time. The invitee sees the inviter's nickname and the party's member count.
Invitations cannot be accepted after 7 days and are deleted once accepted or declined.

**Party chat:** Members of the same blanket party can exchange messages. When you send a message you
wrote (up to 200 characters) or a quick phrase prepared by the app, the server stores **the message
content, the sender, and the time sent**, how far each member has read, and the time a party chat notification was last sent to them (so it is not sent repeatedly). Messages are visible only
to members of the same party, and a member who joins later sees only messages sent after joining.
Messages are **deleted automatically after 7 days**, and your messages are deleted immediately when you
leave the party or delete your account. You can delete your own messages at any time. Messages
containing words on the operator's blocklist are not saved, and violating the rules may suspend your
ability to send messages for a period (the server stores that end date). Whether you agreed to the
promise shown the first time you open the chat is stored only on your device. How many times you have
sent each quick phrase is stored only on your device, to show the ones you use most first, and is not sent
to our server. Usage statistics record only that the chat was opened and that a message was sent (typed or
quick phrase, and for a quick phrase which pack it came from), never which phrase or its content.

**Invite rewards:** within 7 days of your account being created, you can enter another
user's invite code once; both of you receive fluff (in-app points that cannot be exchanged for money).
To prevent double rewards and abuse, we store who entered whose code, when, and whether
the reward was given. The code owner only sees **how many people** used their code.

### 3.8 Reports

If you see an inappropriate nickname or spam (for example in the ranking), you can report
that user; if you find an inappropriate message in party chat, you can report that message.
Reports are used to handle inappropriate nicknames, messages and spam in line with the
user-generated content policies of the app stores (App Store and Google Play).

- **What we store:** the reporter, the reported user, the reason (nickname / spam /
  other), the reported user's nickname at the time of the report, the report time and
  the time it was resolved.
- **Who can see it:** only the operator. The reported user is not told who reported them.
  You can report the same user only once, and there is a daily limit on reports.
- **Automatic action:** if 3 different users report the same user's nickname, that
  nickname is automatically changed to the default nickname ("침대늘보" followed by the
  first 6 characters of the account identifier). Spam and other reports are reviewed and
  handled by the operator.
- **Retention:** if either the reporter or the reported user deletes their account, the
  related report records are deleted with it.
- **Stored for a message report:** the reporter, the author, the reason (insults or harassment /
  sexual content / spam / other), **the message content at the time of the report**, the time of the
  report, and the time it was handled. The content kept in the report remains for handling even after
  the original message is deleted.
- **Automatic action on messages:** a reported message disappears from the reporter's screen right
  away, and when 2 different people report the same message it is deleted for all members. There is a
  daily limit on reports.
- **Operator alert:** the operator is alerted when a report is filed. The alert contains only the
  report number, the reason and whether the message was automatically deleted — no message content,
  nickname, or account identifier.

### 3.9 Detection of abnormal use

To keep rankings and streaks fair and to prevent record manipulation, once a day our server analyzes step records to find abnormal usage patterns (for example, 15 or more consecutive days with zero steps, many past days filled in at once with near-zero step counts, or repeated trimming of limits) and records internal flags. Only step records are analyzed, and these flags are kept for **90 days** and deleted together with your account. When flags appear, the operator is notified, but the notification contains **only the number of flags per kind** — no nickname, account identifier or step count. No automatic sanction is applied based on a flag alone; a person reviews it first.

## 4. Permissions

| Permission | Why we need it | If you deny it |
|---|---|---|
| Physical activity / Motion & Fitness | Counts your steps | Steps are not recorded |
| Health data (steps) read | Adds steps measured by other devices and apps | Only this device's sensor is used |
| Background health data read (Android) | Checks for exceeded limits while the app is closed | Checked only when you open the app |
| Notifications | Sends limit-exceeded notifications | You won't receive notifications |
| App tracking (iOS) | Used for personalized ads | Non-personalized ads are shown |
| Add to photo library (optional) | Saves share cards to your photo album | You can share cards but not save them |
| Storage write (Android 10 and below only) | Saves share cards to your gallery | You can share cards but not save them |

**You can use the app even if you deny any permission.** Only the related feature
stops working.

## 5. Third-party processing

We **do not sell** the information we collect. We entrust processing to the
following companies to the extent needed to run the service.

| Processor | Task | Privacy policy |
|---|---|---|
| Supabase Inc. | Storing accounts, step records, weekday limits and abnormal-use flags, ranking, storing friend / party / party chat / decoration / achievement / Sloth Diary / exemption / report records, fluff purchase records and nickname wallets | https://supabase.com/privacy |
| Google LLC (Firebase Crashlytics / Analytics / Cloud Messaging) | Crash reports, usage statistics, delivering friend update notifications | https://policies.google.com/privacy |
| Google LLC (AdMob, UMP consent message) | Serving ads, verifying rewarded ad views, managing ad consent | https://policies.google.com/technologies/ads |
| RevenueCat, Inc. | Managing in-app purchase and subscription status | https://www.revenuecat.com/privacy |
| Google LLC (Sign-in) | Google account linking (only if you choose it) | https://policies.google.com/privacy |
| Apple Inc. (Sign in with Apple, APNs) | Apple account linking and token revocation on account deletion (only if you choose it), delivering friend update notifications on iOS | https://www.apple.com/legal/privacy/ |

### 5.1 International transfers

The processors above handle personal information outside your country. As required by
applicable laws, we disclose the following.

| Recipient | Country | Items | When and how | Retention |
|---|---|---|---|---|
| Supabase Inc. | South Korea (stored in the Seoul region). The processor is a US company and may access data from the US when needed, e.g. for troubleshooting | Account identifier, nickname, step records, limits (including weekday limits), abnormal-use flags, friend / party / party chat content / decoration / achievement / Sloth Diary / exemption / report records (including message content kept in message reports), fluff purchase records, nickname wallets and piece records, (if linked) Google / Apple account identifier and email, Apple refresh token and related information | Whenever you use the app, over an encrypted network connection | Until account deletion (except as described in section 7) |
| Google LLC (Firebase, AdMob, Sign-in) | United States | Device information, crash records, usage statistics, advertising ID, (if linked) Google account information, (if you watch rewarded ads) a random verification code, (if friend updates are on) push token and notification text (the sender's nickname) | Whenever you use the app, encrypted | Per each company's policy |
| RevenueCat, Inc. | United States | Account identifier, purchase and subscription status | When you make a purchase, encrypted | Per each company's policy |
| Apple Inc. (Sign in with Apple, APNs) | United States | (if linked) sign-in requests, token revocation request on account deletion, (if friend updates are on, on iOS) push token and notification text (the sender's nickname) | When you link or delete, and when a notification is delivered, encrypted | Per each company's policy |

If you do not want your data transferred abroad, you can stop using the app and delete
your account. In that case you will not be able to use the service.

## 6. Recommended products (affiliate links)

When your device region is Korea, the app's "Homebody Picks" section shows Coupang
products as part of the Coupang Partners program, and we receive a commission through
it. Tapping a product link takes you to the Coupang website or app, and any processing
of information after that follows Coupang's privacy policy. These are products from
Coupang Korea and are ordered and shipped only within Korea.

Outside Korea and Japan, the section may show affiliate links from the Amazon
(amazon.com) Associates program. As an Amazon Associate I earn from qualifying
purchases. After you tap a link, Amazon's privacy notice applies. No recommended
products are shown in the Japan region.

To learn which picks are popular, the app records the **product name and recommendation
keyword** in usage statistics (Firebase Analytics) when you tap a product link. This
contains no name or contact details, and the app does not pass your information to
Coupang or Amazon.

**The "Homebody picks" screen is part of the Coupang Partners program, and we receive a commission from it.**

## 7. Retention and deletion

- Step records, nickname, streaks and similar data are kept **until you delete your
  account.**
- When you delete your account, your step records, nickname, limits, weekday limit settings and limit adjustment records, abnormal-use flags, streaks and
  badges, achievements, Sloth Diary progress and story rewards, Streak Savers, postpone passes and exemption records, subscription status, quests and fluff (including fluff purchase records), nickname wallet (passes and pieces) and ad piece records and verification codes, story bonus and decoration try-on records, decorations, friends / blocks / blankets, records of being rescued,
  party membership (including records of parties you left) and invitations, party chat messages you wrote and your read position, and any chat restriction record, invite code, reports you made or received, your device upload keys, and your
  linked Google / Apple account information and Apple refresh token are
  **deleted immediately** (we ask Apple to revoke the Apple token right before deletion). You can do this inside the app (see
  [Account deletion](account-deletion-en.md)).
- However, the following records remain after you delete your account:
  - **Invite reward records:** kept so the other person keeps the reward they already
    received and the invite reward limit still works, but your deleted account's
    identifier is removed so the record no longer shows whose it was.
  - **Blanket parties:** if other members remain in a party you created, the party
    continues for them and only the "created by" information is removed. If you were a party member, that party keeps
    only anonymous per-day success/failure marks (with no identifier) for up to 92 days (see §3.7).
  - **Payment records:** in-app payment notification records (event ID, store transaction ID, product, the
    account identifier string at the time, time, including fluff pack and Nickname Pass payments) are kept for **5 years** as records of
    payment and supply of goods under Korea's Act on the Consumer Protection in
    Electronic Commerce, and then deleted. They are unlinked from your account but the
    account identifier string at the time remains, and they are not used for any purpose
    other than this legal retention.
  - **Ad reward verification records:** records of watching an ad to postpone today (ad
    reward transaction ID, date, step count, result, time) are kept for support and to
    prevent double rewards, but your deleted account's identifier is removed so the record
    no longer shows whose it was.
  - Purchase records held by Google / Apple / RevenueCat follow their own policies.
- Crash reports (Firebase Crashlytics) are deleted automatically after 90 days, and user-level usage
  statistics (Firebase Analytics) after at most 14 months.
- The push token, app language, time zone, and party chat notification setting are kept until you turn off "Friend updates" or delete your
  account, or for 90 days after you last opened the app.
- Party chat messages are deleted automatically **7 days after they are sent**.
- Records of members who left or were removed from a party (membership period, how they left, and their step count and
  step limit on the day they left) are deleted automatically **92 days after the day they left** (earlier if the account
  is deleted or the party no longer exists).
- Limit adjustment records are deleted automatically after **30 days**, and abnormal-use flags after **90 days** (earlier if you delete your account).

## 8. Your rights

You can do the following at any time:

- **Access and correct** — Change your nickname and step limit directly in the app (after the first free change, a nickname change needs a pass, but resetting to your default nickname is always free).
- **Delete** — Deleting your account in the app's Settings erases your records on the
  server (except the remaining records listed in section 7). If you have already removed the app, you can request deletion by
  email as described on the [Account deletion](account-deletion-en.md) page.
- **Withdraw consent** — Turning off a permission in your device settings stops the
  related collection.
- **Opt out of personalized ads** — Use your device's ad ID reset / limit tracking
  settings.

## 9. Children's privacy

The app is not directed at children under 14 and does not knowingly collect
children's personal information. If we learn that a child's information has been
collected, we will delete it without delay.

## 10. Security

- All communication with the server is encrypted (HTTPS).
- The database uses row-level security (RLS) so that **users can access only their
  own records and the information this policy says is visible to other users (ranking,
  friends, parties).**
- Along with nickname, character and step count, the ranking sends the app a **random
  account identifier** for each entry. It is not shown on screen; the app uses it
  internally (for example, to highlight your own rank and to choose whom to report or
  block). It does not reveal your name or contact details.

## 11. Changes to this policy

If this policy changes, we will notify you through an in-app notice or an update.
Important changes will be announced at least 7 days before they take effect.

## 12. Contact

- Privacy officer: Representative, 그이어 (GoWeAre)
- Contact: go.we.are.official@gmail.com
