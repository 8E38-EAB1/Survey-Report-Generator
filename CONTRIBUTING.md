# Contributing

Thank you for considering a contribution.

## Before you start

1. Search existing issues and pull requests to avoid duplicate work.
2. For a substantial change, open an issue describing the problem and proposed approach first.
3. Keep changes focused and explain the user-facing impact.

## Development workflow

1. Fork the repository and create a feature branch.
2. Make changes in `index.html` or supporting documentation.
3. Run the application locally in a modern browser (`python -m http.server 8000` is sufficient).
4. Test the affected workflow manually, including generated print output where relevant.
5. Check the browser console for errors.
6. Submit a pull request with a clear description and testing notes.

## Contribution requirements

- Do not commit API keys, credentials, `.env` files or other secrets.
- Do not commit real insured/customer information, claim files, vehicle documents, policy schedules, invoices, signatures or identifiable screenshots.
- Use synthetic test data only.
- Preserve existing workflows unless the change intentionally modifies them and documents the change.
- For calculation changes, explain the formula, assumptions and relevant source/rule in the pull request. Include test cases with fictional values.
- Keep accessibility, mobile usability and print layout in mind.
- Update the README when features, setup steps, data handling or limitations change.

## Pull request checklist

- [ ] The change has a clear purpose and scope.
- [ ] I tested the affected workflow in a current browser.
- [ ] I checked the browser console for errors.
- [ ] I tested print/PDF output if the change affects reports.
- [ ] I used only fictional/sample data.
- [ ] I did not add secrets or personal information.
- [ ] Documentation is updated where needed.
