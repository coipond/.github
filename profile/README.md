<!-- Optional: lead with a logo, like karafka does.
     ![CoiPond](https://coipond.ai/misc/logo/coipond-logotype.png) -->

# CoiPond

Self-hosted infrastructure for orchestrating autonomous AI coding sessions. Trigger coding-agent runs from events, isolate each one in its own container, and chain them into multi-step workflows - on your own hardware, with no SaaS control plane.

Website: [coipond.ai](https://coipond.ai)

## The Projects

This organization houses two complementary open-source projects. Coi is the runtime that isolates a single agent session; CoiPond is the orchestrator that runs fleets of them.

- [Coi](https://github.com/coipond/coi) (code-on-incus) is a command-line tool that runs an AI coding agent inside an isolated, disposable [Incus](https://linuxcontainers.org/incus/) container: network isolation, resource limits, security hardening, SSH agent forwarding, and tool config, all from one profile. Standalone and agent-agnostic. Reach for it when you want one sandboxed agent run from the command line.
- [CoiPond](https://github.com/coipond/coipond) is a Rails orchestrator built on Coi. It triggers agent sessions from events (cron, webhooks, other sessions, or a click), runs each in its own `coi` container, and chains them into workflows with success/failure routing, approvals, and human-in-the-loop handling, scaling from one box to a fleet. Reach for it when you want scheduled, chained, multi-machine agent automation with a UI and live terminals.

## How They Fit Together

Coi is the sandbox each session runs in. CoiPond drives the `coi` CLI to launch, monitor, and tear down those sandboxes, one per workflow step. You can use Coi entirely on its own; CoiPond is what you add when a single agent run becomes a pipeline, a schedule, or a fleet.

## Getting Started

- CoiPond: start with the [wiki](https://github.com/coipond/coipond/wiki), in particular [Why CoiPond](https://github.com/coipond/coipond/wiki/Why-CoiPond), [Getting Started](https://github.com/coipond/coipond/wiki/Getting-Started), and [How It Works](https://github.com/coipond/coipond/wiki/How-It-Works).
- Coi: see the [Coi repository](https://github.com/coipond/coi) for installation and the profile reference.

## Agents

Both projects are agent-agnostic. Coi runs Claude Code, opencode, Codex, pi, omp, and more inside isolated containers, with a Tool interface for adding new ones. CoiPond ships adapters for Claude Code and Aider today.

## License

Released under the MIT License, (c) Maciej Mensfeld.
