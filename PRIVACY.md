# Privacy Policy for Privy

**Effective date:** September 30, 2026

**Canonical URL:** https://arvin-manager.github.io/privacy/

This Privacy Policy explains how Privy ("**the App**," "**we**," "**us**") handles information when you use the app. Privy is designed so that your private photos, videos, and files never leave your device — this policy describes exactly what that means and what limited data third-party services (analytics, crash reporting, and advertising) may still collect.

If you have questions about this policy, contact us at **anarvin212@gmail.com**.

---

## 1. Summary

- Privy stores your Vault content (photos, videos, files) **only on your device**, encrypted with AES‑256‑GCM. We do not upload it to our servers or to any cloud service, and we cannot see, access, or recover it.
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

None of the data in this table is ever sent to us or to any third party. If you delete the app, this data is deleted with it.

## 4. Permissions the App Requests

Privy will ask for the following device permissions only when a feature that needs them is used. You can grant or deny each independently in iOS Settings.

- **Face ID / Biometrics** — to unlock the app and your Vault using Face ID or Touch ID instead of (or in addition to) a passcode. Biometric data is processed entirely by iOS and is never accessible to Privy or to us.
- **Camera and Microphone** — to let you capture photos and video directly into your Vault using the in-app camera.
- **Photo Library** — to let you import existing photos/videos into your Vault, and to let you save Vault content back out to your Photos library when you choose to export it.


## Face Data

Privy does not collect biometric face data, faceprints, face templates, or facial-recognition identifiers, and it does not attempt to identify any person.

**Face ID and Touch ID.** Unlocking with Face ID or Touch ID is performed entirely by iOS. Privy receives only a success or failure result from the system authentication prompt. Privy never receives, stores, or can access your face image, face geometry, or biometric template. That information remains under Apple's control in the Secure Enclave. It is not shared with us or with any third party, and Privy does not retain it.

**On-device face rectangles for optional privacy copies.** When you save a video in the Vault, or when you choose "Blur detected faces" or "Mosaic detected faces" while creating a privacy copy, Privy uses Apple's Vision framework on this device to find rectangular regions that may contain a face. The only derived information kept is a list of timestamps and rectangle coordinates (position and size within the frame), together with the video duration and display size needed to place a blur or mosaic. Privy does not create a face image, face embedding, identity, or name from this process, and it does not perform facial recognition.

If that rectangle list is saved, it is encrypted on the device with the same AES-256-GCM Vault key and stored only in the app's local container. It is not uploaded to our servers, not synced to any cloud service, and not shared with Firebase, Google AdMob, or any other third party. It is deleted when you delete the corresponding Vault item. Deleting the app deletes it with the rest of the app's local data. A photo blur is applied in memory to the copy you choose to share and is not kept as a separate face database.

Photos and videos you choose to keep in the Vault may themselves show people. Those files are encrypted Vault content stored only on your device, as described in Section 3. They are not sent to us for face analysis.

## 5. Third-Party Services

Privy uses a small number of third-party SDKs that are standard for app development, crash diagnostics, and advertising. These providers may process limited technical/device data as described below — **never your Vault content**.

### 5.1 Crash Reporting, Analytics & Feature Configuration (Firebase, Google LLC)

If enabled for your build, Privy uses **Firebase Analytics** and **Firebase Crashlytics** to understand app usage (e.g., screen views, app opens) and to diagnose crashes. Privy also uses **Firebase Remote Config** to receive operational availability settings for disclosed app features. Firebase may process a Firebase installation identifier, device model, OS version, app version, coarse usage events, and crash logs. Remote Config receives no Vault filenames, source URLs, file contents, passcodes, patterns, tags, or decrypted media.

Learn more: [Google's Privacy Policy](https://policies.google.com/privacy) · [Firebase data processing terms](https://firebase.google.com/terms/data-processing-terms)

### 5.2 Advertising (Google AdMob)

Privy may display a banner ad provided by **Google AdMob**. Two important points:

- **We do not request App Tracking Transparency (ATT) permission, and we do not use IDFA-based tracking.** Ads are requested as **non-personalized/contextual ads only** (the ad request explicitly sets `npa=1`), meaning ads are not personalized using your activity in other companies' apps or websites.
- Before any ad is requested, Privy uses Google's **User Messaging Platform (UMP)** to determine and, where legally required (e.g., in the EEA/UK), present a consent form for applicable privacy regulations (GDPR).

Learn more: [How Google uses information from sites and apps that use our services](https://policies.google.com/technologies/partner-sites) · [AdMob data disclosure](https://support.google.com/admob/answer/6128543)

### 5.3 In-App Purchases (Apple StoreKit)

If Privy offers a subscription or one-time purchase, all payment processing is handled entirely by **Apple** through StoreKit. Privy receives only a purchase/entitlement status from Apple — we never see or store your payment card details, billing address, or Apple ID.

## 6. Networking

Privy makes network requests only in these cases:

- **Downloading a file you provide a link for** — if you choose to import media from a URL (e.g., a video link) into your Vault, the app downloads that file directly from the source you specified using a secure (HTTPS) connection.
- **The third-party SDKs described in Section 5**, which may make their own network calls to their respective providers (Google/Firebase) for the purposes described above.

Privy does not run its own backend server and does not transmit your Vault content over the network under any circumstance.

## 7. Data Retention & Deletion

All Vault content and app data live on your device. You can delete individual items within the app at any time, and deleting the app removes all locally stored data, including your encryption keys and Keychain entries, permanently.

## 8. Children's Privacy

Privy is not directed at children under 13, and we do not knowingly collect personal information from children. The advertising consent flow described in Section 5.2 treats all users as not exempt from age-of-consent requirements.

## 9. Your Rights

Depending on where you live (e.g., under GDPR in the EEA/UK or CCPA/CPRA in California), you may have rights to access, correct, delete, or restrict processing of personal data held about you. Because Privy stores your Vault content only on your device and we hold no account or content data on our servers, most such requests can be satisfied by deleting content within the app or deleting the app itself. For questions about data processed by the third-party services in Section 5, you may also contact Google directly using the links provided there.

To exercise any rights regarding data we may hold (such as data from crash/analytics SDKs), contact us at **anarvin212@gmail.com**.

## 10. Changes to This Policy

We may update this Privacy Policy from time to time. Changes will be posted at the canonical URL above with a revised effective date at the top of the page. Continued use of the app after changes take effect constitutes acceptance of the revised policy.

## 11. Contact Us

**Privy**
Email: **anarvin212@gmail.com**
