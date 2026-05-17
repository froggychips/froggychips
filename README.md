# froggychips

Self-taught. Day job: SRE on a live game backend that fails loudly when I'm wrong. Off-hours: getting 8 GB Macs to do more than they were sold for, plumbing Claude Code into things it probably shouldn't touch yet, and trying to make MCP boring.

## Froggy ecosystem

Four repos built around one idea: a private local LLM daemon that knows what's on your screen.

| Repo | What it does |
|---|---|
| [Froggy](https://github.com/froggychips/Froggy) | Local LLM + screen OCR daemon for 8 GB Apple Silicon Macs. Memory management, sliding context window, private inference. Core of the ecosystem. |
| [FroggyKit](https://github.com/froggychips/FroggyKit) | Shared Swift package — FroggyClient IPC, used by froggy-mcp and froggy-sre. |
| [froggy-mcp](https://github.com/froggychips/froggy-mcp) | MCP server — connects Claude Code to Froggy over a Unix socket. Cloud model, local eyes. |
| [froggy-sre](https://github.com/froggychips/froggy-sre) | SRE incident response agent — feed a Kubernetes alert, get back root cause + fix + risk in one MCP call. Routes LLM calls to Froggy first. |

```
Claude Code ←—MCP—→ froggy-mcp ←—socket—→ Froggy daemon (screen, OCR, local LLM, transcripts)
Claude Code ←—MCP—→ froggy-sre ←—socket (primary) / API (fallback)—→ incident analysis report
```

## Other projects

- **[sre-ai-copilot](https://github.com/froggychips/sre-ai-copilot)** — Python + Celery cloud variant of the SRE agent; AlertManager webhook, Kubernetes backend.
- **[mcp-skills-vault](https://github.com/froggychips/mcp-skills-vault)** — registry + supply-chain integrity gate for MCP servers. 110+ vetted entries with sha512/sha256/Docker-digest pins, 4 advisory feeds, offline-first. Make MCP boring.
- **[tweai](https://github.com/froggychips/tweai)** — AI reply assistant for X (Twitter). Open-source Chrome extension that drafts replies in your voice — 8 personas, smart thread context, tweet translator. OpenAI, Grok, Gemini. BYOK, no subscription, nothing routed through a middleman.


In Frog We Trust 🐸
