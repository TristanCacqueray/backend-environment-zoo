# Backend Runtime Environment Zoo

The goal of this project is to evaluate different runtime environments for a backend system.

## Context and Problem Statement

The goal of the system is to collect the build logs of a CI service in order to enable full text search on the log files.

### Tasks

Here are the different tasks:

- Retrieve the build result from a HTTP JSON api featuring skip&limit pagination.
- For each build retrieve the log files.
- For each log files, process the log lines.

The choice of database is not evaluated, and the system will push the build data into elasticsearch using the bulk api.

### Challenges

Here are the challenges to solve:

- Error recovering: in case of failure, the system should be able to safely restart without losing or duplicating build.
- Throughput monitoring: the system should monitor the performance to indicate the available capacity.
- Parallel streaming API: each tasks should be represented as an uniform stream of events.

### Evaluation

Here are the evaluation criterias:

- Observability. For example, how to check the system health?
- Expression: code writability. For example, how to re-use the stream in a different context?
- Reliability: system stability. For example, how can the system misbehave?
- Environment: language ecosystem. For example, how can the code be tested? How to update a dependency?
- Distribution. For example, how to update a running instance?

## Considered Options

- Haskell (GHC): https://haskell.org
- Rust: https://rust-lang.org
- Elixir (BEAM): https://elixir-lang.org
- &lt;insert your options&gt;

## Decision Outcome
