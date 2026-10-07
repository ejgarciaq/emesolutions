# Eme Tech Consulting Landing

## Objective
Build a professional, modern Spanish-language B2B landing page for Eme Tech Consulting that respects the corporate identity and avoids unsupported security, certification, or performance claims.

## Problem and motivation
The repository had no application source or frontend toolchain. The user authorized implementation. Corporate email is the intended contact channel, but hosting, backend, email provider, and recipient are not supplied. The page must not collect or claim to send inquiries until secure delivery is configured.

## Scope
* Implement a responsive, accessible single-page static frontend using semantic HTML and lightweight CSS.
* Include a hero, four service pillars, a trust/methodology section without invented metrics, contact section, and footer.
* Keep contact submission unavailable until a server-side delivery route is selected and configured.
* Do not deploy, invent corporate/legal details, add unverified claims, or place secrets in client code.

## Constraints and decisions
* Brand: Eme Tech Consulting, confirmed by the user.
* Palette: `#0A192F`, `#00B4D8`, `#2D3748`, `#F8FAFC`, per `AGENTS.md`.
* Services follow `AGENTS.md`: cybersecurity/hardening, IT audit/compliance, enterprise software, and cloud/on-premise infrastructure.
* CTA: “Ver opciones de contacto”; it links to contact status, not a functioning submission.
* Contact channel: corporate email; recipient, provider, and hosting remain unresolved. Never claim delivery succeeds before backend verification.
* TDD: ordinary functional checks, explicitly selected by user. No app framework or test runner exists.
* Estimated authored changes: approximately 250 lines, below the advisory 400-line delivery budget. Delivery strategy: `ask-on-risk`.
* Initial repository was on an unborn `master` branch with user-owned untracked `AGENTS.md` and `.gga`; preserve and exclude them from task commits. Feature branch: `feature/eme-tech-consulting-landing`.

## Authorized scope
Create the landing source and its local styling/accessibility behavior. Do not choose an email provider, hosting product, recipient, legal wording, or public claims for the user. Do not deploy or transfer files remotely.

## Tasks
* [x] **ETL-01: Build the static landing page.** Added the Spanish semantic page, responsive corporate visual system, service and methodology content, and honest disabled contact form. CTA opens contact status; submission controls remain disabled and explain that email delivery is not configured. Acceptance met: keyboard-usable semantic navigation; mobile/desktop structure; high-contrast focus and CTA; no invented metrics, certifications, contact details, external fonts, or images. Route: direct inline fallback after the delegated Explore writer reported no file-editing or terminal tools. Verification: Chrome rendered at 1440x1200 and 390x844; screenshots are `/tmp/eme-landing-desktop.png` and `/tmp/eme-landing-mobile.png`; mobile screenshot shows the next section below the hero. Node checks found no duplicate IDs or broken anchors, all four services present, and the form disabled. Calculated contrast: navy/paper focus 16.82:1, paper/navy focus 16.82:1, cyan CTA/navy 7.14:1. VS Code reported no HTML/CSS diagnostics; `git diff --check` was clean. `gga run` exited successfully but reported `No matching files staged for commit`; `.gga` includes TS/JS only, so this page was not analyzed by GGA. An independent reviewer found and confirmed fixes for focus contrast, CTA clarity, and headline wording. Native RDD was on by default, but review STATUS failed with `immutable_review_transport_unsupported`; mode was not changed.
* Formatting clarification: the earlier `git diff --check` did not inspect untracked files. The later Node check verified final newlines and no trailing whitespace in `index.html`, `styles.css`, and this task document.
* [ ] **ETL-02: Integrate secure contact delivery and deployment headers.** After the user identifies hosting/runtime, email provider, and recipient, add a server-side endpoint with authoritative validation, bounded input/rate limits, spam handling, and host-appropriate security headers. Keep credentials server-side. Acceptance: valid inquiries reach the configured corporate inbox; invalid, oversized, and rate-limited input is rejected; no secret is present in client assets; deployed headers are verified. Route: undecided until configuration is supplied. Verification commands depend on the selected runtime.

## Verification and current progress
* Effective TDD is off by explicit user selection of ordinary functional checks.
* Available locally: Node.js/npm, `gga`, and Google Chrome. No package manifest, tests, or build scripts exist.
* ETL-01 implementation and local checks are complete. ETL-02 is blocked on email provider, hosting/runtime, and recipient configuration.
* Native receipt review is on by default, but this runtime is not an eligible immutable review transport. The switch was not changed; independent read-only verification was used.
* Work-unit commit: not created because the user did not explicitly request a commit. The landing implementation and checks are complete; only `index.html`, `styles.css`, and this task document belong in that commit if authorized. Preserve user-owned `AGENTS.md` and `.gga` as untracked.

## Relevant files
* `AGENTS.md` — corporate identity and quality requirements.
* `index.html` — Spanish landing content and semantic structure.
* `styles.css` — responsive corporate visual system.
* `odd/tasks/eme-tech-consulting-landing.md` — task progress, constraints, and verification evidence.
