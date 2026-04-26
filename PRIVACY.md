---
layout: default
title: Privacy Policy
permalink: /PRIVACY.html
---

# Privacy Policy — ThriveClinic Translate

**Last updated:** 2026-04-25
**Effective:** Upon TestFlight installation

ThriveClinic Translate ("the app") is a clinical communication tool for pediatric clinic providers in Toronto, Ontario. This policy explains what the app collects, how that data is handled, and the controls available to the family using it during a visit.

This policy is written to align with the **Personal Information Protection and Electronic Documents Act (PIPEDA)** and Ontario's **Personal Health Information Protection Act (PHIPA)**.

---

## 1. Who runs the app

The app is operated by the pediatric clinic that distributes it to its providers (the "clinic"). The clinic is the data controller for the purposes of PIPEDA and PHIPA. Contact the clinic directly to exercise any privacy right described below.

## 2. What the app does — and does not do

**Does:**
- Captures audio from the iPhone microphone only during an active provider-initiated translation session.
- Sends audio to a private translation service operated by the clinic, which uses OpenAI Whisper (speech recognition), Anthropic Claude (translation), and OpenAI / Microsoft Azure (text-to-speech) to produce the translated output.
- Stores the transcript of the current visit on the iPhone's local storage (Core Data) for the duration of the visit.

**Does not:**
- Record the family's conversation outside of an active session.
- Send the transcript to any clinic-owned server. Transcripts never leave the device.
- Log session content in third-party analytics or crash reporting services.
- Identify the family by name, contact details, or health card number. The app collects only the audio + transcript of what the family says aloud during the visit, plus a timestamp of family consent.

## 3. Data the app collects

| Data | Where it lives | How long | Purpose |
|---|---|---|---|
| Family consent timestamp | Local on device | 12 hours | PIPEDA / PHIPA audit record that the family agreed before the session |
| Audio of the visit (in-flight only) | RAM during the call to the translation service | Discarded after upload | Speech-to-text input |
| Visit transcript (text) | Local on device, Core Data | **Auto-deleted 12 hours after session ends** | Provider can re-read what was said in this visit |
| Selected patient language | Local on device | Until the provider changes it | Restores the clinic's last patient on next launch |
| Provider profile (name, title, clinic, photo placeholder) | Local on device | Until the provider clears it | Displays in the provider profile screen |
| Provider speech cadence (statistical pause + utterance length) | Local on device | Until the provider taps "Reset my learned cadence" | Tunes voice activity detection to the provider's natural pauses |
| Tigrinya correction submissions | Sent to the clinic's translation service | Until admin removes from the shared rule set | Improves Tigrinya translation for every clinician — submissions are reviewed by a clinic admin and may not contain digits, names, or patient details |

## 4. Data the app does NOT collect

- No patient name, birthdate, health card number, address, or phone number.
- No insurance, billing, or scheduling details.
- No analytics events tied to a session.
- No advertising identifiers.
- No location data.

## 5. Where data goes when the app uses external services

A single clinical session may briefly send the following to third-party AI providers, only for the immediate purpose of producing a translation:

- **OpenAI** — receives the audio chunk for speech recognition (Whisper) and a text snippet for text-to-speech synthesis. OpenAI's API terms state that audio and text submitted via the API are not used to train OpenAI models.
- **Anthropic** — receives the recognized text for translation by Claude. Anthropic's API terms state that API submissions are not used to train Claude models.
- **Microsoft Azure** — receives the translated text for text-to-speech synthesis using Azure Neural voices.

Each request flows through the clinic's private translation service hosted on Netlify. The clinic's service holds the API credentials; the iPhone does not contain any third-party API keys.

## 6. The Tigrinya learning loop (PRD §5.9)

The app includes an optional "Save for everyone" feature visible only when the patient language is Tigrinya. When a provider taps it, three short pieces of text — an English phrase, a Tigrinya phrase, and a rationale — are submitted to a shared learning queue maintained by the clinic admin. **The submission UI rejects any text containing digits or PHI markers.** Submissions are reviewed by a clinic admin before they affect future translations. Submissions identify the contributing provider by name (drawn from the provider profile on the device) and an IP address; they do not include any patient data.

## 7. The discharge SMS (when used)

If the provider taps the discharge SMS option at the end of a session, the iPhone uses iOS Messages to send a summary in the family's language to a phone number entered by the family during the visit. The phone number is held in iPhone memory only for the duration of the visit and is never sent to the clinic's translation service. **No SMS is sent unless the provider explicitly initiates it.**

## 8. Family consent before each session

Every session begins with a screen that displays — in English and the family's language — what the app does, that audio is heard only during the visit, and that the conversation is not saved after the family leaves. The session does not start until a family member physically taps the consent button on the iPhone. The timestamp of that tap is recorded as the consent record.

## 9. Network and security

- All requests to the clinic's translation service use HTTPS.
- The clinic's API keys for OpenAI, Anthropic, and Azure are stored in Netlify environment variables and never travel to the iPhone.
- TestFlight distribution restricts installation to Apple IDs the clinic has explicitly invited.
- The app does not implement a login system; the iPhone is the access control boundary. Loss of an iPhone should be reported to the clinic so the device can be remotely wiped via Find My iPhone.

## 10. Children's information

This is a pediatric clinic app. Children rarely interact with the iPhone directly; their parent or guardian taps the consent screen. Any incidental child information spoken aloud during the visit is treated under the same on-device-only, 12-hour-auto-delete model as adult speech. The app does not knowingly collect any child information beyond what is spoken aloud during a clinically-relevant interpreter exchange.

## 11. Family rights under PIPEDA / PHIPA

A family member can:
- Ask the provider to end and clear the session before submitting consent.
- Withdraw consent during a session, at which point the provider taps "End Session" and the transcript is auto-deleted within 12 hours.
- Contact the clinic directly to request a copy of any consent timestamp record relating to their visit, or to request its deletion ahead of the 12-hour window.

There is no clinic-side database of session transcripts, so a request for the transcript itself is not technically fulfillable beyond the 12-hour on-device window.

## 12. Changes to this policy

This policy may be updated to reflect changes in app behavior, AI provider terms, or applicable law. The updated date appears at the top of this document. Material changes will be communicated to providers, who should re-explain the consent screen to families if the family-facing copy changes.

## 13. Contact

For privacy questions, requests, or complaints, contact the clinic directly. The clinic is responsible under PIPEDA for responding within 30 days.

If the clinic's response is not satisfactory, you may contact the **Office of the Privacy Commissioner of Canada** at https://www.priv.gc.ca/ or the **Information and Privacy Commissioner of Ontario** at https://www.ipc.on.ca/.
