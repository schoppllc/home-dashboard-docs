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

See [TERMS.md](TERMS.md).
