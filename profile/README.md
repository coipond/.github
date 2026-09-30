<!-- Optional: lead with a logo, like karafka does.
     ![CoiPond](https://coipond.ai/misc/logo/coipond-logotype.png) -->

# CoiPond

Self-hosted infrastructure for **orchestrating autonomous AI coding sessions**. Trigger coding-agent runs from events, isolate each one in its own container, and chain them into multi-step workflows - on your own hardware, with no SaaS control plane.

Website: [coipond.ai](https://coipond.ai)

## The Projects

This organization houses two complementary open-source projects. **coi** is the runtime that isolates a single agent session; **CoiPond** is the orchestrator that runs fleets of them.

<table>
<thead>
<tr><th>Project</th><th>What It Is</th><th>Reach For It When</th></tr>
</thead>
<tbody>
<tr>
<td><strong><a href="https://github.com/coipond/coi">coi</a></strong> (code-on-incus)</td>
<td>A CLI that runs an AI coding agent inside an isolated, disposable <a href="https://linuxcontainers.org/incus/">Incus</a> container: network isolation, resource limits, security hardening, SSH agent forwarding, and tool config, all from one profile. Standalone and agent-agnostic.</td>
<td>You want one sandboxed agent run, right now, from the command line.</td>
</tr>
<tr>
<td><strong><a href="https://github.com/coipond/coipond">CoiPond</a></strong></td>
<td>A Rails orchestrator built on coi. It triggers agent sessions from events (cron, webhooks, other sessions, or a click), runs each in its own coi container, and chains them into workflows with success/failure routing, approvals, and human-in-the-loop handling - scaling from one box to a fleet.</td>
<td>You want scheduled, chained, multi-machine agent automation with a UI and live terminals.</td>
</tr>
</tbody>
</table>

## How They Fit Together

coi is the sandbox each session runs in. CoiPond drives coi through its CLI to launch, monitor, and tear down those sandboxes, one per workflow step. You can use coi entirely on its own; CoiPond is what you add when a single agent run becomes a pipeline, a schedule, or a fleet.

## Getting Started

- **CoiPond** - start with the [wiki](https://github.com/coipond/coipond/wiki): [Why CoiPond](https://github.com/coipond/coipond/wiki/Why-CoiPond), [Getting Started](https://github.com/coipond/coipond/wiki/Getting-Started), and [How It Works](https://github.com/coipond/coipond/wiki/How-It-Works).
- **coi** - see the [coi repository](https://github.com/coipond/coi) for installation and the profile reference.

## Agents

Both projects are agent-agnostic. [Claude Code](https://github.com/anthropics/claude-code) and [Aider](https://github.com/Aider-AI/aider) are supported today, behind a small adapter layer.

## License

Released under the MIT License, (c) Maciej Mensfeld.
