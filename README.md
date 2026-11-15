<p align="center">
  <img src=".github/assets/logo-ornate-light.svg" alt="OpenStatic" width="180">
</p>
<p align="center"><strong>OpenStatic</strong></p>
<p align="center">An open-source, autonomous AI development environment.</p>
<p align="center">
  <a href="https://github.com/MilkdromedaStudios/staticcode"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-MilkdromedaStudios%2Fstaticcode-181717?style=flat-square&logo=github" /></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/license-MIT-blue?style=flat-square" /></a>
</p>

OpenStatic is an independently maintained fork of [OpenCode](https://github.com/anomalyco/opencode). It builds on OpenCode's agent runtime, tools, skills, and model integrations, with an OpenStatic-focused workflow and autonomous development mode.

> **Project status:** OpenStatic is under active development. Some inherited interfaces, package names, and documentation may still use the upstream OpenCode name while the rebrand is completed.

## Highlights

- **Auto Mode:** a primary autonomous agent that can inspect and edit a project, run normal development commands, test changes, and use available tools without routine approval prompts.
- **Web research:** use the built-in `websearch` tool when a search provider is configured.
- **Skills:** load task-specific instructions from project or user skill directories.
- **Connected tools:** use configured MCP servers and integrations where available.
- **Model choice:** use the supported model providers and local models available in the underlying runtime.

Auto Mode is designed to move through normal development work independently. It still avoids exposing secrets, destructive system-wide operations, purchases, and unrequested publishing or deployment.

## Quick start

This repository is a Bun workspace monorepo. Use Bun to build and run the source checkout:

```bash
git clone https://github.com/MilkdromedaStudios/staticcode.git
cd staticcode
bun install
bun run dev
```

For the current development branch:

```bash
git clone --branch openstatic/rebrand-auto-mode https://github.com/MilkdromedaStudios/staticcode.git
cd staticcode
bun install
bun run dev
```

### npm installation

A direct `npm install github:MilkdromedaStudios/staticcode` installer is **not available yet**. The source repository uses Bun workspace dependencies and Bun's `catalog:` dependency protocol, which npm cannot install as a normal Git dependency. Use the Bun source install above for now. A standalone npm-distributed CLI needs a separately built and published package; the repository URL alone cannot make that package installable.

## Use Auto Mode

Select **OpenStatic Auto** from the agent selector, or start a session with:

```bash
bun run dev -- --agent openstatic-auto
```

Auto Mode is intended to complete routine development work end-to-end. It may still stop when an action requires explicit authorization under the safety boundaries above.

## Web search and tools

OpenStatic includes the upstream `websearch` tool and supports configured MCP integrations. Search availability depends on having a supported web-search provider configured. To connect external tools, configure an MCP server using the built-in MCP configuration and authentication workflow.

The `openstatic-web` skill documents how the agent should research websites, verify sources, use connected tools, and report actions. Skills can be placed in the repository's `.opencode/skills/<skill-name>/SKILL.md` directory.

## Documentation

- [OpenCode documentation](https://opencode.ai/docs) — upstream runtime documentation; some branding and paths are being migrated.
- [OpenCode upstream repository](https://github.com/anomalyco/opencode) — source project and attribution.

## Upstream attribution

OpenStatic is a community fork of OpenCode by Anomaly. It is not an official OpenCode product and is not affiliated with or endorsed by the OpenCode team. The upstream project and its contributors retain their respective copyrights and licenses. See [LICENSE](LICENSE).
