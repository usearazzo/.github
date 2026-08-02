<div align="center">

<h1>UseArazzo</h1>

### Run Arazzo workflows. See what happened at each step.

A JavaScript/TypeScript toolkit for **Arazzo**, the OpenAPI Initiative's specification for multi-step API workflows.

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

## What it does

Plenty of tools will tell you whether an [Arazzo](https://spec.openapis.org/arazzo/latest.html) document is well formed. Far fewer will run it. UseArazzo does both, and tells you what happened:

1. **Validate** the document against the Arazzo specification.
2. **Run** the workflow against live APIs.
3. **Read the trace** of each step in run order: whether it succeeded, which action was selected, and how many attempts it took, alongside the workflow's outputs and final status. What happened at each step, not just a pass or fail at the end.

Do it from the command line with `@usearazzo/cli`, on your machine or in CI.

![Running an Arazzo workflow from the command line](https://raw.githubusercontent.com/usearazzo/.github/main/profile/assets/workflow-run-demo.gif)

The toolkit is pre-1.0 and APIs may change before the stable release.

### Validate and run workflows

| Package                                                                                | Description |
| :------------------------------------------------------------------------------------- | :---------- |
| [**CLI**](https://github.com/usearazzo/arazzo-toolkit/tree/main/packages/cli)          | `@usearazzo/cli` — one command-line interface across the toolchain: validate and run workflows on your machine and in CI. Start here. |
| [**Validator**](https://github.com/usearazzo/arazzo-toolkit/tree/main/packages/parser) | `@usearazzo/validator` — the same validation the CLI runs, as a library: every violation against the Arazzo specification, with the location that caused it. |
| [**Runner**](https://github.com/usearazzo/arazzo-toolkit/tree/main/packages/runner)    | `@usearazzo/runner` — executes workflows step by step: criteria evaluation, output mapping, failure actions, and retries, returning a per-step record of the run. Reach for it when you want execution embedded in your own program. |

Lower-level packages are published for anyone building Arazzo tooling of their own:

- [`@usearazzo/parser`](https://github.com/usearazzo/arazzo-toolkit/tree/main/packages/parser)
- [`@usearazzo/resolver`](https://github.com/usearazzo/arazzo-toolkit/tree/main/packages/resolver)

### Compatibility

| Document | Versions | Validate | Run |
| :------- | :------- | :------- | :-- |
| Workflow Document: [Arazzo](https://spec.openapis.org/arazzo/latest.html) | [1.0.0](https://spec.openapis.org/arazzo/v1.0.0), [1.0.1](https://spec.openapis.org/arazzo/v1.0.1) | yes | yes |
| Workflow Document: [Arazzo](https://spec.openapis.org/arazzo/latest.html) | [1.1.0](https://spec.openapis.org/arazzo/v1.1.0) | no | partial |
| Source Description: [OpenAPI](https://www.openapis.org/) | [2.0](https://spec.openapis.org/oas/v2.0), [3.0.x](https://spec.openapis.org/oas/v3.0.4), [3.1.x](https://spec.openapis.org/oas/v3.1.2) | yes | yes |
| Source Description: [Arazzo](https://spec.openapis.org/arazzo/latest.html) | [1.0.0](https://spec.openapis.org/arazzo/v1.0.0), [1.0.1](https://spec.openapis.org/arazzo/v1.0.1) | yes | no |
| Source Description: [AsyncAPI](https://www.asyncapi.com/) | any | no | no |

## Why UseArazzo

A single API call is a solved problem, and everything above it isn't. OpenAPI describes endpoints, but not the order you call them in, what you carry between them, or when you're done. Agent frameworks improvise that order at runtime, and improvisation is exactly what you don't want in production. UseArazzo fills the gap with [Arazzo](https://spec.openapis.org/arazzo/latest.html), the OpenAPI Initiative's specification for multi-step API workflows:

- **Deterministic execution** — a workflow that ran yesterday runs the same today. Agents get autonomy at the decision boundary, not inside the steps.
- **The standard is the product** — Arazzo implemented as specified, with contributions upstream rather than a private dialect only our tools understand.
- **Portable artifacts** — plain Arazzo documents in your repository, driven from the CLI, your CI pipeline, or an agent. If you stop using the toolkit, your workflows keep working.

### Free and open source

<p align="left">
  <img alt="Open source" src="https://img.shields.io/badge/Open_source-5E8A1F?style=for-the-badge" />
  <img alt="Apache 2.0" src="https://img.shields.io/badge/Apache_2.0-5E8A1F?style=for-the-badge" />
  <img alt="Runs locally" src="https://img.shields.io/badge/Runs_locally-17210D?style=for-the-badge" />
  <img alt="No lock-in" src="https://img.shields.io/badge/No_lock--in-17210D?style=for-the-badge" />
</p>

## On the roadmap

| Layer | Description |
| :---- | :---------- |
| **Language&nbsp;Service** | An LSP-compatible library bringing Arazzo intelligence to any editor or tool — validation, completion, hover, go-to-definition, and find references. |
| **Editor** | A browser-based editor for authoring and validating Arazzo workflows with real-time feedback. |
| **VS&nbsp;Code&nbsp;Extension** | Arazzo authoring inside VS Code — real-time validation, semantic linting, autocompletion, and live preview. |
| **Agent&nbsp;Skills** | A set of task-shaped skills teaching agents to work the toolchain — authoring workflows from an API description, validating and fixing them, and reading a run trace when a step fails. |
| **MCP&nbsp;Server** | A generic [Model Context Protocol](https://modelcontextprotocol.io/) server exposing validation and execution over any Arazzo document, so agents can check and run workflows with no build step. |
| **MCP&nbsp;Compiler** | Compiles a specific workflow into a dedicated MCP server — one typed tool per workflow, with real input schemas, for production agent deployments. |
| **Arazzo&nbsp;Transformers** | Explicit, versioned transformations for reshaping data between steps — declared as ordinary API calls the toolchain can validate, rather than arbitrary code that needs a sandbox to run. |

## Who we are

UseArazzo was founded by [Vladimir Gorej](https://vladimirgorej.com/) and [Francesco Tumanischvili](https://github.com/frantuma), two industry veterans with over 15 years of combined experience building and maintaining core tools in the Swagger/OpenAPI ecosystem.

## Get in touch

Questions, ideas, and bug reports belong in [Discussions](https://github.com/orgs/usearazzo/discussions). For anything else, reach the maintainers directly.

- **Website**: https://usearazzo.com
- **Email**: info@usearazzo.com

## Built on SpecLynx

<a href="https://github.com/speclynx"><img align="left" height="80" alt="SpecLynx" src="https://raw.githubusercontent.com/usearazzo/.github/main/profile/assets/speclynx-logo.png" /></a>

UseArazzo is built end to end on [SpecLynx](https://github.com/speclynx) — the semantic parsing core, reference resolution, and standards discipline behind years of Swagger/OpenAPI tooling. The toolkit sits on that foundation, which is why it handles malformed documents, external references, and specification edge cases from day one rather than learning them the hard way.

---

<div align="center">
  <sub>Describe the workflow once. Run it anywhere — by hand, in CI, or through an agent.</sub>
</div>
