# Pore Salon Simulator — Privacy Policy

**Go We Are** ("we") provides the mobile game **Pore Salon Simulator** (the "Game").

**Effective date:** 2026-10-11

## 1. Information we collect and why

You can play without signing in, and the Game never asks for your name, phone number or location. In the Android/iOS app you may choose to sign in with a Google or Apple account to back up your progress (see e).

**a. Stored only on your device (never sent to us)**

- Stars per stage, best Endless score, best records (length/amount extracted), coins and the looks you picked in the shop, settings such as language, sound and skin tone, whether a tip has been shown
- The ranking device key and auto nickname (see b), an Endless score from this week not yet sent, and an update version you chose to skip
- These are deleted when you uninstall the Game or clear its app/browser data. Progress you backed up by signing in (see e) stays in your account.

**b. Weekly ranking — Android/iOS app only**

When an Endless run starts, the Game sends its device key and platform to obtain a play token. When it ends, the Game sends the following to our ranking server.

| Item | What it is | Purpose |
|---|---|---|
| Device key (`user_key`) | A random value (UUID) created on your device the first time the Game runs. Not an advertising ID or hardware ID | Keep your records together so they can be ranked |
| Auto nickname | "#" plus four digits (e.g. #0042), chosen at random by the Game — you never type it | Shown on the ranking ("Guest #0042") |
| Score | Endless score (mg), your best this week and your all-time best | Ranking, "My best" |
| Platform | android or ios | Server operation |
| Timestamps | First/last submission time, time of best score | Breaking ties, limiting overly frequent submissions |
| Play verification | Server token, play duration, and the sequence of lesion kinds, outcomes and jackpots | Recalculating scores and preventing tampering/reuse. The DB stores a token hash, start/expiry times, submitted score, duration and event count, but not individual events |
| Connection address hash | A server-secret hash of the gateway-provided IP, request count and expiry time | Limiting excessive requests across changing device keys. The rate-limit DB does not store the original IP |

- **Other players see only nicknames and scores (ranks).** The device key is never shown.
- The Game also keeps a token and event sequence on the device for submission retries. Offline runs started without a server token remain local records only.
- When you open the ranking, the Game sends the device key to find your own rank.
- Our hosting provider may process connection data such as your IP address when the Game talks to the server. What is logged and for how long is governed by the hosting provider's (Supabase) policy (section 4).

**c. Update check — Android/iOS app only**

When the Game starts (or returns after a long break) it asks the server whether a newer version exists. It sends **only the platform (android/ios)** — nothing that identifies you. The version comparison happens on your device.

**d. Vibration (haptics)** only calls a device/platform feature; we receive no information from it.

**e. Sign-in and backup — Android/iOS app only, optional**

If you sign in with a Google or Apple account under Settings → Back up progress, we keep the following on our server so that you can continue on another device or after reinstalling. Nothing here is collected unless you sign in.

| Item | What | Why |
|---|---|---|
| Account identifiers | The user identifier Google or Apple issues to this Game, and an account ID created by our server | Keep one person's progress in one account |
| Email address | The email passed by the sign-in service (Apple's relay address if you choose "Hide My Email") | Link Google and Apple sign-ins that share an email; shown partly masked in Settings |
| Game progress | From 1-a: stars per stage, best scores and records, coin earnings and spending, looks you own and wear, skin tone, whether a tip has been shown, customer review log, claimed awards and running counts of treatments and requests, the ranking device key and nickname | Continue on another device |
| Sign-in tokens | A session token (kept on your device only) and a token used to disconnect Sign in with Apple (kept on our server) | Stay signed in; disconnect Apple when you delete your account |

- We never receive or store your password. You sign in on Google's or Apple's own screen.
- Language, sound and customer-reaction settings are not backed up.
- When you sign out, that device's progress is saved to your account and then removed from the device.
- Deleting your account: Settings → Back up progress → Delete account. Your account, backed-up progress and that account's ranking records are deleted immediately and Sign in with Apple is disconnected. This cannot be undone.

## 2. Advertising

The Game **contains ads**: an occasional interstitial ad when moving to the next stage (or restarting Endless), and optional rewarded ads ("2× coins", "continue" in Endless). Buttons that play an ad are marked with an ad icon.

**Android/iOS app: Google AdMob**

- Ads are loaded and shown by Google LLC's Google Mobile Ads SDK (AdMob). **Google** may collect and process, to serve and measure ads and prevent fraud: advertising identifiers (such as the Android Advertising ID, and on iOS the IDFA only if you allow tracking), IP address (to estimate general location), ad interactions such as impressions and clicks, and device and diagnostic information.
- We do not receive this information directly and do not combine it with ranking data.
- How Google uses data: Google Privacy Policy <https://policies.google.com/privacy>, How Google uses information from sites or apps that use its services <https://policies.google.com/technologies/partner-sites>
- To limit personalised ads: on Android you can reset or delete your advertising ID in device settings (Google → Ads). On iOS the app asks once for App Tracking Transparency (ATT) permission before ads are first prepared. If you decline, the game and ads continue without the IDFA (less personalised ads); you can change this any time in Settings → Privacy & Security → Tracking. Menu names may differ by OS version.
- Where consent is required (e.g. the EEA and UK), Google's consent form (UMP) is shown before ads are requested, and ads are requested only as your consent allows. You can change your choice any time under Settings → "Privacy options".

**Inside the Toss app (Apps in Toss): Toss ads**

- Ads are shown through the Apps in Toss ad feature, and ad-related data is handled under Viva Republica (Toss)'s policies. We do not receive information that identifies who viewed an ad; we only see aggregate ad statistics that cannot identify a person.

## 3. Host platform (Toss app)

When the Game runs inside the Toss app (Apps in Toss), the Toss app's own data handling is governed by **Viva Republica (Toss)'s privacy policy**.

- This version uses **Toss Game Center** for ranking: Endless scores are submitted to Toss Game Center and Toss shows the ranking screen, including how players are named.
- This version does not use 1-b (our ranking server) or 1-c (update check).
- The Game does not request a user identifier from Toss. The data used to submit scores and show rankings is handled by Toss.

## 4. Processors and third parties

| Recipient | Role | Data | Build |
|---|---|---|---|
| Supabase, Inc. | Hosting for the ranking, update-check, and account/backup server (processor) | Items in 1-b, the platform value in 1-c, items in 1-e, connection data | Android/iOS app |
| Google LLC, Apple Inc. (sign-in) | Verify who you are with the account you choose (processed under their own policies) | The sign-in request and its result (account identifier, email) | Android/iOS app, only if you sign in |
| Google LLC (AdMob) | Advertising (processed under Google's own policies) | Ad data in section 2 | Android/iOS app |
| RevenueCat, Inc. | In-app purchase receipt validation and purchase notifications (processor) | Purchase records (product, time of purchase, store transaction ID), an app user ID for purchases (your account ID if signed in, otherwise an anonymous ID) | Android/iOS app |
| Viva Republica (Toss) | Host platform, ads, Game Center | Data in section 3 | Toss version |

- Supabase privacy policy: <https://supabase.com/privacy>. Server location: Republic of Korea (Seoul region, verified 2026-10-06). The hosting provider (Supabase, a US company) may access the server while operating or supporting the service.
- We do not sell or otherwise provide your information to anyone else.

## 5. Retention and deletion

- **Purchase records** (in-app purchases in the Android/iOS app): we keep the product, time of purchase and store transaction ID on our server. Payment details (such as card numbers) are handled by the store (Apple or Google) and never reach us. When you delete your account we remove the link between the purchase records and your account; the transaction records themselves are kept for 5 years for refunds and as required by law (the Korean Act on Consumer Protection in Electronic Commerce), then deleted. RevenueCat privacy policy: <https://www.revenuecat.com/privacy>.

- On-device data (1-a) stays on your device until you uninstall the Game or clear its data.
- Your account and backed-up progress (1-e) are kept until you delete your account, and are deleted immediately when you do.
- Play tokens expire after seven days; subsequent start requests clean up at most 100 expired sessions each. Subsequent requests clean up at most 100 IP-hash counters that expired more than a day ago. Cleanup can be delayed when there are no requests.
- Ranking data (1-b): the ranking starts fresh every Monday at 0:00 (KST), but **past weeks' rows and each player's all-time best row are not deleted automatically and remain on the server.** Uninstalling the Game does not remove server records (a reinstall creates a new device key). We delete them on request (section 7). Otherwise we delete them when the ranking service ends.

## 6. Children

The Game is not primarily directed to children and does not ask for names, contact details or other information that identifies a child. The ad SDK may still process the data described in section 2.

## 7. Your rights

- You can remove on-device records by uninstalling the Game or clearing its data.
- If you signed in, you can delete your account, backed-up progress and ranking records yourself in Settings → Back up progress → Delete account (1-e).
- If you did not sign in, ranking records on our server (1-b) cannot be viewed or deleted in the Game; contact us below. Tell us your nickname (#NNNN) and roughly your score and date, and we will delete the records we can identify.
- For advertising identifier choices, see section 2.

## 8. Contact

- Company: Go We Are
- Privacy officer: Representative of Go We Are
- Email: go.we.are.official@gmail.com
- Ranking data deletion requests: go.we.are.official@gmail.com (subject e.g. "Ranking data deletion")

## 9. Changes

We will announce changes on the store page or in the Game before they take effect.
