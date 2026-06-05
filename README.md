# mcp-legal-toolkit

MCP tools and examples for safe, local-first legal and compliance workflows.

## Project overview

`mcp-legal-toolkit` is a starter toolkit for building Model Context Protocol
servers that help legal, compliance, and operations teams inspect documents,
organize evidence, and prepare review-ready summaries. The project is intended
to favor read-only data access, deterministic checks, explicit audit trails, and
human review before any advice, filing, approval, or external communication.

The first public scope is deliberately practical:

- read local matter or policy files through narrowly scoped MCP tools
- extract structured facts that a reviewer can verify against source text
- compare documents against checklists, playbooks, or compliance controls
- produce review packets that show sources, assumptions, and unresolved items
- document safe defaults for teams experimenting with legal agent workflows

## Non-goals

This toolkit does not provide legal advice, replace qualified legal review, or
make autonomous legal or compliance decisions. It should not submit filings,
contact counterparties, approve regulated actions, or mutate source systems
without a separate product layer that includes authorization, logging, and
human confirmation.

Broad AI-generated rewrites are also out of scope. Contributions should be
small, testable, and easy for maintainers to review.

## Example workflows

- Contract triage: index a folder of contracts, identify governing law,
  renewal dates, assignment clauses, and missing schedules, then generate a
  reviewer checklist with citations.
- Compliance evidence review: map policy files and control evidence to a
  framework checklist, flag missing proof, and leave unresolved judgments for a
  human reviewer.
- Data subject request packet: gather local correspondence and document
  metadata, summarize timelines, and prepare a source-linked review bundle.
- Legal operations intake: classify incoming requests, extract key dates and
  parties, and prepare a routing summary without sending messages or taking
  action automatically.

## Safety model

This project should be safe to run against sensitive legal and compliance
materials by default. Tools, examples, and docs should assume that source
documents are confidential, reviewer-owned, and read-only unless a user has
explicitly opted into a stronger action.

Recommended defaults:

- Read-only access: tools may inspect local files, metadata, and review
  checklists, but they should not edit source documents or compliance records.
- Human approval: any proposed edit, upload, issue comment, pull request,
  filing, notice, or external message must require explicit user approval.
- Auditability: generated outputs should identify the tool call, input scope,
  source files, assumptions, and unresolved reviewer decisions.
- Data boundaries: privileged, confidential, personal, or regulated data should
  stay local unless the user has approved the exact destination and purpose.
- Review-first output: tools should prepare source-linked summaries and
  checklists, not final legal advice or autonomous compliance decisions.

For maintainers, new tools should document their permissions, inputs, outputs,
and failure modes before they are treated as stable. For users, every generated
summary should be treated as a review aid that needs independent verification
against the underlying source material.

## Contributing

Useful contributions are narrow and evidence-led. Good first issues include
documentation improvements, small read-only tools, test fixtures, example
workflows, safety notes, and reproducible bug reports.

When proposing a change, include:

- the workflow or risk the change supports
- the files or commands used to verify it
- the safety boundary, especially whether the tool is read-only
- sample input and output where that makes review easier

Please avoid broad rewrites, generated boilerplate, or speculative integrations
without a concrete legal or compliance workflow.
