# froggychips

Bangkok · working at the edges of Apple Silicon, local LLMs, and SRE automation.

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
- **[mcp-skills-vault](https://github.com/froggychips/mcp-skills-vault)** — curated MCP skill definitions for Claude Code.
- *̶*̶[̶T̶w̶e̶A̶I̶]̶(̶h̶t̶t̶p̶s̶:̶/̶/̶g̶i̶t̶h̶u̶b̶.̶c̶o̶m̶/̶f̶r̶o̶g̶g̶y̶c̶h̶i̶p̶s̶/̶T̶w̶e̶A̶I̶)̶*̶*̶ ̶—̶ ̶C̶h̶r̶o̶m̶e̶ ̶e̶x̶t̶e̶n̶s̶i̶o̶n̶ ̶f̶o̶r̶ ̶X̶ ̶/̶ ̶T̶w̶i̶t̶t̶e̶r̶ ̶A̶I̶ ̶a̶s̶s̶i̶s̶t̶a̶n̶c̶e̶.̶ ̶B̶Y̶O̶K̶,̶ ̶n̶o̶ ̶b̶a̶c̶k̶e̶n̶d̶. 

Telegram: [@froggychips](https://t.me/froggychips)  
In Frog We Trust 🐸
