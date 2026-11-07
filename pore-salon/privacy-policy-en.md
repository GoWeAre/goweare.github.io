# Pore Salon Simulator — Privacy Policy

**Go We Are** ("we") provides the mobile game **Pore Salon Simulator** (the "Game"). The Game is offered as an Android/iOS app (the "mobile app") and as a version that runs inside the Toss app (Apps in Toss, the "Toss version").

**Effective date:** 2026-11-08

## 1. Information we collect and why

The Game never asks for your name, phone number, address or location.

- The mobile app can be played without signing in. If you want, you can link a Google or Apple account to back up your progress (see e).
- The Toss version has no sign-in screen. When the Game starts, an account is created automatically from the user key Toss issues to this Game, and your progress is saved automatically (see f).

**a. Stored on your device**

- Stars per stage, best Endless score, best records (length/amount extracted), coins and the looks you picked in the shop, hearts, Daily Guest records, and whether you have seen story scenes and tips
- Settings such as language, sound, vibration, art style, skin tone, customer reactions and heart notifications
- The ranking key and nickname (see b), scores not yet sent, nicknames you chose to hide, and an update version you chose to skip
- A token that keeps you signed in, and on the Toss version a list of purchase order numbers (see g)
- These are removed from your device when you uninstall the Game or clear its data. Progress saved to an account (see e and f) stays on our server.
- On iOS, reinstalling the Game signs you out. Sign in again to get your account's progress back.

**b. Weekly ranking and nicknames — mobile app and Toss version**

When an Endless run starts, the Game sends its ranking key and platform to obtain a play token. When it ends, the Game sends the following to our ranking server. The mobile app (Android and iOS together) and the Toss version have separate rankings.

| Item | What it is | Purpose |
|---|---|---|
| Ranking key (`user_key`) | A random value (UUID) created on your device the first time the Game runs. Not an advertising ID or hardware ID | Keep your records together so they can be ranked |
| Nickname | At first a random name chosen by the Game (e.g. "GlowyPeach", "mochi93"); you can change it to anything 2–12 characters long | Shown on the ranking |
| Score | Endless score (mg), your best this week and your all-time best | Ranking, "My best" |
| Platform | android, ios or toss | Separating rankings, server operation |
| Timestamps | First/last submission time, time of best score, time of the last rename | Breaking ties, limiting overly frequent requests |
| Play verification | Server token, play duration, and the sequence of lesion kinds, outcomes and jackpots | Recalculating scores and preventing tampering/reuse. The DB stores a token hash, start/expiry times, submitted score, duration and event count, but not individual events |
| Connection address hash | A server-secret hash of the gateway-provided IP, request count and expiry time | Limiting excessive ranking, rename, report, invite and Toss account requests. The original IP is not stored |

- **Other players see only nicknames and scores (ranks).** The ranking key is never shown. The ranking also includes rows for regular customers, who are fictional characters made by the Game.
- When you change your nickname, all of your ranking rows, including past weeks, show the new name. Nicknames may not impersonate the operator or contain profanity, sexual or hateful expressions.
- **Reporting a nickname:** when you report another player's nickname, we store the ranking keys of the reporter and the reported player, the reported nickname, the week, the time of the report and how it was handled. The reported nickname and a ranking reference are sent to an operator notification channel (Discord) so we can review it. A nickname reported by five different players is automatically reset to "#" plus five digits, and the operator may reset an inappropriate nickname or hide it from the ranking.
- Nicknames you choose to hide are stored only on your device.
- The Game also keeps a token and event sequence on the device for submission retries. Offline runs started without a server token remain local records only.
- Our hosting provider may process connection data such as your IP address when the Game talks to the server. What is logged and for how long is governed by the hosting provider's (Supabase) policy (section 4).

**c. Update check — mobile app only**

When the Game starts (or returns after a long break) it asks the server whether a newer version exists. It sends **only the platform (android/ios)** — nothing that identifies you. The version comparison happens on your device.

**d. Device features**

- Vibration (haptics) and the rating prompt (mobile app; the in-app review feature of Google Play or the App Store) only call a device or store feature. We receive no information from them.
- Heart notifications (mobile app, only if you turn them on) are scheduled on your device and send nothing to our server. On Android 13 and later the Game asks for notification permission.
- The check that stops hearts from being refilled by moving the device clock forward is calculated only on your device.

**e. Linking an account and backup — mobile app only, optional**

If you sign in with a Google or Apple account under Settings or MY → Link account, we keep the following on our server so that you can continue on another device or after reinstalling. While you are signed in, your progress is backed up automatically. Nothing here is collected unless you sign in.

| Item | What | Why |
|---|---|---|
| Account identifiers | The user identifier Google or Apple issues to this Game, and an account ID created by our server | Keep one person's progress in one account |
| Email address | The email passed by the sign-in service (Apple's relay address if you choose "Hide My Email") | Link Google and Apple sign-ins that share an email; shown partly masked in Settings |
| Sign-in profile | With Google sign-in, the name and profile picture address that Google sends along may remain in the sign-in record. The Game does not display them or use them for anything else | Processing the sign-in |
| Game progress | From 1-a: stars per stage, best scores and records, coin earnings and spending, looks you own and wear, skin tone, whether you have seen story scenes and tips, customer review log, claimed awards and running counts of treatments and requests, rename tickets and pieces, invite rewards, the ranking key and nickname, and coins, Remove Ads and rename tickets from purchases | Continue on another device |
| Sign-in tokens | A session token (kept on your device only) and a token used to disconnect Sign in with Apple (kept on our server) | Stay signed in; disconnect Apple when you delete your account |

- We never receive or store your password. You sign in on Google's or Apple's own screen.
- Settings such as language, sound, vibration, art style, customer reactions, hearts and heart notifications are not backed up and stay on the device.
- When you sign out, that device's progress is saved to your account and then removed from the device.
- Deleting your account: Settings or MY → Link account → Delete account (type "DELETE" to confirm). Section 5 explains what is deleted.

**f. Toss version account and automatic saving — Toss version only**

- When the Game starts, it gets a one-time authorization code from the Toss app and sends it to our server. The server checks the code with Toss (Viva Republica), receives the **user key** Toss issues to this Game, and finds or creates a game account from a hash of that value. The original user key is not stored.
- The user key only tells users apart. It is not your name, phone number or other Toss member information, and the Game does not ask Toss for such personal information.
- The account automatically saves the same items as "Game progress" in 1-e (except invite rewards). Your progress continues if you open the Game on another device with the same Toss account or reinstall it.
- Ranking, nicknames and reports on the Toss version work as in 1-b (platform toss).
- The sign-in token is kept in the device's web storage.

**g. Purchase records**

- Mobile app: payments are processed by Google Play or the App Store, and receipts are validated and purchase notifications delivered through RevenueCat. Our server keeps the product, time of purchase, store transaction ID and the link to your account.
- Toss version: payments are processed by Toss. After you pay, the Game sends the order number to our server, which checks the order status with Toss and then adds the item to your account. Our server keeps the order number, product, time of purchase and the link to your account. The device keeps the numbers of orders still to be processed, orders already processed, and orders whose refund has been checked.
- We never receive payment details such as card numbers.

**h. Inviting friends — mobile app only**

- When you create or enter an invite code, the Game sends the ranking key and the code to our server. If you enter a code while signed in, your account ID is recorded too.
- Our server keeps the ranking keys of the inviter and the invitee, the code, when the code was entered, when the condition (clearing stage 5) was met, and the rewards given. This is to stop the same person from claiming rewards more than once.
- Invite links are shared using your device's share feature and clipboard. We do not know whom you sent them to.

**i. Google Play Games — Android app only**

The Android app tries to sign in to Google Play Games when it starts, and sends achievements and gameplay events (stage number, treatments, clean treatments, stars, best combo, progress) to Google Play Games. Google processes this under its own policies, and you can manage your profile and visibility in the Play Games app. We do not combine it with ranking or account data.

**j. Toss event log — Toss version only**

To improve the service, the Toss version sends gameplay records to Toss through the Apps in Toss event log feature:

- Game start (hearts, coins, stage)
- Stage start, clear, failure and quit
- End of an Endless run (score, duration)
- Opening, using and closing the heart window
- Detection of a device clock change
- Ad shown (type, placement)
- Shop purchase (item, price, coins)
- Aftercare completed
- Response to the notification permission request

No name or account information is included. We see these as statistics in the Toss console.

## 2. Advertising

The Game **contains ads**.

- Interstitial ads appear occasionally when moving to the next stage, restarting Endless, or leaving Practice after more than a minute.
- Rewarded ads play only when you choose to watch one: "2× coins", "continue" in Endless, rename ticket pieces, Practice reward coins, and getting a heart.
- Buttons that play an ad are marked with an ad icon.

**Mobile app: Google AdMob**

- Ads are loaded and shown by Google LLC's Google Mobile Ads SDK (AdMob). **Google** may collect and process the following to serve and measure ads and prevent fraud:
  - Advertising identifiers (such as the Android Advertising ID, and on iOS the IDFA only if you allow tracking)
  - IP address (to estimate general location)
  - Ad interactions such as impressions and clicks
  - Device and diagnostic information
- We do not receive this information directly and do not combine it with ranking or account data.
- How Google uses data: Google Privacy Policy <https://policies.google.com/privacy>, How Google uses information from sites or apps that use its services <https://policies.google.com/technologies/partner-sites>
- To limit personalised ads:
  - Android: you can reset or delete your advertising ID in device settings (Google → Ads).
  - iOS: the app asks once for App Tracking Transparency (ATT) permission before ads are first prepared. If you decline, the game and ads continue without the IDFA (less personalised ads). You can change this any time in Settings → Privacy & Security → Tracking.
  - Menu names may differ by OS version.
- Where consent is required (e.g. the EEA and UK), Google's consent form (UMP) is shown before ads are requested, and ads are requested only as your consent allows. You can change your choice any time under Settings → "Privacy options".
- If you are in a US state that gives you the right to opt out of the "sale" or "sharing" of personal information (such as California), you can opt out of selling or sharing your information for targeted advertising under Settings → "Privacy options". This button appears only where such a choice is required. See also section 7.

**Toss version: Toss ads**

- Ads are shown through the Apps in Toss ad feature, and ad-related data is handled under Viva Republica (Toss)'s policies. We do not receive information that identifies who viewed an ad; we only see aggregate ad statistics that cannot identify a person.

## 3. Host platform (Toss app)

The Toss app's own data handling is governed by **Viva Republica (Toss)'s privacy policy**. The only information the Toss version exchanges with Toss is what is described in 1-f (user key), 1-g (order checks), 1-j (event log) and section 2 (ads). The Toss version does not use 1-c (update check), 1-h (invites) or 1-i (Play Games).

## 4. Processors and third parties

| Recipient | Role | Data | Applies to |
|---|---|---|---|
| Supabase, Inc. | Hosting for the ranking, nickname, report, update-check, account and progress, purchase record and invite server (processor) | Items in 1-b, 1-c, 1-e, 1-f, 1-g and 1-h, connection data | Mobile app and Toss version |
| Discord Inc. | Delivering nickname report notifications to the operator (processor) | The reported nickname and a ranking reference | Mobile app and Toss version |
| Google LLC, Apple Inc. (sign-in) | Verify who you are with the account you choose (processed under their own policies) | The sign-in request and its result (account identifier, email, and for Google your name and profile picture) | Mobile app, only if you sign in |
| Google LLC (AdMob) | Advertising (processed under Google's own policies) | Ad data in section 2 | Mobile app |
| Google LLC (Play Games) | Achievements and gameplay records (processed under Google's own policies) | Data in 1-i | Android app |
| RevenueCat, Inc. | In-app purchase receipt validation and purchase notifications (processor) | Purchase records (product, time of purchase, store transaction ID), an app user ID for purchases (your account ID if signed in, otherwise an anonymous ID) | Mobile app |
| Viva Republica (Toss) | Host platform, issuing and checking the user key, payments and order checks, ads, event log | Data in section 3 | Toss version |

- Supabase privacy policy: <https://supabase.com/privacy>. Server location: Republic of Korea (Seoul region). The hosting provider (Supabase, a US company) may access the server while operating or supporting the service.
- Discord privacy policy: <https://discord.com/privacy>. Report notifications pass through Discord's servers (United States) on their way to our operator.
- RevenueCat privacy policy: <https://www.revenuecat.com/privacy>.
- We do not sell or otherwise provide your information to anyone else.

## 5. Retention and deletion

- **On-device data (1-a):** stays on your device until you uninstall the Game or clear its data.
- **Accounts and saved progress (1-e, 1-f):** kept until you delete your account. When you delete it, we immediately delete:
  - The account, saved progress, that account's ranking and nickname records and play tokens, your invite code, and the Apple connection
  - The progress left on that device
- The following remain after deletion, changed so that they no longer identify you:
  - The invite ledger, so that the same person cannot claim rewards again. A new random value or a hash replaces your identifier.
  - Nickname report records. The reporter's and reported player's identifiers are replaced with new random values; the reported nickname and how it was handled remain.
  - Purchase records, with the link to your account removed.
- **Purchase records:** kept for 5 years for refunds and as required by law (the Korean Act on Consumer Protection in Electronic Commerce), then deleted. Payment records held by RevenueCat follow RevenueCat's policy.
- **Play tokens and IP hashes:**
  - Play tokens expire after seven days. Each later start request cleans up at most 100 expired sessions.
  - IP-hash counters are cleaned up a day after they expire, at most 100 per later request.
  - Cleanup can be delayed when there are no requests.
- **Ranking data (1-b):** the ranking starts fresh every Monday at 0:00 (KST), but **past weeks' rows and each player's all-time best row are not deleted automatically and remain on the server.**
  - If you play the mobile app without signing in, uninstalling the Game does not remove server records. A reinstall creates a new ranking key.
  - We delete these records when you delete your account or ask us to (section 7). Otherwise we delete them when the ranking service ends.

## 6. Children

The Game is not primarily directed to children and does not ask for names, contact details or other information that identifies a child. The ad SDK may still process the data described in section 2.

## 7. Your rights

- You can remove on-device records by uninstalling the Game or clearing its data.
- **Signed in on the mobile app:** you can delete your account, saved progress and ranking records yourself in Settings or MY → Link account → Delete account.
- **Toss version:** there is no account deletion menu in the Game. Email us (section 8) with the subject "Toss version account deletion". To confirm it is you, tell us the nickname shown on the Game's MY screen and roughly when you last played. After checking, we delete your data as described in section 5.
- **Not signed in on the mobile app:** ranking records on our server (1-b) cannot be viewed or deleted in the Game. Contact us (section 8) with your nickname and roughly your score and date, and we will delete the records we can identify.
- You can also ask us for access, correction or restriction of processing via section 8. You can change your nickname yourself in the Game.
- For advertising identifier choices, see section 2.
- **US state privacy rights (California and others)**
  - We do not sell your information for money. However, Google (AdMob) collecting advertising identifiers, IP address and ad interactions (section 2) for targeted ads in the mobile app may count as a "sale" or "sharing" of personal information under some state laws.
  - You can opt out under Settings → "Privacy options". You can request access to or deletion of your data in the ways above or via the contact in section 8.
  - We will not discriminate against you for exercising these rights.
  - We do not collect sensitive personal information, and we do not knowingly sell or share the information of users under 16.

## 8. Contact

- Company: Go We Are
- Privacy officer: Representative of Go We Are
- Email: go.we.are.official@gmail.com
- Data and account deletion requests: go.we.are.official@gmail.com (subject e.g. "Ranking data deletion", "Toss version account deletion")

## 9. Changes

We will announce changes on the store page or in the Game before they take effect. Previous version effective: 2026-10-16.
