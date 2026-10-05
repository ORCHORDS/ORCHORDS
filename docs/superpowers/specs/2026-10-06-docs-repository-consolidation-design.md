# ORCHORDS Documentation Repository Consolidation — Design

Date: 2026-10-06  
Status: Proposed for implementation  
Canonical company-docs destination: `ORCHORDS/ORCHORDS`

## 1. Goal

Replace `ORCHORDS/docs` as the active source of truth by moving documentation ownership to the repositories that actually own the subject matter, while preserving a single canonical home for company-wide policy and reusable knowledge.

The migration must not create copied policy trees that drift between repositories. Product repositories own product-specific documentation; company-wide governance and reusable documentation are owned centrally.

## 2. Current state

`ORCHORDS/docs` currently contains 18,322 tracked files and is primarily a public, company-wide governance and reusable-knowledge corpus.

Major families include:

- `docs/knowledge/engineering`
- `docs/knowledge/reference`
- `docs/knowledge/platforms`
- `docs/knowledge/operations`
- `docs/knowledge/business`
- `docs/knowledge/data-ai`
- `docs/knowledge/security`
- `docs/knowledge/lessons`
- `docs/knowledge/playbooks`
- `docs/knowledge/standards`
- `docs/knowledge/templates`
- 40+ controlled policy categories under `docs/policies/`

Existing product repositories already contain substantial product-owned documentation:

- `ORCHORDS/W.A.S.P`
- `ORCHORDS/q-pipe`
- `ORCHORDS-LCC/OAI-2.0`
- `ORCHORDS/orchords.com`
- `ORCHORDS/retmo-site`
- `ORCHORDS/gmail-mcp-connector`

The current `ORCHORDS/ORCHORDS` README also depends on `ORCHORDS/docs` for its banner and advertises `ORCHORDS/docs` as a separate public project.

## 3. Ownership model

### 3.1 Company-wide canonical documentation

The following classes move to and remain canonical in `ORCHORDS/ORCHORDS`:

- company governance
- company security policy
- privacy policy framework
- engineering standards
- compliance policy
- legal and records policy
- accessibility policy
- finance, treasury, tax and procurement policy
- people and workplace policy
- reusable technical knowledge
- generic engineering playbooks
- generic security guidance
- standards references
- project-neutral templates
- public assurance and customer-trust documentation

The canonical path remains under `docs/` wherever practical so relative link churn is minimized.

### 3.2 Product repositories

Each product repository owns only documentation tied to that product's implementation, operation, release, architecture, compliance evidence, deployment, issue execution, or product-specific procedures.

Examples:

- W.A.S.P / THEWAM material stays in `ORCHORDS/W.A.S.P`.
- q-pipe runtime, cluster, learner, gateway and worker material stays in `ORCHORDS/q-pipe`.
- OAI-2.0 architecture, training, evaluation, worker and hybrid-model material stays in `ORCHORDS-LCC/OAI-2.0`.
- orchords.com architecture, deployment and Mission Control material stays in `ORCHORDS/orchords.com`.
- Retmo product and verification material stays in `ORCHORDS/retmo-site`.
- Gmail MCP implementation knowledge that names and documents `gmail-mcp-connector` as the actual implementation belongs in `ORCHORDS/gmail-mcp-connector`.

### 3.3 No duplication rule

A document may have exactly one canonical repository.

Product repos may link to company-wide documentation but must not carry copied canonical policy trees solely for convenience.

Where a product requires a product-specific control derived from company policy, the product document should state the product-specific implementation and link to the company-level policy.

## 4. Migration strategy

### Phase A — establish the canonical company-docs tree

1. Import the current company-wide `ORCHORDS/docs` documentation tree into `ORCHORDS/ORCHORDS`.
2. Preserve paths under `docs/` where doing so avoids unnecessary link churn.
3. Preserve root-level governance files where appropriate, including:
   - `SECURITY.md`
   - `CONTRIBUTING.md`
   - `CODE_OF_CONDUCT.md`
   - `LICENSE`
4. Reconcile rather than overwrite any existing `ORCHORDS/ORCHORDS` files.
5. Move the banner asset into the canonical repository so its README no longer depends on `ORCHORDS/docs`.

### Phase B — extract product-owned material

Search the old corpus for content that materially names, describes, or records implementation details for a specific product.

Move that content to the owning repository when it is genuinely product-specific.

Known initial candidates include Gmail MCP engineering notes that explicitly document `gmail-mcp-connector`.

Do not move generic lessons merely because they originated from a product. If the content has already been sanitized into reusable project-neutral guidance, it remains company knowledge.

### Phase C — reconcile product repos

For each product repo:

1. inventory its existing `docs/` tree;
2. identify duplicates or superseded copies;
3. keep the newest authoritative product-specific version;
4. add links to canonical company policy where relevant;
5. update repository READMEs and contributor/security references;
6. avoid replacing current product docs with generic company documents.

### Phase D — rewrite references

Update references that point to `ORCHORDS/docs`, including:

- README links
- badge URLs
- raw asset URLs
- support links
- issue-template links
- citation metadata
- documentation workflows
- CODEOWNERS paths
- scripts that assume the old repository
- any published links under product repositories

External historical links must remain intelligible through the retained archive.

### Phase E — retire the old active source

After the new canonical tree and product-owned migrations are verified:

1. freeze `ORCHORDS/docs`;
2. replace its README with a clear migration notice and destination map;
3. disable routine maintenance there;
4. archive the repository only after confirming that no active automation or public reference still treats it as authoritative.

The old repository is retained as historical evidence and Git history unless a later, separately verified Git-history import proves that all historical references have been preserved elsewhere.

## 5. Git-history policy

The migration must not falsely claim that file history has been preserved in a destination repository when it has only been copied as a snapshot.

Preferred order:

1. preserve historical Git evidence in `ORCHORDS/docs`;
2. where safe and supported, import history using Git-level tooling;
3. otherwise preserve provenance in migration commits and archive the source repository.

A connector-only file copy is not treated as a history-preserving transfer.

## 6. Public/private boundary

The existing public-neutrality rule remains binding.

Company-wide public docs must not absorb:

- private endpoints
- credentials or secret identifiers
- product deployment topology
- internal customer information
- private infrastructure identifiers
- sensitive issue evidence
- operational secrets
- unpublished product plans

Product-specific information goes to the owning product repository only when that repository's visibility and security boundary permit it.

## 7. Repository-specific decisions

### ORCHORDS/ORCHORDS

Becomes the active public company documentation source of truth.

Its README must stop advertising `ORCHORDS/docs` as a separate active project and must use assets hosted inside `ORCHORDS/ORCHORDS`.

### ORCHORDS/W.A.S.P

Keep its current product documentation structure. Do not import the generic company corpus.

Link to company policy where useful; retain product-specific compliance, mobile, operations, release and architecture docs locally.

### ORCHORDS/q-pipe

Keep runtime, gateway, cluster, learner, Android curriculum, benchmarks and operational evidence local.

Do not duplicate generic engineering/security policy trees.

### ORCHORDS-LCC/OAI-2.0

Keep OAI-2.0 architecture, training, hybrid-model, evidence and worker documentation local.

Company-wide standards remain referenced from `ORCHORDS/ORCHORDS`.

### ORCHORDS/orchords.com

Keep website and Mission Control product architecture, deployment and operational docs local.

Company governance/policy references should target `ORCHORDS/ORCHORDS`.

### ORCHORDS/gmail-mcp-connector

Receive genuinely implementation-specific Gmail MCP knowledge currently located in the generic knowledge corpus.

Generic reusable MCP guidance remains centralized.

### ORCHORDS/retmo-site

Keep product roadmap, architecture, verification and security-tooling docs local.

Do not import generic company policy trees.

## 8. Link and provenance rules

Every moved document must have:

- one canonical destination;
- corrected relative links;
- corrected repository URLs;
- no stale `ORCHORDS/docs` dependency unless intentionally historical;
- provenance recorded in the migration commit when copied from the old repository.

Historical citations and release records must not be rewritten in a way that falsifies their original repository context.

## 9. Verification gates

The migration is not complete until all applicable gates pass:

1. file inventory is reconciled between old and new canonical trees;
2. no intended company-wide document is missing;
3. no product-specific document was accidentally made public in the canonical company repo;
4. no unintended duplicate canonical documents exist across repositories;
5. internal Markdown links resolve;
6. repository links resolve;
7. README assets render from their new canonical location;
8. documentation-quality scripts pass in their new home;
9. public-neutrality checks pass;
10. product repositories still retain their existing product-specific docs;
11. searches for active `ORCHORDS/docs` references return only intentional historical/archive references;
12. exact destination commit SHAs are recorded.

## 10. Rollback

Before any destructive deletion or archive action:

- the old repository remains intact;
- destination commits are independently identifiable;
- migrations are additive first;
- retirement happens only after verification.

If verification fails, the destination changes can be reverted while `ORCHORDS/docs` remains the authoritative fallback.

## 11. Completion state

The desired end state is:

- `ORCHORDS/ORCHORDS` — canonical company-wide public documentation and reusable knowledge;
- product repos — canonical product-specific documentation;
- `ORCHORDS/docs` — historical migration/archive repository, no longer an active source of truth;
- no competing canonical copies;
- no broken public links;
- no loss of historical evidence.
