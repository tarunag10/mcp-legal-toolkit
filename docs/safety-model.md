# Safety Model

`mcp-legal-toolkit` is designed for legal and compliance work where incorrect, unauthorized, or poorly handled output can create material risk. Tools and examples should be designed around the following defaults.

## Read-only by default

Legal documents, matter records, compliance evidence, and connected systems are read-only unless a user explicitly requests a state-changing action. A tool must not edit, upload, delete, send, file, comment, or create a pull request as an implicit consequence of reading or analyzing data.

When a workflow has a write mode, it should expose that mode clearly and keep its scope as narrow as possible. Prefer generating a reviewable draft, patch, or action plan before calling a write-capable integration.

## Human approval gates

A human must approve each external or irreversible action, including:

- editing or deleting a document or record;
- uploading content to a third party;
- sending email or another external message;
- posting an issue, comment, review, commit, or pull request; and
- changing access controls, retention settings, or compliance evidence.

Approval should identify the destination and the exact content or change being authorized. A generic instruction to "handle this" is not approval to take an external action.

## Auditability

Implementations should retain an auditable record of material tool calls and generated outputs. At minimum, record the request time, actor, tool name, target system, parameters or a privacy-preserving summary, approval reference for state-changing actions, outcome, and relevant source identifiers.

Audit logs must avoid storing more sensitive content than is needed for accountability. They should be access-controlled, tamper-evident where practical, and governed by an explicit retention policy.

## Sensitive information boundaries

Before connecting a source or sharing generated output, classify the data and apply the stricter applicable rule:

- **Privileged information:** do not disclose it outside the authorized legal team or send it to services without confirmed authorization and safeguards.
- **Confidential information:** limit access to the engagement purpose and approved recipients; do not place it in public repositories, issue trackers, or prompts visible to third parties.
- **Personal data:** minimize collection and sharing, use approved processors, and follow the applicable legal basis, retention, and data-subject requirements.

When classification or authorization is unclear, stop at a read-only draft and ask a human reviewer to decide.

## Maintainer checklist

New tools and examples should document their read and write behavior, request the minimum permissions needed, require an explicit approval step before external writes, and describe the audit record they create. Tests should cover that read-only mode cannot trigger an external mutation and that missing approval prevents the mutation.
