# Public research archive

This repository is public. Include only reviewed public articles, article metadata, and intentionally public supporting material. Never copy the website repository wholesale, local drafts, resume data, access credentials, `.env` files, or deployment/runtime secrets here.

Chinese is the semantic source of truth. Read `glossary.md` before editing bilingual content. Preserve the argument and strength of claims; use actor for general acting entities and agent for AI. Maintain complete English mirrors when available; do not publish placeholder translations as completed articles.

`article-metadata.json` records each article's stable website path, explicit `publishedAt` and `updatedAt`, Markdown file, source/history URLs, and content hash. Do not substitute a Git commit time or file modification time for either date. Only substantive content changes advance `updatedAt`; preserve `publishedAt` when importing, moving, or synchronizing files.

Git commit history is the public version history from the actual import onward. Do not backdate commits or invent previous revisions.

The private `rikkalab` website has a local Markdown copy and metadata snapshot. Codex must maintain both copies for article edits and verify them with the website's `npm run check:research`. Website builds must remain independent of this checkout. No git submodule or deployment-time content download.

Do not overwrite unrelated changes in either checkout. Reconcile independent edits before synchronization. Public titles, descriptions, dates, and source/history links must match the website.
