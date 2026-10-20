# FINDINGS — getboring/scopeblind-gateway   (save as repo-docs-review/sheets/getboring__scopeblind-gateway.md)
- reviewed_sha: 01d2d89051566622614010b880906dd437b10c49
- main_moved: no
- default_branch: master / reviewed_at (ET): 2026-10-19 20:24 EDT / reviewer (agent id): bc-875af725-12f2-540e-85bf-71cc05e34c98
- status: DORMANT  evidence: GitHub `isArchived` is false — https://github.com/getboring/scopeblind-gateway — FACT. Head commit `01d2d89051566622614010b880906dd437b10c49` is dated 2026-04-10 22:30:59 -0400 — `git log -1` — FACT. That is 193 days before 2026-10-20 — FACT. DORMANT is the rubric row for an unarchived repo whose last commit is more than 180 days ago — FACT (rubric application).
- live since: not deployed — GitHub deployments list is empty — https://api.github.com/repos/getboring/scopeblind-gateway/deployments — FACT. GitHub Pages GET returned 404 — https://api.github.com/repos/getboring/scopeblind-gateway/pages — FACT. `gh run list -R getboring/scopeblind-gateway --limit 200 --json event,conclusion,createdAt` returned `[]` — FACT.
- what it is (one sentence, from code not docs): Node library and CLI (`protect-mcp`) that proxies an MCP server over stdio, with an optional HTTP listener, intercepts MCP `tools/call` requests, evaluates a local policy, and can write Ed25519-signed decision receipts.
- live where: none

## Docs claim (quote, file:line)

- FACT: `> **⚠️ This repository has moved.** Active development continues at **[ScopeBlind/scopeblind-gateway](https://github.com/ScopeBlind/scopeblind-gateway)**.` — README.md:1 @01d2d89051566622614010b880906dd437b10c49
- FACT: `> This personal fork may be behind the canonical repository. Please use the org repo for issues, pull requests, and the latest code.` — README.md:3 @01d2d89051566622614010b880906dd437b10c49
- FACT: `# protect-mcp` — README.md:5 @01d2d89051566622614010b880906dd437b10c49
- FACT: `# Wrap an existing OpenClaw / MCP config into a usable pack` — README.md:14 @01d2d89051566622614010b880906dd437b10c49
- FACT: `npx @scopeblind/passport wrap --runtime openclaw --config ./openclaw.json --policy email-safe` — README.md:15 @01d2d89051566622614010b880906dd437b10c49
- FACT: `- **Shadow mode** (default): logs every tool call and allows everything through` — README.md:42 @01d2d89051566622614010b880906dd437b10c49
- FACT: `- **Optional local signed receipts** — generated when you run with a policy containing `signing.key_path`, persisted to `.protect-mcp-receipts.jsonl`, and exposed at `http://127.0.0.1:9876/receipts`` — README.md:52 @01d2d89051566622614010b880906dd437b10c49
- FACT: `- **Signing is not automatic on the bare `npx protect-mcp -- ...` path.** That path logs decisions in shadow mode. For local signing, run `npx protect-mcp init` and then start the gateway with the generated policy file.` — README.md:60 @01d2d89051566622614010b880906dd437b10c49
- FACT: `- **Tier-aware policy checks are live, but manifest admission is not wired into the default CLI/stdio path.** The CLI defaults sessions to `unknown` unless a host integration calls the admission API programmatically.` — README.md:61 @01d2d89051566622614010b880906dd437b10c49
- FACT: `- **Credential config currently validates env-backed credential references and records credential labels in logs/receipts.** Generic per-call injection into arbitrary stdio tools is adapter-specific and is not performed by the default proxy path.` — README.md:62 @01d2d89051566622614010b880906dd437b10c49
- FACT: `- **External PDP adapters and audit bundle helpers exist as exported utilities.** They are not yet fully wired into the default CLI path.` — README.md:63 @01d2d89051566622614010b880906dd437b10c49
- FACT: `| `require` | `"any"`, `"none"` | Basic access requirement |` — README.md:96 @01d2d89051566622614010b880906dd437b10c49
- FACT: `  init              Generate Ed25519 keypair + config template` — README.md:135 @01d2d89051566622614010b880906dd437b10c49
- FACT: `  status            Show decision stats and local passport identity` — README.md:136 @01d2d89051566622614010b880906dd437b10c49
- FACT: `  digest            Generate a local human-readable summary` — README.md:137 @01d2d89051566622614010b880906dd437b10c49
- FACT: `  receipts          Show recent persisted signed receipts` — README.md:138 @01d2d89051566622614010b880906dd437b10c49
- FACT: `  bundle            Export an offline-verifiable audit bundle` — README.md:139 @01d2d89051566622614010b880906dd437b10c49
- FACT: `[PROTECT_MCP] {"v":2,"tool":"read_file","decision":"allow","reason_code":"observe_mode","policy_digest":"none","mode":"shadow","timestamp":1710000000}` — README.md:179 @01d2d89051566622614010b880906dd437b10c49
- FACT: `Verify in browser: [scopeblind.com/verify](https://scopeblind.com/verify)` — README.md:189 @01d2d89051566622614010b880906dd437b10c49
- FACT: `Full OWASP Agentic Top 10 mapping: [scopeblind.com/docs/owasp](https://scopeblind.com/docs/owasp)` — README.md:233 @01d2d89051566622614010b880906dd437b10c49
- FACT: `Supports OPA, Cerbos, Cedar (AWS AgentCore), and generic HTTP endpoints:` — README.md:237 @01d2d89051566622614010b880906dd437b10c49
- FACT: `[scopeblind.com](https://scopeblind.com) · [npm](https://www.npmjs.com/package/protect-mcp) · [GitHub](https://github.com/scopeblind/ScopeBlindD2) · [IETF Draft](https://datatracker.ietf.org/doc/draft-farley-acta-signed-receipts/)` — README.md:261 @01d2d89051566622614010b880906dd437b10c49
- FACT: `## v0.3.1 (2026-03-24)` — CHANGELOG.md:3 @01d2d89051566622614010b880906dd437b10c49
- FACT: `- Per-tool policies: `block`, `rate_limit`, `min_tier`, `require_approval`` — CHANGELOG.md:6 @01d2d89051566622614010b880906dd437b10c49
- FACT: `- Policy packs: shadow, web-browsing-safe, email-safe, strict` — CHANGELOG.md:13 @01d2d89051566622614010b880906dd437b10c49
- FACT: `- Shadow mode is the default (renamed from "observe mode")` — CHANGELOG.md:17 @01d2d89051566622614010b880906dd437b10c49
- FACT: No `CLAUDE.md`, `AGENTS.md`, `docs/` tree, `PLAN*`, `ROADMAP*`, `THE-PLAN*`, or `.boring/project.json` is in `git ls-tree -r 01d2d89051566622614010b880906dd437b10c49 --name-only` — FACT.
- OBSERVATION: Markdown docs at this SHA are `README.md` and `CHANGELOG.md` only.

## Code shows (entrypoints, routes, schema, deploy config, CI; file:line)

- FACT: `  "name": "protect-mcp",` — package.json:2 @01d2d89051566622614010b880906dd437b10c49
- FACT: `  "version": "0.4.2",` — package.json:3 @01d2d89051566622614010b880906dd437b10c49
- FACT: `  "mcpName": "io.github.tomjwxf/protect-mcp",` — package.json:4 @01d2d89051566622614010b880906dd437b10c49
- FACT: `"protect-mcp": "dist/cli.js"` — package.json:10 @01d2d89051566622614010b880906dd437b10c49
- FACT: `"build": "tsup src/index.ts src/cli.ts src/demo-server.ts --format cjs,esm --dts --clean"` — package.json:20 @01d2d89051566622614010b880906dd437b10c49
- FACT: `"test": "vitest run"` — package.json:21 @01d2d89051566622614010b880906dd437b10c49
- FACT: `"prepublishOnly": "npm run build"` — package.json:22 @01d2d89051566622614010b880906dd437b10c49
- FACT: `"url": "git+https://github.com/scopeblind/scopeblind-gateway.git"` — package.json:56 @01d2d89051566622614010b880906dd437b10c49
- FACT: `"homepage": "https://www.scopeblind.com"` — package.json:53 @01d2d89051566622614010b880906dd437b10c49
- FACT: Library entry re-exports `ProtectGateway` and does not declare a Worker `fetch` handler (`export default` is absent from `src/`) — src/index.ts:2 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const mode = this.config.enforce ? 'enforce' : 'shadow';` — src/gateway.ts:85 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (message.method === 'tools/call' && message.id !== undefined) {` — src/gateway.ts:187 @01d2d89051566622614010b880906dd437b10c49
- FACT: `this.sendToChild(trimmed);` — src/gateway.ts:191 @01d2d89051566622614010b880906dd437b10c49
- FACT: `private currentTier: TrustTier = 'unknown';` — src/gateway.ts:50 @01d2d89051566622614010b880906dd437b10c49
- FACT: `setManifest(manifest: ManifestPresentation | null): AdmissionResult {` — src/gateway.ts:171 @01d2d89051566622614010b880906dd437b10c49
- OBSERVATION: `setManifest` appears only as that definition. `src/cli.ts` has no `setManifest` call — FACT (search of `src/cli.ts` at this SHA).
- FACT: `default_tier: parsed.default_tier || 'unknown',` is stored on the loaded policy object — src/policy.ts:27 @01d2d89051566622614010b880906dd437b10c49
- OBSERVATION: `src/gateway.ts` does not read `policy.default_tier`. The session tier stays the constructor value unless `setManifest` runs.
- FACT: `const httpPort = parseInt(process.env.PROTECT_MCP_HTTP_PORT || '9876', 10);` — src/gateway.ts:109 @01d2d89051566622614010b880906dd437b10c49
- FACT: `server.listen(config.port, '127.0.0.1', () => {` — src/http-server.ts:136 @01d2d89051566622614010b880906dd437b10c49
- FACT: `GET  /receipts        → recent receipts as JSON array` — src/http-server.ts:10 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const LOG_FILE = '.protect-mcp-log.jsonl';` — src/gateway.ts:25 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const RECEIPTS_FILE = '.protect-mcp-receipts.jsonl';` — src/gateway.ts:26 @01d2d89051566622614010b880906dd437b10c49
- FACT: `process.stderr.write(`[PROTECT_MCP] ${JSON.stringify(log)}\n`);` — src/gateway.ts:462 @01d2d89051566622614010b880906dd437b10c49
- FACT: `timestamp: Date.now(), mode: mode as 'shadow' | 'enforce',` — src/gateway.ts:454 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const reasonCode = this.config.enforce ? 'policy_allow' : 'observe_mode';` — src/gateway.ts:418 @01d2d89051566622614010b880906dd437b10c49
- FACT: `process.stderr.write(`[PROTECT_MCP_RECEIPT] ${signed.signed}\n`);` — src/gateway.ts:469 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (toolPolicy.block) {` — src/gateway.ts:339 @01d2d89051566622614010b880906dd437b10c49
- FACT: `return null;` — src/gateway.ts:344 @01d2d89051566622614010b880906dd437b10c49
- FACT: `} else {` — src/gateway.ts:198 @01d2d89051566622614010b880906dd437b10c49
- FACT: `this.sendToChild(JSON.stringify(modified));` — src/gateway.ts:200 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (toolPolicy.block) {` — src/gateway.ts:339 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (toolPolicy.require_approval) {` — src/gateway.ts:348 @01d2d89051566622614010b880906dd437b10c49
- FACT: `NOTE: v1 does not enforce this field — it is metadata only, logged in decision entries` — src/types.ts:22 @01d2d89051566622614010b880906dd437b10c49
- OBSERVATION: `src/gateway.ts` reads `require_approval` and does not read `toolPolicy.require`.
- FACT: `if (credentials) {` — src/cli.ts:1170 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const warnings = validateCredentials(credentials);` — src/cli.ts:1171 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (credConfig.inject === 'env' && credConfig.name && credConfig.value_env) {` — src/gateway.ts:127 @01d2d89051566622614010b880906dd437b10c49
- FACT: `childEnv[credConfig.name] = envValue;` — src/gateway.ts:130 @01d2d89051566622614010b880906dd437b10c49
- FACT: `return { ...request, params: { ...request.params, _credentials: injections } };` — src/gateway.ts:220 @01d2d89051566622614010b880906dd437b10c49
- FACT: `inject: 'header' | 'query' | 'env';` — src/types.ts:102 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (this.config.policy?.external && (this.config.policy.policy_engine === 'external' || this.config.policy.policy_engine === 'hybrid')) {` — src/gateway.ts:306 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export type PolicyEngineMode = 'built-in' | 'external' | 'hybrid' | 'cedar';` — src/types.ts:51 @01d2d89051566622614010b880906dd437b10c49
- FACT: `case 'opa':` — src/external-pdp.ts:72 @01d2d89051566622614010b880906dd437b10c49
- FACT: `case 'cerbos':` — src/external-pdp.ts:85 @01d2d89051566622614010b880906dd437b10c49
- FACT: `case 'cedar':` — src/external-pdp.ts:103 @01d2d89051566622614010b880906dd437b10c49
- FACT: `case 'generic':` — src/external-pdp.ts:129 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const timeout = config.timeout_ms || 500;` — src/external-pdp.ts:31 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const fallback = config.fallback || 'deny';` — src/external-pdp.ts:206 @01d2d89051566622614010b880906dd437b10c49
- FACT: `Supports OPA, Cerbos, Cedar (AWS), and generic JSON formats.` — src/external-pdp.ts:7 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (args[0] === 'bundle') {` — src/cli.ts:1069 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const { createAuditBundle } = await import('./bundle.js');` — src/cli.ts:679 @01d2d89051566622614010b880906dd437b10c49
- FACT: `format: 'scopeblind:audit-bundle';` — src/bundle.ts:47 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (!existsSync(receiptsPath)) {` — src/cli.ts:693 @01d2d89051566622614010b880906dd437b10c49
- FACT: `process.exit(0);` — src/cli.ts:695 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (!existsSync(keyPath)) {` — src/cli.ts:698 @01d2d89051566622614010b880906dd437b10c49
- FACT: `process.exit(1);` — src/cli.ts:700 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (args[0] === 'quickstart') {` — src/cli.ts:1034 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (args[0] === 'init') {` — src/cli.ts:1040 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (args[0] === 'doctor') {` — src/cli.ts:1092 @01d2d89051566622614010b880906dd437b10c49
- FACT: `protect-mcp simulate --policy <path> [--log <path>] [--tier <tier>] [--json]` — src/cli.ts:48 @01d2d89051566622614010b880906dd437b10c49
- FACT: `protect-mcp report [--period <days>d] [--format md|json] [--output <path>] [--dir <path>]` — src/cli.ts:49 @01d2d89051566622614010b880906dd437b10c49
- FACT: `--http            Start HTTP/SSE server instead of stdio proxy` — src/cli.ts:56 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const useHttp = args.includes('--http');` — src/cli.ts:1190 @01d2d89051566622614010b880906dd437b10c49
- FACT: `npx protect-mcp --http --port 3000 -- node your-server.js` — src/http-transport.ts:13 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (url.pathname === '/health' && req.method === 'GET') {` — src/http-transport.ts:63 @01d2d89051566622614010b880906dd437b10c49
- FACT: `version: '0.4.0',` — src/http-transport.ts:68 @01d2d89051566622614010b880906dd437b10c49
- FACT: Status server `/health` returns `version: '0.3.1'` — src/http-server.ts:154 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const configPath = join(process.cwd(), 'scopeblind.config.json');` — src/cli.ts:1287 @01d2d89051566622614010b880906dd437b10c49
- FACT: `init` writes `protect-mcp.json` — src/cli.ts:161 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const logFile = join(process.cwd(), 'protect-mcp-decisions.jsonl');` — src/cli.ts:1344 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const receiptFile = join(process.cwd(), 'protect-mcp-receipts.jsonl');` — src/cli.ts:1345 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (!parsed.tools || typeof parsed.tools !== 'object') {` — src/policy.ts:21 @01d2d89051566622614010b880906dd437b10c49
- FACT: `missing "tools" object` — src/policy.ts:22 @01d2d89051566622614010b880906dd437b10c49
- FACT: `name = "scopeblind-gateway"` — wrangler.toml:1 @01d2d89051566622614010b880906dd437b10c49
- FACT: `main = "src/index.ts"` — wrangler.toml:2 @01d2d89051566622614010b880906dd437b10c49
- FACT: `ORIGIN_URL = "https://your-backend-api.com"` — wrangler.toml:7 @01d2d89051566622614010b880906dd437b10c49
- FACT: `SCOPEBLIND_AUDIENCE = "YOUR_SLUG"` — wrangler.toml:11 @01d2d89051566622614010b880906dd437b10c49
- FACT: `SCOPEBLIND_JWKS_URL = "https://api.scopeblind.com/.well-known/jwks.json"` — wrangler.toml:14 @01d2d89051566622614010b880906dd437b10c49
- FACT: `OBSERVE_MODE = "true"` — wrangler.toml:19 @01d2d89051566622614010b880906dd437b10c49
- FACT: `  "name": "io.github.tomjwxf/protect-mcp",` — server.json:3 @01d2d89051566622614010b880906dd437b10c49
- FACT: `  "version": "0.4.0",` — server.json:9 @01d2d89051566622614010b880906dd437b10c49
- FACT: `"url": "https://github.com/scopeblind/ScopeBlindD2"` — server.json:6 @01d2d89051566622614010b880906dd437b10c49
- FACT: `RUN npm install -g protect-mcp@latest` — Dockerfile:7 @01d2d89051566622614010b880906dd437b10c49
- FACT: Policy files with a `tools` object: `policies/clinejection.json:13`, `policies/data-exfiltration.json:12`, `policies/financial-safe.json:14`, `policies/github-mcp-hijack.json:13`, `policies/terraform-destroy.json:13` @01d2d89051566622614010b880906dd437b10c49
- FACT: `policies/claude-code-hooks.json:3` is a `hooks` document. It has no `tools` key — policies/claude-code-hooks.json:3 @01d2d89051566622614010b880906dd437b10c49
- FACT: Cedar files present: `policies/cedar/clinejection.cedar`, `policies/cedar/terraform-destroy.cedar` — `git ls-tree` at this SHA — FACT.
- FACT: Tests under `src/`: `admission.test.ts`, `bundle.test.ts`, `cedar-evaluator.test.ts`, `credentials.test.ts`, `evidence-store.test.ts`, `manifest.test.ts`, `policy.test.ts`, `simulate.test.ts`. None import `ProtectGateway` — FACT (search of `src/*.test.ts`).
- FACT: No `.github/workflows/` path in `git ls-tree -r 01d2d89051566622614010b880906dd437b10c49 --name-only` — FACT. Contents API 404 — https://api.github.com/repos/getboring/scopeblind-gateway/contents/.github/workflows — FACT.
- FACT: `describe('loadPolicy'` — src/policy.test.ts:12 @01d2d89051566622614010b880906dd437b10c49
- FACT: `describe('evaluateTier'` — src/admission.test.ts:5 @01d2d89051566622614010b880906dd437b10c49
- FACT: `describe('resolveCredential'` — src/credentials.test.ts:5 @01d2d89051566622614010b880906dd437b10c49
- FACT: `describe('createAuditBundle'` — src/bundle.test.ts:4 @01d2d89051566622614010b880906dd437b10c49
- FACT: `describe('simulate'` — src/simulate.test.ts:8 @01d2d89051566622614010b880906dd437b10c49
- FACT: `describe('loadCedarPolicies'` — src/cedar-evaluator.test.ts:11 @01d2d89051566622614010b880906dd437b10c49
- FACT: `describe('isAgentId'` — src/manifest.test.ts:15 @01d2d89051566622614010b880906dd437b10c49
- FACT: `describe('EvidenceStore'` — src/evidence-store.test.ts:7 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { anchorToRekor, verifyRekorAnchor, hashReceipt, createLogAnchorField } from './rekor-anchor.js';` — src/index.ts:94 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { redactFields, revealField, verifyCommitment, verifyAllCommitments, createDisclosurePackage } from './selective-disclosure.js';` — src/index.ts:98 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { sendApprovalNotification, parseNotificationConfigFromEnv } from './notifications.js';` — src/index.ts:102 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { receiptsToHFRows, generateHFMetadata, exportJSONL, generateDatasetCard } from './huggingface-export.js';` — src/index.ts:106 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { ed25519ToDIDKey, manifestToVC, receiptToVP } from './did-vc.js';` — src/index.ts:119 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { createSandbox, runInSandbox, generateSafetyTranscript, destroySandbox } from './sandbox.js';` — src/index.ts:122 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { createC2PAManifest, exportC2PAManifestJSON, generateC2PACommand, verifyActaC2PAAssertions } from './c2pa-credentials.js';` — src/index.ts:130 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { computeCalibration, toMetaculusFormat, toManifoldFormat } from './prediction-bridge.js';` — src/index.ts:134 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { ReceiptPropagator, createReceiptChannel } from './agent-exchange.js';` — src/index.ts:138 @01d2d89051566622614010b880906dd437b10c49
- FACT: `export { ConfidentialGate, confidentialInference } from './confidential.js';` — src/index.ts:142 @01d2d89051566622614010b880906dd437b10c49

## Workflows | file | jobs | triggers | runs by event (success/failure/other, `gh run list --workflow <file> --limit 200`) | first and last run (ET) |

| file | jobs | triggers | runs by event | first and last run (ET) |
| --- | --- | --- | --- | --- |
| none. `.github/workflows/` is not in the tree at 01d2d89051566622614010b880906dd437b10c49. GitHub contents URL returned 404: https://api.github.com/repos/getboring/scopeblind-gateway/contents/.github/workflows | no `jobs:` keys | no `on:` keys | Repo-level `gh run list -R getboring/scopeblind-gateway --limit 200 --json event,conclusion,createdAt` returned `[]` (0 rows). No per-file `--workflow` list was run because there is no workflow file. | no `createdAt` values in that list, so no ET conversion |

## Features | feature | state | evidence |

| feature | state | evidence |
| --- | --- | --- |
| stdio MCP proxy; shadow unless `--enforce` | PARTIAL | code src/gateway.ts:85 and src/gateway.ts:187 @01d2d89051566622614010b880906dd437b10c49 — FACT. No test imports `ProtectGateway` — FACT. |
| `loadPolicy` / `getToolPolicy` / rate-limit parse | DONE | src/policy.test.ts:12 and src/policy.ts:74 @01d2d89051566622614010b880906dd437b10c49 — FACT |
| `require` enforcement | NOT STARTED | README.md:96 claims a basic access requirement — FACT. src/types.ts:22 says v1 does not enforce the field — FACT. `src/gateway.ts` does not read `toolPolicy.require` — OBSERVATION |
| `require_approval` on the live proxy | PARTIAL | src/gateway.ts:348 @01d2d89051566622614010b880906dd437b10c49 — FACT. No gateway test — FACT |
| `simulate()` | DONE | src/simulate.test.ts:8 @01d2d89051566622614010b880906dd437b10c49 — FACT |
| `evaluateTier` / `meetsMinTier` | DONE | src/admission.test.ts:5 @01d2d89051566622614010b880906dd437b10c49 — FACT |
| CLI manifest admission | NOT STARTED | README.md:61 says it is not wired — FACT. src/gateway.ts:171 defines `setManifest`. A search of `src/cli.ts` at this SHA finds no `setManifest` call — FACT |
| credential resolve / validate | DONE | src/credentials.test.ts:5 @01d2d89051566622614010b880906dd437b10c49 — FACT |
| child-env and `params._credentials` injection | PARTIAL | src/gateway.ts:127 and src/gateway.ts:220 @01d2d89051566622614010b880906dd437b10c49 — FACT. No test of `ProtectGateway` — FACT |
| Ed25519 decision receipts | PARTIAL | src/gateway.ts:469 @01d2d89051566622614010b880906dd437b10c49 — FACT. No `signing.test.ts` — FACT |
| localhost receipt HTTP server | PARTIAL | src/http-server.ts:136 @01d2d89051566622614010b880906dd437b10c49 — FACT. No test file — FACT |
| `createAuditBundle` | DONE | src/bundle.test.ts:4 @01d2d89051566622614010b880906dd437b10c49 — FACT |
| `protect-mcp bundle` CLI | PARTIAL | src/cli.ts:1069 @01d2d89051566622614010b880906dd437b10c49 — FACT. No CLI test — FACT |
| external PDP from the stdio gateway | PARTIAL | src/gateway.ts:306 and src/external-pdp.ts:72 @01d2d89051566622614010b880906dd437b10c49 — FACT. No external-PDP test file — FACT |
| Cedar policy load | DONE | src/cedar-evaluator.test.ts:11 @01d2d89051566622614010b880906dd437b10c49 — FACT |
| manifest validators | DONE | src/manifest.test.ts:15 @01d2d89051566622614010b880906dd437b10c49 — FACT |
| evidence store | DONE | src/evidence-store.test.ts:7 @01d2d89051566622614010b880906dd437b10c49 — FACT. README has no evidence-store section — OBSERVATION. State for the README claim is UNDOCUMENTED |
| HTTP/SSE `--http` transport | UNDOCUMENTED | src/cli.ts:56 and src/http-transport.ts:13 @01d2d89051566622614010b880906dd437b10c49 — FACT. README command list is README.md:135 through README.md:139 — FACT |
| `quickstart`, `demo`, `doctor`, `trace`, `report` | UNDOCUMENTED | handlers src/cli.ts:1034, src/cli.ts:1092, src/cli.ts:49 @01d2d89051566622614010b880906dd437b10c49 — FACT. README command list is README.md:135 through README.md:139 — FACT. CHANGELOG.md:12 names `protect-mcp report` — FACT, so `report` is claimed in the changelog and absent from the README command list |
| Rekor, selective disclosure, notifications, Hugging Face export, WebAuthn approval, DID/VC, E2B sandbox, evidence attestation, C2PA, prediction bridge, receipt propagator, confidential gate | UNDOCUMENTED | exported src/index.ts:94, src/index.ts:98, src/index.ts:102, src/index.ts:106, src/index.ts:119, src/index.ts:122, src/index.ts:130, src/index.ts:134, src/index.ts:138, src/index.ts:142 @01d2d89051566622614010b880906dd437b10c49 — FACT. No matching README section — OBSERVATION |
| incident JSON policy packs | PARTIAL | tools objects at policies/clinejection.json:13, policies/data-exfiltration.json:12, policies/financial-safe.json:14, policies/github-mcp-hijack.json:13, policies/terraform-destroy.json:13 @01d2d89051566622614010b880906dd437b10c49 — FACT. No pack test — FACT |
| Cloudflare pass-token Worker described by wrangler.toml | NOT STARTED | wrangler.toml:1 and wrangler.toml:2 @01d2d89051566622614010b880906dd437b10c49 — FACT. src/index.ts:2 exports a library and the tree has no `fetch` handler — FACT |

## Drift | doc says | code shows | severity | cite |

| doc says | code shows | severity | cite |
| --- | --- | --- | --- |
| README.md:96 `require` values `"any"`, `"none"` are a "Basic access requirement" | src/types.ts:22 says v1 does not enforce the field. `src/gateway.ts` does not read `toolPolicy.require`. The type also allows `"gateway"` (src/types.ts:20). | HIGH | README.md:96, src/types.ts:20, src/types.ts:22 @01d2d89051566622614010b880906dd437b10c49 |
| README.md:62 says generic per-call injection "is not performed by the default proxy path" | src/gateway.ts:130 copies an env credential onto the child environment at startup. src/gateway.ts:220 adds `params._credentials` for header and query injection. src/cli.ts:1171 calls `validateCredentials`. | HIGH | README.md:62, src/gateway.ts:130, src/gateway.ts:220, src/cli.ts:1171 @01d2d89051566622614010b880906dd437b10c49 |
| README.md:63 says external PDP adapters and audit bundle helpers "are not yet fully wired into the default CLI path" | src/gateway.ts:306 calls the external PDP when `policy_engine` is `external` or `hybrid`. src/cli.ts:1069 runs `bundle`, which calls `createAuditBundle` (src/cli.ts:679). Both are also exported from src/index.ts:18 and src/index.ts:21. | HIGH | README.md:63, src/gateway.ts:306, src/cli.ts:1069, src/index.ts:18, src/index.ts:21 @01d2d89051566622614010b880906dd437b10c49 |
| README.md:15 quick start runs `npx @scopeblind/passport wrap` | This package bin is `protect-mcp` → `dist/cli.js` (package.json:10). `src/cli.ts` has no `wrap` command. npm registry package `@scopeblind/passport` exists, latest `0.4.3`, bin name `passport` — https://registry.npmjs.org/@scopeblind/passport — FACT. Whether that package accepts this exact argv is UNKNOWN (this review did not execute it). | HIGH | README.md:15, package.json:10 @01d2d89051566622614010b880906dd437b10c49 |
| wrangler.toml:1 names Worker `scopeblind-gateway`, main `src/index.ts`, JWKS pass-token vars, `OBSERVE_MODE` | src/index.ts:2 exports `ProtectGateway`. No Worker `fetch` handler is in `src/`. `ORIGIN_URL` is the placeholder `https://your-backend-api.com` (wrangler.toml:7). | HIGH | wrangler.toml:1, wrangler.toml:2, wrangler.toml:7, src/index.ts:2 @01d2d89051566622614010b880906dd437b10c49 |
| README.md:233 links a full OWASP mapping at `https://scopeblind.com/docs/owasp` | GET of that URL returned HTTP 404 on 2026-10-19. GET `https://scopeblind.com/docs` returned HTTP 200 and the body had zero `owasp` matches. | LOW | README.md:233 @01d2d89051566622614010b880906dd437b10c49 ; https://scopeblind.com/docs/owasp |
| README.md:261 GitHub link `https://github.com/scopeblind/ScopeBlindD2` | GET returned HTTP 404 on 2026-10-19. package.json:56 records `git+https://github.com/scopeblind/scopeblind-gateway.git`. GET `https://github.com/scopeblind/scopeblind-gateway` returned HTTP 200 and GitHub resolves that URL to https://github.com/ScopeBlind/scopeblind-gateway | LOW | README.md:261, package.json:56 @01d2d89051566622614010b880906dd437b10c49 |
| CHANGELOG.md:13 "Policy packs: shadow, web-browsing-safe, email-safe, strict" | Those filenames are absent from `git log --all --diff-filter=A --summary`. The tree has the five `tools` JSON packs listed above. `git ls-tree -r 9a6435a8637158ebfc35520746e19ff1b3c16f5a --name-only` (changelog add, 2026-03-25) has no `policies/` directory. Policies arrived in `e575fda78ce550add56f22ff96481b0d2855e485`. | LOW | CHANGELOG.md:13 @01d2d89051566622614010b880906dd437b10c49 ; commit e575fda78ce550add56f22ff96481b0d2855e485 |
| CHANGELOG.md newest heading is v0.3.1 | package.json:3 is `0.4.2`. server.json:9 is `0.4.0`. src/http-server.ts:154 hardcodes `0.3.1`. src/http-transport.ts:68 hardcodes `0.4.0`. | LOW | CHANGELOG.md:3, package.json:3, server.json:9, src/http-server.ts:154, src/http-transport.ts:68 @01d2d89051566622614010b880906dd437b10c49 |
| README.md:135 through README.md:139 list init, status, digest, receipts, bundle | src/cli.ts also dispatches quickstart (src/cli.ts:1034), demo, doctor (src/cli.ts:1092), trace, simulate (src/cli.ts:48), report (src/cli.ts:49), and `--http` (src/cli.ts:56). | LOW | README.md:135, src/cli.ts:48, src/cli.ts:49, src/cli.ts:56, src/cli.ts:1034, src/cli.ts:1092 @01d2d89051566622614010b880906dd437b10c49 |
| README.md:237 "Cedar (AWS AgentCore)" | src/external-pdp.ts:7 says "Cedar (AWS)". The format string is `cedar` (src/external-pdp.ts:103). The source has no `AgentCore` identifier. | LOW | README.md:237, src/external-pdp.ts:7, src/external-pdp.ts:103 @01d2d89051566622614010b880906dd437b10c49 |
| README.md:179 sample log uses `timestamp":1710000000` and omits `policy_engine`, `request_id`, `otel_trace_id`, `otel_span_id` | src/gateway.ts:454 sets `timestamp` from `Date.now()`. src/gateway.ts:448 through src/gateway.ts:459 always set `v`, `policy_engine`, `request_id`, `otel_trace_id`, and `otel_span_id`. `reason_code` `observe_mode` with `mode` `shadow` matches the no-rate-limit shadow branch (src/gateway.ts:418). | LOW | README.md:179, src/gateway.ts:418, src/gateway.ts:454 @01d2d89051566622614010b880906dd437b10c49 |

Rows that match and are not drift:

- FACT: Shadow mode logs and, when `enforce` is false, deny branches return null so the call is forwarded — README.md:42, src/gateway.ts:85, src/gateway.ts:339 @01d2d89051566622614010b880906dd437b10c49
- FACT: `if (signing) {` — src/cli.ts:1162 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const warnings = await initSigning(signing);` — src/cli.ts:1163 @01d2d89051566622614010b880906dd437b10c49
- FACT: `private currentTier: TrustTier = 'unknown';` — src/gateway.ts:50 @01d2d89051566622614010b880906dd437b10c49
- FACT: README.md:61 says the CLI defaults sessions to `unknown` — README.md:61 @01d2d89051566622614010b880906dd437b10c49
- FACT: Receipt file and default listen address match README.md:52 — src/gateway.ts:26, src/gateway.ts:109, src/http-server.ts:136 @01d2d89051566622614010b880906dd437b10c49
- FACT: `https://scopeblind.com/verify` returned HTTP 200 on 2026-10-19 — README.md:189
- FACT: `https://datatracker.ietf.org/doc/draft-farley-acta-signed-receipts/` returned HTTP 200 on 2026-10-19 — README.md:261
- FACT: `https://api.scopeblind.com/health` returned HTTP 200 on 2026-10-19. `https://api.scopeblind.com/.well-known/jwks.json` returned HTTP 200 with 1 public OKP key and no private `d` field. This repo's GitHub deployments list is empty, so those hosts are not a deploy record for this SHA.

## Confusing names | where | name | conflicts with |

| where | name | conflicts with |
| --- | --- | --- |
| GitHub repo | `getboring/scopeblind-gateway` — https://github.com/getboring/scopeblind-gateway — FACT | README.md:5 title `protect-mcp`; package.json:2 `protect-mcp`; wrangler.toml:1 `scopeblind-gateway` |
| package.json:4 | `io.github.tomjwxf/protect-mcp` | server.json:3 same string; repo owner `getboring`; parent owner `tomjwxf` — https://github.com/tomjwxf/scopeblind-gateway — FACT |
| package.json:56 | `scopeblind/scopeblind-gateway` | README.md:1 `ScopeBlind/scopeblind-gateway`; README.md:261 `scopeblind/ScopeBlindD2`; server.json:6 `scopeblind/ScopeBlindD2`; Dockerfile label source `scopeblind/ScopeBlindD2` (Dockerfile:4) |
| package.json:3 | `0.4.2` | CHANGELOG.md:3 `v0.3.1`; server.json:9 `0.4.0`; src/http-server.ts:154 `0.3.1`; src/http-transport.ts:68 `0.4.0`; npm `protect-mcp` dist-tag `latest` is `0.31.1` published 2026-10-07T00:13:23.186Z with repository `git+https://github.com/ScopeBlind/scopeblind-gateway.git` — https://registry.npmjs.org/protect-mcp — FACT |
| src/cli.ts:161 | `protect-mcp.json` | src/cli.ts:1287 `scopeblind.config.json` |
| src/gateway.ts:25 | `.protect-mcp-log.jsonl` | src/cli.ts:1344 `protect-mcp-decisions.jsonl` |
| src/gateway.ts:26 | `.protect-mcp-receipts.jsonl` | src/cli.ts:1345 `protect-mcp-receipts.jsonl` |
| README.md:15 | `@scopeblind/passport` | package.json:2 `protect-mcp` |
| glama.json:3 | maintainers `scopeblind`, `tomjwxf` | repo `getboring/scopeblind-gateway` |
| domain strings | `scopeblind.com` (README.md:261), `www.scopeblind.com` (package.json:53), `api.scopeblind.com` (wrangler.toml:14) | wrangler.toml:7 placeholder `your-backend-api.com` |

## Possible overlap (record only, no verdict)

- FACT: This repo is a fork. Parent is `tomjwxf/scopeblind-gateway`. `gh api repos/getboring/scopeblind-gateway/compare/master...tomjwxf:master` returned `status` `identical`, `ahead_by` 0, `behind_by` 0 — https://github.com/tomjwxf/scopeblind-gateway
- FACT: `ScopeBlind/scopeblind-gateway` exists, `isArchived` false, default branch `main`, `pushedAt` `2026-10-07T01:11:35Z`, `isFork` true, parent `tomjwxf/scopeblind-gateway` — https://github.com/ScopeBlind/scopeblind-gateway
- FACT: README.md:1 names that GitHub URL as where active development continues.
- FACT: npm `protect-mcp` was created `2026-03-14T10:00:58.072Z`. Version `0.4.2` time is `2026-03-27T11:35:40.637Z` and that version's repository URL is `git+https://github.com/tomjwxf/scopeblind-gateway.git` — https://registry.npmjs.org/protect-mcp
- FACT: `gh repo view Boring-Works/scopeblind-gateway` returned `Could not resolve to a Repository` — FACT.
- FACT: `@scopeblind/passport` latest `0.4.3` describes itself as a portable identity and local pack builder with create/wrap CLI flows — https://registry.npmjs.org/@scopeblind/passport — FACT. It is a different npm package from `protect-mcp`.

## UNKNOWN / questions

- UNKNOWN: README patent sentence ("4 Australian provisional patents pending") has no file, commit, or registry citation in this review.
- UNKNOWN: Whether `npx @scopeblind/passport wrap --runtime openclaw --config ./openclaw.json --policy email-safe` succeeds. The npm package exists. This review did not execute it.
- UNKNOWN: Any Cloudflare Worker named `scopeblind-gateway` created outside this repo's GitHub deployments. No Cloudflare account call was made.
- UNKNOWN: Why GitHub `pushedAt` for `getboring/scopeblind-gateway` is `2026-07-03T05:22:18Z` while the newest commit is `2026-04-10`. `createdAt` is `2026-08-02T20:21:52Z` — https://github.com/getboring/scopeblind-gateway
- UNKNOWN: Whether `https://scopeblind.com/verify` accepts a receipt produced by `src/signing.ts`. The URL returned HTTP 200. The page was not treated as proof of this SHA.
- UNKNOWN: `https://www.npmjs.com/package/protect-mcp` returned HTTP 403 from this environment. The registry URL above returned the package metadata.
- FACT: `const configPath = join(process.cwd(), 'scopeblind.config.json');` — src/cli.ts:1287 @01d2d89051566622614010b880906dd437b10c49
- FACT: `process.stdout.write(yellow('No scopeblind.config.json — run: protect-mcp init\n'));` — src/cli.ts:1302 @01d2d89051566622614010b880906dd437b10c49
- FACT: `} else {` — src/cli.ts:1301 @01d2d89051566622614010b880906dd437b10c49
- OBSERVATION: The else body is the print on src/cli.ts:1302 and closes on the next line. It does not contain `issues++` and it does not throw.
- FACT: `const logFile = join(process.cwd(), 'protect-mcp-decisions.jsonl');` — src/cli.ts:1344 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const configPath = join(dir, 'protect-mcp.json');` — src/cli.ts:161 @01d2d89051566622614010b880906dd437b10c49
- FACT: `const LOG_FILE = '.protect-mcp-log.jsonl';` — src/gateway.ts:25 @01d2d89051566622614010b880906dd437b10c49

## Self-check
- [x] Re-opened every cited file:line at reviewed_sha; each quote is word-for-word on that line (list any fixed). Fixed before commit: README command lines are 135–139 (bundle is README.md:139); `process.exit(0)` is src/cli.ts:695 and `process.exit(1)` is src/cli.ts:700; `validateCredentials` call is src/cli.ts:1171; `initSigning` call is src/cli.ts:1163; changelog `protect-mcp report` is CHANGELOG.md:12; doctor missing-config print is src/cli.ts:1302 and that branch does not increment `issues`.
- [x] Every HIGH drift row is a wrong current-state claim about product, deploy or data; history gaps are LOW.
- [x] Every workflow file under .github/workflows/ is in the Workflows table.
- [x] No SUPERSEDED-BY / DUPLICATE-OF / DEAD / CANONICAL verdicts; no recommendations outside Naming suggestions.

## Naming suggestions (ideas only, no action)

| strings in play | idea |
| --- | --- |
| `getboring/scopeblind-gateway`, `scopeblind-gateway` (wrangler.toml:1), `protect-mcp` (package.json:2, README.md:5), `io.github.tomjwxf/protect-mcp` (package.json:4, server.json:3), `scopeblind/ScopeBlindD2` (README.md:261, server.json:6) | `scopeblind-gateway` for the repo, Worker, and package; `protect-mcp` for the bin only |
| `protect-mcp.json` (src/cli.ts:161), `scopeblind.config.json` (src/cli.ts:1287) | `protect-mcp.json` |
| `.protect-mcp-log.jsonl` (src/gateway.ts:25), `protect-mcp-decisions.jsonl` (src/cli.ts:1344) | `.protect-mcp-log.jsonl` |
| `.protect-mcp-receipts.jsonl` (src/gateway.ts:26), `protect-mcp-receipts.jsonl` (src/cli.ts:1345) | `.protect-mcp-receipts.jsonl` |
| `0.4.2` (package.json:3), `0.4.0` (server.json:9, src/http-transport.ts:68), `0.3.1` (CHANGELOG.md:3, src/http-server.ts:154) | `0.4.2` |
| `scopeblind.com`, `www.scopeblind.com`, `api.scopeblind.com`, `your-backend-api.com` | `scopeblind.com` and `api.scopeblind.com` |
