---
lang: en
---

# BedSloth Privacy Policy

**Last updated: 2026-10-05**
**Effective date: 2026-10-05**

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
| Nickname | Shown in the ranking, to friends and in parties | Yes — ranking (top 100), friends, party members, people you invite to a party |
| Daily step limit | Threshold for "limit exceeded" notifications. Each day's limit is stored on the server with that day's steps | Yes — friends and party members |

You start with an automatic nickname ("침대늘보", Korean for "BedSloth", followed by the
first 6 characters of your random account identifier) and can change it in Settings
(1–20 characters). Your nickname is **visible to other users**, so please don't use
your real name, contact details or anything that could identify you.

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

### 3.3 App usage records

| Item | Purpose |
|---|---|
| Streak records and badges | Providing features |
| Postpone passes / Streak Savers owned and used | Providing features |
| Today's exemption record (date, whether it came from a postpone pass or an ad, and for an ad the step count at that moment) | Judging streaks and party streaks |
| Achievement unlocks (achievement, time unlocked) | Achievements and their rewards |
| "Not-to-do" quest completions (date, quest) | Calculating fluff rewards |
| Decoration purchases (item, fluff spent, time) | Decoration feature, fluff balance |
| Equipped decorations | Shown in your room and **to your friends and party members** |

Your fluff (in-app points) balance is not stored; it is calculated from these records
and invite reward records. Fluff cannot be exchanged for money and is unrelated to
payments.

#### Information stored only on your device

Your weekday step limits, the last date you opened the app (for reminders to users who
haven't opened it for a while), notification history, whether the app has
asked you for a rating, which "Not-to-do" settlements you have seen, and today's steps for the home-screen widget are stored **only on your device**
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
  our server after payment, and the server records that notification (event ID,
  product, account identifier, time) to prevent double delivery. **The app never
  receives or stores card numbers or other payment details**; Google/Apple process
  payments directly.
- **Access logs** — When the app communicates with our server, access records such as
  your IP address and request time are logged by our server provider (Supabase). They
  are used only for security and troubleshooting and are deleted automatically after
  **7 days**.

**We do not use a push server.** All notifications are local notifications created
on your device; we do not collect remote push tokens such as Firebase Cloud
Messaging tokens.

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

**Removing and blocking:** you can remove or block a friend at any time. Doing so deletes
the friendship and any unseen blankets between you; blocking also deletes pending party
invitations between you. A block record (who blocked whom) is kept until account deletion
so the two accounts cannot become friends again; the other person is not notified.
People you block are hidden from your ranking screen, and only you can see your block
list. If you are in the same blanket party, you remain visible to each other in the party
until one of you leaves.

To prevent code guessing, we count failed code entries and code regenerations **per day
only** and delete older counts.

**Blanket party:** 2–5 friends can join one "party" (one party per person). We store the
party, its members and when they joined, and who created it. Members of the same party
can see each other's **nickname, most recent day's steps and step limit, and
decorations**; the party streak (consecutive days everyone stayed under their limit) is
calculated from these records when needed and is not stored separately. Accepting an
invitation and joining a party is your agreement to share this with the party; you can
leave at any time. A party is deleted when its last member leaves.

**Party invitations:** when you invite a friend to a party, we store the inviter, invitee
and time. The invitee sees the inviter's nickname and the party's member count.
Invitations cannot be accepted after 7 days and are deleted once accepted or declined.

**Invite rewards:** within 7 days of your account being created, you can enter another
user's invite code once; both of you receive fluff (in-app points with no cash value).
To prevent double rewards and abuse, we store who entered whose code, when, and whether
the reward was given. The code owner only sees **how many people** used their code.

### 3.8 Reports

If you see an inappropriate nickname or spam (for example in the ranking), you can report
that user. Reports are used to handle inappropriate nicknames and spam in line with the
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
| Supabase Inc. | Storing accounts and step records, ranking, storing friend / party / decoration / achievement / exemption / report records | https://supabase.com/privacy |
| Google LLC (Firebase Crashlytics / Analytics) | Crash reports, usage statistics | https://policies.google.com/privacy |
| Google LLC (AdMob, UMP consent message) | Serving ads, verifying rewarded ad views, managing ad consent | https://policies.google.com/technologies/ads |
| RevenueCat, Inc. | Managing in-app purchase and subscription status | https://www.revenuecat.com/privacy |
| Google LLC (Sign-in) | Google account linking (only if you choose it) | https://policies.google.com/privacy |
| Apple Inc. (Sign in with Apple) | Apple account linking and token revocation on account deletion (only if you choose it) | https://www.apple.com/legal/privacy/ |

### 5.1 International transfers

The processors above handle personal information outside your country. As required by
applicable laws, we disclose the following.

| Recipient | Country | Items | When and how | Retention |
|---|---|---|---|---|
| Supabase Inc. | South Korea (stored in the Seoul region). The processor is a US company and may access data from the US when needed, e.g. for troubleshooting | Account identifier, nickname, step records, limits, friend / party / decoration / achievement / exemption / report records, (if linked) Google / Apple account identifier and email, Apple refresh token and related information | Whenever you use the app, over an encrypted network connection | Until account deletion (except as described in section 7) |
| Google LLC (Firebase, AdMob, Sign-in) | United States | Device information, crash records, usage statistics, advertising ID, (if linked) Google account information, (if you watch an ad to postpone today) a random verification code | Whenever you use the app, encrypted | Per each company's policy |
| RevenueCat, Inc. | United States | Account identifier, purchase and subscription status | When you make a purchase, encrypted | Per each company's policy |
| Apple Inc. (Sign in with Apple) | United States | (if linked) sign-in requests, token revocation request on account deletion | When you link or delete, encrypted | Per each company's policy |

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
- When you delete your account, your step records, nickname, limits, streaks and
  badges, achievements, Streak Savers, postpone passes and exemption records, quests and fluff, decorations, friends / blocks / blankets,
  party membership and invitations, invite code, reports you made or received, and your
  linked Google / Apple account information and Apple refresh token are
  **deleted immediately** (we ask Apple to revoke the Apple token right before deletion). You can do this inside the app (see
  [Account deletion](account-deletion-en.md)).
- However, the following records remain after you delete your account:
  - **Invite reward records:** kept so the other person keeps the reward they already
    received and the invite reward limit still works, but your deleted account's
    identifier is removed so the record no longer shows whose it was.
  - **Blanket parties:** if other members remain in a party you created, the party
    continues for them and only the "created by" information is removed.
  - **Payment records:** in-app payment notification records (event ID, product, the
    account identifier string at the time, time) are kept for **5 years** as records of
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

## 8. Your rights

You can do the following at any time:

- **Access and correct** — Change your nickname and step limit directly in the app.
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
