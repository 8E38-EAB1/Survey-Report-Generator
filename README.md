# Motor Survey Report Generator

A browser-based toolkit for motor insurance surveyors and loss assessors. It helps prepare structured survey reports, repair assessments, spot survey reports, vehicle valuation reports and fee bills from a single HTML application.

> **Project status:** Early-stage open-source release. Review calculations, policy wording, document handling and generated reports before using them in professional work. This software does not replace a licensed surveyor's judgement or insurer requirements.

## Features

- **Motor survey reports:** policy, insured, vehicle, driver, accident, police record, certification and document-verification details.
- **Repair assessment:** labour and spare-parts line items, depreciation, GST calculations, summaries and payment details.
- **Spot survey reports:** a separate spot-survey workflow, including damage notes and saved report history.
- **Vehicle valuation reports:** a dedicated valuation workflow and printable output.
- **Fee bills:** prepare, save and print survey fee bills.
- **AI-assisted document extraction:** send uploaded RC, driving licence, policy, permit, fitness, estimate and bill documents to the Anthropic Messages API for OCR-assisted field and line-item extraction.
- **Print/PDF output:** browser print layouts designed for A4 output. Choose “Save as PDF” in the browser's print dialog.
- **Local history and backups:** saved reports and bills are kept in the current browser's local storage; export/import backup files to move data between browsers or devices.
- **Configurable letterhead:** set the surveyor/business name, designation, department, licence details, address and contact information in the Letterhead Settings panel.

## Quick start

This is a static HTML application. No build step or package installation is required.

1. Download or clone this repository.
2. Open `index.html` in a modern desktop browser.
3. Configure the Letterhead Settings before generating reports.
4. Fill in the relevant report sections. Use the OCR controls only if you have configured your own Anthropic API key.
5. Generate the preview and use the browser print dialog to print or save a PDF.
6. Export regular JSON/ZIP backups from the application. Keep backups in a secure location.

For local development, you can also serve the folder with any static HTTP server, for example:

```bash
python -m http.server 8000
```

Then open <http://localhost:8000>.

## AI-assisted OCR setup

The OCR feature calls the Anthropic API directly from the user's browser. Each user must provide their own Anthropic API key in the application. The key remains only in the page memory while the page is open; it is not written to browser storage, included in backups, or included in the repository.

- Never commit an API key, `.env` file, real claim document, RC, driving licence, policy, invoice or customer record.
- Use a key you control and monitor its usage and billing.
- Uploaded document content is transmitted to Anthropic when OCR is run. Do not upload documents unless you are authorised to share them with that service.
- Verify every extracted field and amount against the source document. OCR can misread text, dates, registration numbers and amounts.
- Check Anthropic's current API documentation for supported model identifiers and API requirements. The model identifier in the current application source may need updating as Anthropic changes its model catalogue.

## Data storage and privacy

This project has no application backend, user accounts, server-side database or built-in cloud synchronisation.

- Report histories, bills and letterhead settings are stored in the browser's `localStorage`.
- The Anthropic API key is held only in page memory while the page is open; it is not persisted in browser storage.
- Backups exported by the app can contain sensitive personal, vehicle, policy and claim information. Treat them as confidential records.
- Browser storage is not encrypted by this application. Anyone with access to the same browser profile may be able to access locally stored records.
- Clearing browser data can remove locally stored records. Export backups regularly and protect them appropriately.
- OCR document contents and prompts are sent to Anthropic when the user invokes extraction. Other form data is not intentionally sent to a project-operated server because this project does not operate one.

See [SECURITY.md](SECURITY.md) for security reporting and handling guidance.

## Technology

- HTML, CSS and vanilla JavaScript
- Anthropic Messages API for optional OCR
- JSZip (loaded from a CDN) for ZIP backup export/import
- Google Fonts (loaded remotely)

An internet connection is required for CDN-hosted libraries/fonts and Anthropic OCR. Core form entry and report generation are designed to run in the browser.

## Browser support

Use a current version of Chrome, Edge, Firefox or Safari. Printing and local file access behaviour can vary by browser. A desktop browser is recommended for editing large assessment tables and reviewing A4 print output.

## Known limitations

- No authentication, role management, server-side storage, audit trail or multi-user collaboration.
- Browser-local records do not automatically sync between devices.
- The API key is used from the client browser for OCR; this is convenient for a personal tool but is not a substitute for a secure server-side integration in a multi-user hosted product.
- The application includes starter insurer/garage lists and report conventions that may need adaptation to a user's jurisdiction, insurer and workflow.
- Calculations and standard clauses must be independently checked against current policy wording, applicable tariff/regulatory requirements and insurer instructions.
- No formal automated test suite or independent legal/accounting validation is included in this initial release.

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md), open an issue before large changes, and do not include real personal data or claim documents in issues, pull requests, tests or screenshots.

## Licence

Released under the MIT License. See [LICENSE](LICENSE).

## Disclaimer

This project is an administrative productivity tool. It does not provide insurance, legal, engineering or financial advice; determine claim liability; guarantee policy compliance; or certify the accuracy of assessments. The surveyor/user remains responsible for checking source documents, calculations, applicable rules and final reports.
