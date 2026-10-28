Software engineer. Agent tooling, eval harnesses, vulnerability research.

- [beardthelion.dev](https://beardthelion.dev)
- [X](https://x.com/beardthelyon)

## Security research

Reported vulnerabilities:

| Advisory | Finding | Severity | Fix |
| --- | --- | --- | --- |
| [GHSA-fm7v-38h4-4q7w](https://github.com/AgentDeskAI/browser-tools-mcp/security/advisories/GHSA-fm7v-38h4-4q7w) | SSRF in the Lighthouse audit tools of `@agentdeskai/browser-tools-mcp`. URL validation checked scheme only, so the audit browser could reach loopback, private network, and cloud metadata addresses, and the report screenshot exposed the rendered internal page | High (CVSS 7.4) | Fixed in 2.0.3 |

In triage (details withheld until the vendor publishes):

| Report | Status |
| --- | --- |
| Report filed Oct 26 | In triage with the vendor |
| Report filed Oct 20 | In triage with the vendor |
| Report filed Oct 8 | In triage with the vendor |
| Report filed Oct 8 | In triage with the vendor |
| Report filed Sep 14 | In triage with the vendor |

Detection work:

- **[cve-variant-sweep](https://github.com/beardthelion/cve-variant-sweep)**: Validated Semgrep rules from recent guard-adding CVE fixes, for variant hunting. 75 verified rules, all pushed with test evidence. One generalized variant flagged a live sibling instance in Pillow that the advisory fix missed.
- **[RedPen Eval](https://github.com/beardthelion/redpen-eval)**: Eval harness that grades AI code reviewers against real CVE-derived vulnerability cases. 48 seeded cases, ground truth from the sweep rule corpus.
- **[ssrf-guard-audit](https://github.com/beardthelion/ssrf-guard-audit)**: Guard-completeness audit for SSRF defenses: classifies how each caller-controlled URL fetch site is incomplete, not just whether a sink exists.
- **[mcp-ssrf-audit](https://github.com/beardthelion/mcp-ssrf-audit)**: The same guard-completeness audit applied to MCP servers, with Semgrep rules, CLI, and labeled corpus.
- **[path-guard-audit](https://github.com/beardthelion/path-guard-audit)**: Static audit of incomplete filesystem and archive path guards in Python and TypeScript.
- **[egress-plane](https://github.com/beardthelion/egress-plane)**: Static egress scanner across Rust, Python, JavaScript, TypeScript, and Go, with blind spots declared and completeness reported in its exit code.
- **dyetrace** (private): Black-box dataflow tracer: injects a unique tracer into every observed input of a recorded session, re-drives read surfaces, and flags tracers resurfacing where they should never reach.

## Building

- **[signet](https://github.com/beardthelion/signet)**: Self-sovereign agent state: DID-rooted, end-to-end-encrypted, portable memory, config, transcripts, and permission grants as ciphertext the store can never read. Crypto-blind sync store, MCP adapter, conformance checker.
- **[memval](https://github.com/beardthelion/memval)**: Eval harness: an agent with no memory versus encrypted memory backends, scored three-way with red-check controls.
- **[hermes-skill-distillation](https://github.com/beardthelion/hermes-skill-distillation)**: Real-world agent trajectories for Hermes 4: task battery, judge, SFT export, Atropos RL.
- **[subprompt](https://github.com/beardthelion/subprompt)**: Hermes plugin that resolves `{{fuzzy description}}` markers before the model reads the message.
- **[openbeard](https://github.com/beardthelion/openbeard)**: Gemini CLI fork: OpenAI-compatible, MiMo reasoning, tool calling.
- **[hermes-sendblue-plugin](https://github.com/beardthelion/hermes-sendblue-plugin)**: Sendblue iMessage/SMS/RCS for Hermes Agent.

## Contributing to

Maintainer on the Twigpine org (formerly Gitlawb):

- **[twigpine/node](https://github.com/twigpine/node)**: Path-scoped visibility on git and IPFS surfaces; withheld IPFS subtrees no longer leak through tree objects; peer rows bound to DID so only the keyholder can repoint them; peer-supplied repo slugs cannot escape `repos_dir`.
- **[twigpine/openclaude](https://github.com/twigpine/openclaude)**: Per-turn simple-vs-strong auto-routing; WebFetch SSRF-guard regression test; MCP skills from `skill://` resources.
- **[twigpine/zero](https://github.com/twigpine/zero)**: Workspace-trust gate for hooks, plugins, and MCP; normalize launcher names before the sandbox command-prefix denylist.
- **[twigpine/openrecall](https://github.com/twigpine/openrecall)**: Zero-knowledge encrypted memory for AI agents. Hash namespace into slug so tenants cannot collide.

Upstream contributions:

- **[NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent)**: 89 authored PRs, including opencode-go routing for `qwen3.7-max` via `anthropic_messages`.
- **[CopilotKit/OpenBot](https://github.com/CopilotKit/OpenBot)**: MCP tokens only for their own server at their own address; refuse a credential written into the rest of the address; Docker socket on loopback, not every host address.
- **[ApeWorX/ape](https://github.com/ApeWorX/ape)**: Resolve overloaded methods by argument type, not just count.
- **[vercel-labs/fx](https://github.com/vercel-labs/fx)**: Write MCP config durably instead of truncating it in place; keep the MCP session id alive until in-flight requests drain.
- **[laude-institute/headlong](https://github.com/laude-institute/headlong)**: API keys off the docker command line; a sibling directory is not a mounted one.
- **[sooperset/mcp-atlassian](https://github.com/sooperset/mcp-atlassian)**: Convert markdown in Jira text-area custom fields to ADF.
- **[OpenListTeam/OpenList](https://github.com/OpenListTeam/OpenList)**: Stop the upload retry loop when the context is canceled.

## Stack

Rust, Python, JavaScript, TypeScript, Java with Spring and microservices, SQL.
