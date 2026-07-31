<div align="center">

<h1>UseArazzo</h1>

### The Operating System for API workflows

Author, validate, execute, and ship multi-step **Arazzo** workflows — then compile them into deterministic tools your AI agents can trust.

<br/>

[![Website](https://img.shields.io/badge/Website-usearazzo.com-5E8A1F?style=for-the-badge&logoColor=white)](https://usearazzo.com)
[![Toolkit](https://img.shields.io/badge/arazzo--toolkit-17210D?style=for-the-badge&logo=github&logoColor=white)](https://github.com/usearazzo/arazzo-toolkit)
[![Discussions](https://img.shields.io/badge/Discussions-17210D?style=for-the-badge&logo=github&logoColor=white)](https://github.com/orgs/usearazzo/discussions)

</div>

<br/>

<div align="center">
  <a href="https://spec.openapis.org/arazzo/latest.html"><img height="36" alt="Arazzo" src="https://raw.githubusercontent.com/usearazzo/.github/main/profile/assets/arazzo-logo.png" /></a>&nbsp;&nbsp;
  <a href="https://www.openapis.org/"><img height="36" alt="OpenAPI" src="https://raw.githubusercontent.com/usearazzo/.github/main/profile/assets/openapi-logo.png" /></a>
</div>

## The stack

UseArazzo builds the full stack for API workflows — from a low-level Arazzo parser all the way up to embeddable UI components. Free and open source under Apache 2.0, published under the `@usearazzo/*` namespace.

### Available now

| Layer | Description |
| :---- | :---------- |
| [**Parser**](https://github.com/usearazzo/arazzo-toolkit) | `@usearazzo/parser` — reads Arazzo documents into a lossless semantic model. Error-recovery capable, reference-aware, and honest about what it can't resolve. |
| [**Resolver**](https://github.com/usearazzo/arazzo-toolkit) | `@usearazzo/resolver` — resolves references and external source descriptions across files and URLs into one fully dereferenced document. |
| [**Validator**](https://github.com/usearazzo/arazzo-toolkit) | `@usearazzo/validator` — checks documents against the Arazzo specification: structural rules for document shape, semantic rules for expressions and cross-step references. |
| [**Bundler**](https://github.com/usearazzo/arazzo-toolkit) | `@usearazzo/bundler` — inlines JSON Schema references into a single document. Source descriptions stay external by design — Arazzo points at them by URL rather than embedding them. |
| [**Runner**](https://github.com/usearazzo/arazzo-toolkit) | `@usearazzo/runner` — executes workflows step by step: criteria evaluation, output mapping, failure actions, and retries, with a full trace of every decision made. |
| [**UI**](https://github.com/usearazzo/arazzo-toolkit) | `@usearazzo/ui` — embeddable components for rendering and inspecting Arazzo workflows inside your own application. |

### On the roadmap

| Layer | Description |
| :---- | :---------- |
| **Language Service** | An LSP-compatible library bringing Arazzo intelligence to any editor or tool — validation, completion, hover, go-to-definition, and find references. |
| **Editor** | A browser-based editor for authoring and validating Arazzo workflows with real-time feedback. |
| **VS Code Extension** | Arazzo authoring inside VS Code — real-time validation, semantic linting, autocompletion, and live preview. |
| **AI Design Skills** | Lets AI agents author and validate workflows natively from natural language, emitting a standard `.arazzo.yaml` that's parsed and checked before you ever see it. |
| **MCP Compiler** | Compiles a validated workflow into a production-ready [Model Context Protocol](https://modelcontextprotocol.io/) server — one typed tool per workflow, for Claude, Cursor, Windsurf, and anything else that speaks MCP. |
| **Arazzo Transformers** | Explicit, versioned transformation steps for reshaping data between steps — declared in the document and reviewable in a pull request, instead of smuggled in as inline scripts. |

## Why UseArazzo

A single API call is a solved problem — everything above it isn't. OpenAPI describes endpoints, but not the order you call them in, what you carry between them, or when you're done. Agent frameworks improvise that order at runtime, and improvisation is exactly what you don't want in production. UseArazzo fills the gap with [Arazzo](https://spec.openapis.org/arazzo/latest.html), the OpenAPI Initiative's specification for multi-step API workflows:

- **Deterministic execution** — a workflow that ran yesterday runs the same today. Agents get autonomy at the decision boundary, not inside the steps.
- **The standard is the product** — Arazzo implemented as specified, with contributions upstream rather than a private dialect only our tools understand.
- **Portable artifacts** — plain Arazzo documents in your repository, driven from the CLI, your CI pipeline, or an agent. If you stop using us, your workflows keep working.

### Free and open source

<p align="left">
  <img alt="Open source" src="https://img.shields.io/badge/Open_source-5E8A1F?style=for-the-badge" />
  <img alt="Apache 2.0" src="https://img.shields.io/badge/Apache_2.0-5E8A1F?style=for-the-badge" />
  <img alt="Runs locally" src="https://img.shields.io/badge/Runs_locally-17210D?style=for-the-badge" />
  <img alt="No lock-in" src="https://img.shields.io/badge/No_lock--in-17210D?style=for-the-badge" />
</p>

## Who we are

UseArazzo was founded by [Vladimir Gorej](https://vladimirgorej.com/) and [Francesco Tumanischvili](https://github.com/frantuma), two industry veterans with over 15 years of combined experience building and maintaining core tools in the Swagger/OpenAPI ecosystem.

## Join the discussion

Have questions or want to share your thoughts? Join our [Discussions](https://github.com/orgs/usearazzo/discussions) to engage with the community.

## Get help from the maintainers

UseArazzo is free to use. We can help developers and teams adopt Arazzo, standardize workflow specifications, and ship agent integrations that hold up in production.

- **Website**: https://usearazzo.com
- **Email**: info@usearazzo.com

## Built on SpecLynx

<a href="https://github.com/speclynx"><img align="left" height="80" alt="SpecLynx" src="https://raw.githubusercontent.com/usearazzo/.github/main/profile/assets/speclynx-logo.png" /></a>

UseArazzo is built end to end on [SpecLynx](https://github.com/speclynx) — the semantic parsing core, reference resolution, and standards discipline behind years of Swagger/OpenAPI tooling. Every layer of UseArazzo sits on that foundation, which is why the toolchain handles malformed documents, external references, and specification edge cases from day one rather than learning them the hard way.

---

<div align="center">
  <sub>Describe the workflow once. Run it anywhere — by hand, in CI, or through an agent.</sub>
</div>
