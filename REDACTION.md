# Redaction Checklist

Do not publish until every item here is checked.

## Must Remove

- Personal emails.
- Account IDs, org IDs, invoice numbers, receipt numbers, payment details.
- GitHub PATs, API keys, bearer tokens, OAuth tokens, recovery codes.
- Raw `.eml` files.
- Raw `.jsonl` session files.
- Raw `.claude` config files.
- Private names not necessary to the technical case.
- Medical/family/relationship details unless explicitly chosen for a personal essay version.
- Crisis/despair lines that can be weaponized against the author.

## Keep

- Dates and relative sequence.
- Commands, if redacted and technically relevant.
- File paths, if they do not expose secrets.
- Failure categories.
- Short transcript excerpts showing the behavior under analysis.
- Public source links.
- Redacted support-response facts.

## Secret Scans Before Publishing

Run these from repo root before pushing:

```bash
rg -n '[[:alnum:]._%+-]+@[[:alnum:].-]+\.[[:alpha:]]+' .
rg -n 'ghp_[A-Za-z0-9_]+|github_pat_[A-Za-z0-9_]+' .
rg -n 'sk-[A-Za-z0-9_-]+|sk_[A-Za-z0-9_]+' .
rg -n 'Bearer [A-Za-z0-9._-]+' .
rg -n 'AIza[0-9A-Za-z_-]+' .
rg -n 'invoice|receipt|orgId|payment|card|Fatima|Ghadah' .
```

Better: run `gitleaks detect --no-git --source .` if available.

## Publishing Sequence

1. Rotate/scrub exposed tokens first.
2. Build the redacted Markdown case study.
3. Run scans.
4. Create GitHub repo under the correct account.
5. Push as private first.
6. Review rendered GitHub Markdown.
7. Flip public only after final human pass.
8. Post short links to X and Reddit.

