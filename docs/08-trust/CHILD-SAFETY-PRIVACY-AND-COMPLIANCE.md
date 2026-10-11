# Child Safety, Privacy, and Compliance Research

**Status:** Product requirements and legal research checklist, not legal advice. Obtain qualified counsel before launch.

## Product-level controls to design
- Minimise personal data; character names should be optional and described as fictional.
- Avoid collecting child voice recordings or open-ended voice input in the first release unless justified by research and approved privacy review.
- Use age-banded story constraints and layered safety checks before presenting content.
- Prevent or carefully handle frightening, violent, sexual, hateful, self-harm, dangerous imitation, and manipulative content.
- Keep parent controls, purchase actions, external links, account changes, and data controls behind suitable adult gates.
- Provide an easy report/hide workflow and documented incident response.
- Keep generation/provider logs free of unnecessary child-identifying content; define retention and deletion periods.
- Review vendor terms for training use, retention, subprocessors, residency, security, and deletion.
- Use no targeted advertising to children; assess whether third-party analytics/SDKs are compatible with target app-store policies.
- Verify rights and permitted use for generated and licensed music, voices, sound effects, and artwork.

## Official sources to review
- US FTC, “Complying with COPPA: Frequently Asked Questions”: https://www.ftc.gov/business-guidance/resources/complying-coppa-frequently-asked-questions . The FTC says COPPA applies to covered services directed to children under 13 that collect personal information, with parental notice/consent and access/deletion obligations in applicable cases. The rule was amended in 2025; re-check the current rule and counsel’s advice.
- Apple, “Design safe and age-appropriate experiences”: https://developer.apple.com/kids/ . Covers Kids category age bands and parental gates.
- Apple, App Review Guidelines: https://developer.apple.com/app-store/review/guidelines/ . Review Kids category, privacy, external links, purchases, analytics, and advertising restrictions.
- Google Play Families Policy: https://support.google.com/googleplay/android-developer/answer/9893335 . Review age-appropriate content, target-audience declarations, privacy, SDK, and advertising requirements.

## Jurisdiction matrix required before launch

| Jurisdiction | Research required | Owner/reviewer |
|---|---|---|
| India | Applicable child data protection, consent/parental consent, consumer protection, subscriptions, payment, privacy, and platform requirements | Qualified local counsel |
| United States | COPPA applicability and amended rule, state privacy laws, subscriptions, consumer protection | US counsel |
| European Union/EEA | GDPR child-consent age by member state, data protection by design, transparency, consumer/subscription rules, AI-related obligations as applicable | EU counsel |
| United Kingdom | UK GDPR, Age Appropriate Design Code applicability, consumer/subscription requirements | UK counsel |
| Other markets | Local child privacy, consumer, AI, content, app-store, tax, and subscription rules | Local counsel |

This is not an exhaustive legal inventory. Scope depends on audience, data flows, product features, and actual target markets.

## Launch-blocking questions
- Which data is necessary for an account and can a parent use the product without a child account?
- What parental consent/age assurance is required in each market?
- What is the lawful basis, purpose, retention period, and deletion process for each data field?
- What vendor contracts and data-processing terms are required?
- Which analytics, crash reporting, attribution, and billing SDKs are permitted?
- How will user-generated names and prompts be filtered for personal information?
- What safety testing and human review are required before release?
- How are copyright, publicity/voice rights, and generated output terms addressed?

Do not claim compliance until a jurisdiction-specific review and operational evidence are complete.