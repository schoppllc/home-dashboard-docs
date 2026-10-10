# Home Dashboard: patient app documentation

Home Dashboard is a personal, self-hosted application. Each person runs their own copy on their own computer. It is not a hosted service, has no central server, and is not sold or offered to the public.

## What the app does with patient data

When a patient chooses to connect their health system's patient portal (for example MyChart), the app uses the SMART on FHIR standalone patient launch:

1. The patient signs in to their own patient portal in the portal's own window and approves read-only access.
2. The app reads that patient's own records through the health system's FHIR R4 patient API:
   - Patient (demographics needed to identify the record)
   - Observation: laboratory results and vital signs
   - MedicationRequest
   - Condition (problem list)
   - AllergyIntolerance
   - Immunization
3. The records are shown to that patient on their own dashboard: lab results over time with reference ranges, vital signs trends, and lists of medications, conditions, allergies and immunizations.

The app only reads data. It never writes, changes or deletes anything in the health system.

## Privacy policy

- **Who sees the data:** only the person running their own copy of the app (and members of their own household they choose to give access to on that computer). The developer has no access to anyone's data.
- **Where it is stored:** in a local database on the patient's own computer. Access tokens are stored encrypted. Nothing is sent to the developer or any third party.
- **Optional AI summary:** if the patient turns on the optional AI weekly read, a summary of their own numbers is sent to the AI provider they configured (Anthropic) to produce a wellness summary. It is off by default.
- **No sale or sharing:** data is never sold, shared, or used for advertising.
- **Deleting data:** the patient can delete all of their health data from the app at any time (Health, Sources, Delete). Disconnecting the portal stops all further access; access can also be revoked from the patient portal.
- **Security:** the app runs on the patient's own device behind their own login (password plus two-step code or a passkey) and is reachable only on their private network.

## Contact

Questions: open an issue in this repository.

## Terms and conditions

Last updated: October 10, 2026

These terms apply when you connect your patient portal (for example MyChart) to your own copy of Home Dashboard. Please read them before you approve access.

### What you're agreeing to

- **It's your copy.** Home Dashboard is self-hosted software. You run it on your own computer, and you're the only one responsible for that computer and who can use it. There's no hosted service and no account with the developer.
- **Read-only access to your own records.** When you approve access, the app reads your own health records through your health system's patient API. It never writes, changes or deletes anything in your health system.
- **Your data stays with you.** Records are stored in a local database on your computer. Nothing is sent to the developer. The optional AI summary is off by default; if you turn it on, a summary of your own numbers goes to the AI provider you configured. See the [privacy policy](#privacy-policy).
- **You can stop at any time.** Disconnect the portal in Health, Sources, or revoke access from your patient portal. You can delete all of your health data from the app whenever you want.

### Not medical advice

Home Dashboard shows your records and simple trends. It doesn't diagnose, treat or give medical advice, and it isn't a substitute for your doctor. Always talk to a qualified clinician about your results and before making health decisions. In an emergency, call 911 or your local emergency number.

### No warranty

The software is provided "as is", free of charge, without warranty of any kind. Records shown in the app may be incomplete, delayed or out of date; your health system's own records are the official source. To the extent the law allows, the developer isn't liable for any loss or harm that comes from using the software.

### Changes

If these terms change, the new version is posted here with a new date. Continuing to use the portal connection after a change means you accept the updated terms.

### Contact

Questions: open an issue in this repository.
