---
title: "Application Compatibility WG, May 22, 2024"
tags: unikraft, app-compat, bincompat, syscall
datetime: 2024-05-22T14:00:00+02:00
location: Online, Discord (https://bit.ly/UnikraftDiscord), the `#monkey-business` voice channel
teams:
- app-compat, syscall, bincompat
participants:
- RăzvanD
- CosminV
- Sebastian
- Martin
---

## :dart: Agenda

- Status update
- Next steps

## :closed_book: Discussions

### Java Support

CV: I debugged Java Springboot, but I wasn't able to find meaningful information.
So I moved on to only test / evaluate HTTP Server.

CV: What should I test?

### Blockchain

Port MultiverseX blockchain Node to Unikraft.

I'm replicating the native Unikraft machine on Unikraft.

The problem I'm facing is some missing features in Unikraft, such as Netlink node.

I'll do measurements on blockchain node running on Unikraft.

### Rust

From Rust-side, everything should work if you have a compiled Rust library.
In the example, we always use the `nightly`, in order to build our standard library.

There have to be more users of the target.

## :wrench: TODOs and Decisions

CV: Measure Java HTTP server running on Unikraft:

* number of requests per second: Docker, Linux VM, Unikraft VM
* boot times(s) for Unikraft VM: VMM start, Unikraft boot, application boot (to network ready)
* scalability: performance degrade in case of multiple client connections: Docker, Linux VM, Unikraft VM

RD: Provide a binary or a preview branch.

RD: Approve and merge Rust Axum PR: https://github.com/unikraft/catalog/pull/100
