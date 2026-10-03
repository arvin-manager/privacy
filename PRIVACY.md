# Privacy Policy for Privy

**Effective date:** October 3, 2026

**Canonical URL:** https://arvin-manager.github.io/privacy/

This Privacy Policy explains how Privy ("**the App**," "**we**," "**us**") handles information when you use the app. Privy stores your Vault content on your device and does not upload it to us. You control whether to export or share a copy. This policy also describes on-device face detection and the limited data third-party services (analytics, crash reporting, and advertising) may process.

If you have questions about this policy, contact us at **anarvin212@gmail.com**.

---

## 1. Summary

- Privy stores your Vault content (photos, videos, files) **on your device**, encrypted with AES‑256‑GCM at rest. Local working copies are used for viewing, processing, and export. We do not upload your Vault content to our servers or to a cloud service. You may choose to export or share a copy, as explained in Sections 4.1.3 and 6.
- There is no user account, sign-up, or login. We do not collect your name, email address, or any other identity information.
- Your app passcode, gesture pattern, and encryption keys are stored in the device's **Keychain** and never leave your device.
- We do **not** use Apple's App Tracking Transparency (ATT) framework, and we do not track you across other companies' apps or websites.
- Some optional, industry-standard third-party services (crash reporting, analytics, and non-personalized advertising) may be active depending on your build/region, as described in Section 5.

## 2. Information We Do Not Collect

Privy does not require an account and has no server-side backend for your content. Specifically, we do **not**:

- Collect or store your Vault photos, videos, files, notes, or tags on any server
- Sync your Vault content to iCloud or any other cloud service
- Collect your name, email address, phone number, or physical address
- Sell your personal information to anyone

Some files you view from an on-device source that is itself synced to iCloud (for example, a Photos library asset) may require that file to download from iCloud before Privy can read it. That download is handled entirely by iOS/Apple's frameworks — Privy never transmits the file anywhere else.

## 3. Information Stored on Your Device

To provide the app's core functionality, Privy stores the following data **locally on your device only**:

| Data | Where it's stored | Purpose |
|---|---|---|
| Vault photos, videos, and files | App's local container, encrypted with AES‑256‑GCM | The core "private vault" feature |
| App passcode / gesture pattern (salted, hashed) | iOS Keychain / on-device storage | Unlocking the app |
| Encryption master key | iOS Keychain (`WhenUnlockedThisDeviceOnly`) | Encrypting/decrypting your Vault content |
| App preferences (auto-lock timer, theme, etc.) | On-device app storage | Remembering your settings |

Privy does not send the data in this table to us or to analytics or advertising providers. If you choose to export or share content, the selected destination receives the copy you choose. Viewing, editing, and sharing may create decrypted local working copies in the app's cache or temporary storage. Deleting the app (rather than offloading it) removes its local container; Keychain entries are managed separately by iOS and may remain after uninstallation. See Section 7 for retention and deletion details.

## 4. Permissions the App Requests

Privy will ask for the following device permissions only when a feature that needs them is used. Photo import uses the iOS picker without requiring broad library access; library read/write access is requested if you choose to delete originals, and add-only access may be requested when saving a copy to Photos. You can grant or deny each independently in iOS Settings.

- **Face ID / Biometrics** — to unlock the app and your Vault using Face ID or Touch ID instead of (or in addition to) a passcode. Biometric data is processed entirely by iOS and is never accessible to Privy or to us.
- **Camera and Microphone** — to let you capture photos and video directly into your Vault using the in-app camera.
- **Photo Library** — to let you import existing photos/videos into your Vault, and to let you save Vault content back out to your Photos library when you choose to export it.


## 4.1 Face Data

### 4.1.1 Data Processed and Purpose

Privy processes photos and videos that you choose to import or capture; these files may contain visible faces. For face blur or mosaic, Apple's Vision framework runs on your device to detect face rectangles and, for videos, track their positions between frames. Privy may automatically precompute and cache these positions after a supported video is saved or the Vault is reopened, before you select a face effect. Photo detection runs when you enable "Blur detected faces"; video detection can also run when you select "Mosaic detected faces" if a suitable cache is unavailable.

The stored video detection data consists of frame timestamps and rectangle coordinates (position and size), video duration, display dimensions, and an algorithm version. Its only purpose is to position a blur or mosaic in a privacy copy and avoid repeating video analysis. Privy does not create or store separate face crops, faceprints, biometric templates, face embeddings, names, identities, or facial-recognition identifiers. It does not identify people, infer personal attributes, or use face data for advertising, profiling, or model training.

### 4.1.2 Face ID and Touch ID

Face ID and Touch ID unlocking use Apple's LocalAuthentication framework. Privy receives an authentication success or failure result and may receive a system error; it does not receive the biometric face image, face geometry, fingerprint, or biometric template. Apple manages biometric authentication, and its biometric templates are protected by the Secure Enclave. Privy does not collect, store, retain, or share Face ID or Touch ID biometric data.

### 4.1.3 Storage, Disclosure, and Sharing

Video face-detection caches are encrypted with the Vault's AES-256-GCM key and stored in the app's local Vault container on your device, with iOS file protection. The Vault directory containing these caches is excluded from device backups. The caches are not uploaded to us, synced to iCloud or another cloud service, or provided to Firebase, Google AdMob, or any other third party. Face analysis runs locally through Apple's frameworks and does not send the media to Apple for analysis.

Photos and videos containing faces remain user-selected Vault content. If you explicitly export or share an original or a processed copy through the system share sheet or save it to Photos, that media copy is sent to the destination you choose and may still contain visible faces. Privy does not include the separate face-detection cache with that copy. The destination's storage, sharing, and retention practices apply; for example, your Photos settings may sync an exported copy to iCloud Photos.

### 4.1.4 Retention and Deletion

Video face-detection caches have no separate fixed expiry while their associated video remains in the Vault. Moving a video to "Recently Deleted" retains the video and its encrypted face-detection cache for recovery. You can permanently delete it sooner from "Recently Deleted". Items become eligible for automatic permanent deletion after 30 days, and the app performs that cleanup when the corresponding Vault is next opened or unlocked. Permanent deletion removes the corresponding face-detection cache together with the video; if local file removal fails, the app retries cleanup when that Vault is reopened. Deleting the app, rather than offloading it, removes the local container containing these caches. Keychain entries are separate and contain no face-detection data.

### 4.1.5 Photo Detection and Temporary Copies

Photo face rectangles are used in memory for processing and are not saved as a separate face-detection database. Local temporary media and processed copies can contain faces. The privacy editors remove their prepared share files when those files are dismissed or cleaned up; leftover Safe Share output files older than 24 hours are eligible for cleanup on the next app launch. This is not a guarantee of deletion exactly 24 hours after creation. Copies you save or share outside Privy are retained by the destination until you delete them there.

Files received through the iOS share extension wait in an on-device App Group inbox protected by iOS file protection and excluded from device backups. They are working copies and are not yet encrypted with the Vault's AES-256-GCM key until you confirm import. Pending requests become eligible for removal after 7 days; Privy checks for expiry when the app is opened or the share extension prepares another transfer. An item currently being reviewed in the app is kept until that review finishes. Unreferenced transfer folders left by an interrupted share become eligible for cleanup after 24 hours. Successful import or cancelling an incoming review removes its pending copy. Cleanup failures are retried at a later cleanup opportunity. These actions do not delete source-app originals or already imported Vault items.


## 5. Third-Party Services

Privy uses a small number of third-party SDKs that are standard for app development, crash diagnostics, and advertising. These providers may process limited technical/device data as described below — **never your Vault content**.

### 5.1 Crash Reporting, Analytics & Feature Configuration (Firebase, Google LLC)

If enabled for your build, Privy uses **Firebase Analytics** and **Firebase Crashlytics** to understand app usage (e.g., screen views, app opens) and to diagnose crashes. Privy also uses **Firebase Remote Config** to receive operational availability settings for disclosed app features. Firebase may process a Firebase installation identifier, device model, OS version, app version, coarse usage events, and crash logs. Remote Config receives no Vault filenames, source URLs, file contents, passcodes, patterns, tags, or decrypted media.

Learn more: [Google's Privacy Policy](https://policies.google.com/privacy) · [Firebase data processing terms](https://firebase.google.com/terms/data-processing-terms)

### 5.2 Advertising (Google AdMob)

Privy may display banner, interstitial, or rewarded interstitial ads provided by **Google AdMob**. Two important points:

- **We do not request App Tracking Transparency (ATT) permission, and we do not use IDFA-based tracking.** Ads are requested as **non-personalized/contextual ads only** (the ad request explicitly sets `npa=1`), meaning ads are not personalized using your activity in other companies' apps or websites.
- Before any ad is requested, Privy uses Google's **User Messaging Platform (UMP)** to determine and, where legally required (e.g., in the EEA/UK), present a consent form for applicable privacy regulations (GDPR). When UMP requires a privacy-options entry point, Settings displays **Advertising Privacy Options** so you can review or change your advertising privacy choices. Changing these choices discards cached ads; subsequent requests follow the updated UMP state.

Learn more: [How Google uses information from sites and apps that use our services](https://policies.google.com/technologies/partner-sites) · [AdMob data disclosure](https://support.google.com/admob/answer/6128543)

### 5.3 In-App Purchases (Apple StoreKit)

If Privy offers a subscription or one-time purchase, all payment processing is handled entirely by **Apple** through StoreKit. Privy receives only a purchase/entitlement status from Apple — we never see or store your payment card details, billing address, or Apple ID.

## 6. Networking

Privy makes network requests for these functions:

- **Browsing and opening links** — the private browser loads websites and their resources. The websites you visit receive normal web requests, including your IP address, requested URLs, and information you submit to them. The browser uses a non-persistent website data store, which does not prevent websites from receiving these requests.
- **Downloading a file you provide a link for** — if you choose to download a PDF document into your Vault, the app retrieves it directly from the source you specified using a secure (HTTPS) connection. Network downloads are limited to PDF documents; Privy does not offer audio or video downloading. You can still import your own photos, videos, and other files through the iOS Photos or Files picker.
- **User-directed export or sharing** — a destination you choose may transfer your selected media using its own services. Privy does not upload the separate face-detection cache.
- **Apple purchase services**, which verify purchases and subscription entitlements through StoreKit.
- **The third-party SDKs described in Section 5**, which may make their own network calls to their respective providers (Google/Firebase) for the purposes described above.

Privy does not run a backend for Vault content and does not automatically upload that content or face-detection caches. Exporting or sharing a copy is under your control.

## 7. Data Retention & Deletion

Vault content and associated video face-detection caches stay on your device while you keep the item. Ordinary deletion moves items to "Recently Deleted" for recovery. You can permanently delete them there at any time. After 30 days, they are eligible for automatic permanent deletion when the corresponding Vault is next opened or unlocked. Failed local file deletions are retried when that Vault is reopened. Sections 4.1.4 and 4.1.5 explain face-detection and temporary-copy retention.

Deleting the app (rather than offloading it) removes its local container, including Vault content and face-detection caches. iOS Keychain entries, such as encryption keys and credential hashes, may persist after uninstallation; these entries contain no face images, face rectangles, or biometric templates. Uninstallation does not delete originals in Photos, previously exported or shared copies, or records retained by third-party services. Those services apply their own retention policies, linked in Section 5.

## 8. Children's Privacy

Privy is not directed at children under 13, and we do not knowingly collect personal information from children. Applicable advertising consent requests are handled through the consent flow described in Section 5.2.

## 9. Your Rights

Depending on where you live (e.g., under GDPR in the EEA/UK or CCPA/CPRA in California), you may have rights to access, correct, delete, or restrict processing of personal data held about you. Because Privy stores your Vault content only on your device and we hold no account or content data on our servers, most such requests can be satisfied by deleting content within the app or deleting the app itself. For questions about data processed by the third-party services in Section 5, you may also contact Google directly using the links provided there.

To exercise any rights regarding data we may hold (such as data from crash/analytics SDKs), contact us at **anarvin212@gmail.com**.

## 10. Changes to This Policy

We may update this Privacy Policy from time to time. Changes will be posted at the canonical URL above with a revised effective date at the top of the page. Continued use of the app after changes take effect constitutes acceptance of the revised policy.

## 11. Contact Us

**Privy**
Email: **anarvin212@gmail.com**
