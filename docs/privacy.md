---
layout: default
title: Pointwise Privacy Policy
permalink: /privacy/
---

# Pointwise Privacy Policy

**Effective date: 25 August 2026**

Pointwise is a collaborative estimation application that connects to GitHub repositories, allows repository contributors to estimate GitHub issues and uses GitHub Copilot to produce an advisory task assessment.

This policy explains what information Pointwise processes, why it is used, how long it is retained and the choices available to users.

## 1. Information Pointwise processes

Depending on how Pointwise is used, it may process:

- GitHub account information, including a username and avatar URL;
- stable GitHub numeric account identifiers used to recognise a returning account or installation;
- GitHub App installation identifiers and installation status information;
- GitHub Marketplace subscription information, including plan, billing-cycle, trial and subscription-status metadata supplied by GitHub;
- GitHub repository identifiers, repository names and default branches;
- GitHub issue numbers, titles, descriptions and labels;
- repository paths and relevant repository content used to assess an issue;
- repository contributor identifiers, usernames and avatar URLs;
- estimation-session identifiers, participant names and submitted estimates;
- GitHub Copilot assessment results, progress information and validation errors;
- workspace plan and repository-entitlement information;
- records that a repository requested information about Pointwise Pro;
- essential authentication and session cookies; and
- limited operational logs needed to secure, diagnose and operate the service.

Pointwise does not intentionally collect payment-card information, advertising profiles or special-category personal data.

## 2. How information is collected

Information is received:

- from GitHub after a user authorises Pointwise;
- from GitHub App installation and Marketplace events;
- from repositories selected through the Pointwise GitHub App installation;
- from users participating in an estimation session;
- from GitHub Copilot when it returns an assessment; and
- automatically through essential cookies, service requests and operational logs.

Pointwise only requests access to repositories made available through the relevant GitHub authorisation or GitHub App installation.

## 3. How information is used

Pointwise processes information to:

- authenticate users and verify their GitHub connection;
- associate a returning GitHub account or GitHub App installation with the correct Pointwise workspace;
- identify repositories, issues and contributors available to a workspace;
- create and synchronise collaborative estimation sessions;
- record and display participant estimates;
- provide relevant issue and repository context to GitHub Copilot;
- validate, display and download advisory task assessments;
- enforce repository and plan limits;
- process GitHub Marketplace subscription state and installation lifecycle events;
- measure repository interest in a future Pointwise Pro plan;
- prevent misuse and protect the service; and
- investigate errors and maintain reliability.

Pointwise does not sell personal information or use it for third-party advertising.

## 4. GitHub Copilot processing

When a session leader requests a review, Pointwise sends the selected issue and relevant repository context to GitHub Copilot. Submitted team scores and the permitted Fibonacci scale may also be supplied so Copilot can return one advisory estimate.

GitHub Copilot processes this information to generate the requested assessment. Pointwise instructs Copilot to treat repository and issue content as untrusted evidence, return a structured response and avoid judging whether the team estimate is correct.

GitHub's own terms and privacy documentation also apply to information processed by GitHub and GitHub Copilot.

## 5. Cookies and authentication

Pointwise uses essential cookies only.

The GitHub OAuth access token is encrypted using AES-256-GCM and stored in an `HttpOnly` cookie. In production, the cookie is also marked `Secure` and `SameSite=Lax`. It expires after no more than 30 days unless it is cleared sooner.

A short-lived OAuth state cookie is used to protect the GitHub connection flow and expires after approximately 10 minutes.

A separate session-leader cookie is used to protect privileged actions within a shared estimation session.

Disconnecting GitHub clears the Pointwise GitHub connection cookie. Uninstalling or revoking the GitHub App prevents future access through that installation.

## 6. Storage and retention

### Shared estimation sessions

Shared-session information is stored temporarily in Upstash Redis. Sessions, estimates and completed assessments expire after two hours of inactivity. Activity within a session renews this two-hour period.

### GitHub connection

The encrypted GitHub OAuth token is stored in the user's browser cookie rather than in Pointwise's persistent application database. The cookie expires after no more than 30 days or is cleared when the user disconnects GitHub.

### Workspace and entitlement records

Supabase Postgres stores durable records needed to identify a workspace and enforce product entitlements. These may include:

- a generated Pointwise workspace UUID;
- a GitHub numeric user ID for a personal workspace;
- a GitHub App installation ID;
- the workspace plan and repository limit;
- selected repository numeric IDs and repository names; and
- creation and update timestamps.

The GitHub numeric user ID is a stable identifier supplied by GitHub. Pointwise does not need to store the user's GitHub username in the workspace record to recognise the account. These identifiers are pseudonymous identifiers rather than anonymous data, because they can be associated with a GitHub account through GitHub.

### GitHub App and Marketplace records

Pointwise may retain installation and Marketplace event records needed to operate and administer the service. These may include GitHub installation IDs, GitHub numeric account IDs, account type, installation status, subscription plan and status, billing-cycle metadata, trial dates, event actions and event timestamps.

Pointwise does not receive or store payment-card details from GitHub Marketplace.

### Pro-interest and product-operation records

Pointwise may store workspace IDs, repository IDs, product milestone state and timestamps used to understand Pro demand, track installation milestones and operate related automation.

### Operational logs

Vercel and other infrastructure providers may retain limited request and error logs under their configured retention periods. Where Pointwise derives identifiers specifically for logging, rate limiting or security correlation, it may hash or otherwise pseudonymise them. This does not mean that all durable GitHub identifiers in the application database are hashed.

Pointwise avoids intentionally logging GitHub access tokens, complete issue content, repository source content or complete Copilot assessments.

Persistent records are retained while needed to provide the service, enforce plan limits, process installation or subscription state, understand product demand or meet legal and security obligations.

Users may request deletion of eligible persistent Pointwise records. Disconnecting GitHub alone does not automatically delete workspace-entitlement, installation, Marketplace or Pro-interest records where they are still required for the purposes above.

## 7. Service providers

Pointwise relies on the following providers:

- **GitHub:** authentication, GitHub App installation data, Marketplace subscription data, repository data, issue data, contributor data and GitHub Copilot;
- **Vercel:** application hosting, serverless execution and operational logging;
- **Upstash:** temporary Redis storage and shared-session synchronisation; and
- **Supabase:** persistent workspace, repository-entitlement, installation, Marketplace, milestone and Pro-interest records.

These providers may process information in countries outside the user's country. Their own contractual safeguards and privacy terms apply to their processing.

Pointwise may also disclose information where required by law, to protect users or the service, or as part of a business transfer. Pointwise does not permit service providers to use Pointwise data for their own advertising.

## 8. Legal bases

Where UK or EU data-protection law applies, Pointwise relies on one or more of the following legal bases:

- providing the service requested by the user;
- legitimate interests in operating, securing and improving Pointwise;
- compliance with legal obligations; and
- consent, where consent is specifically requested and may be withdrawn.

## 9. Security

Pointwise uses measures intended to protect information, including:

- encrypted GitHub OAuth tokens;
- `HttpOnly`, `Secure` and `SameSite` cookie controls in production;
- OAuth state validation;
- hashed session-leader tokens;
- hashed or pseudonymised identifiers for selected logging and rate-limiting use cases;
- server-side authorisation and repository-entitlement checks;
- time-limited shared-session storage;
- validation of API inputs and Copilot responses; and
- restricted access through the GitHub App installation.

No internet service can guarantee absolute security. Security concerns should be reported through the contact method below without including secrets, access tokens or private repository content.

## 10. User choices and rights

Depending on location, users may have rights to request:

- access to personal information;
- correction of inaccurate information;
- deletion of eligible information;
- restriction of processing;
- objection to certain processing;
- a portable copy of information; or
- withdrawal of consent where processing relies on consent.

Users can disconnect GitHub from within Pointwise and can revoke or uninstall Pointwise through GitHub settings.

To make a privacy or deletion request, contact Pointwise using the details below. Do not include passwords, access tokens, private source code or other sensitive information in a public GitHub issue.

## 11. Children's privacy

Pointwise is intended for professional software-development teams and is not directed at children. Pointwise does not knowingly collect personal information from children.

## 12. Changes to this policy

This policy may be updated when Pointwise's features, providers or legal obligations change. Material changes will be published in this file with a revised effective date. The repository history provides a record of previous versions.

## 13. Contact

For privacy questions, deletion requests or security concerns, contact Pointwise using the appropriate channel:

- Support email: support@pointwise-estimates.tech
- Security email: security@pointwise-estimates.tech
- Support repository: https://github.com/ark-whale-applications/pointwise-support
- Support requests: https://github.com/ark-whale-applications/pointwise-support/issues/new
- Pointwise organisation: https://github.com/ark-whale-applications

Please avoid posting personal information, security-sensitive information or confidential repository data in a public issue. Use the relevant email address for private requests.
