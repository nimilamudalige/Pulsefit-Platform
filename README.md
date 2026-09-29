# PulseFit — Platform (Parent / Super-Repository)

## Project Description

This is the **parent repository** for the PulseFit platform tier. It is a
super-repository that ties together three independent child repositories as
Git submodules:

- [`service-registry`](https://github.com/nimilamudalige/service-registry) — Eureka Service Registry
- [`config-server`](https://github.com/nimilamudalige/config-server) — Spring Cloud Config Server
- [`api-gateway`](https://github.com/nimilamudalige/api-gateway) — Spring Cloud Gateway

Together these three components form the platform layer described in the
ITS 2130 guidelines ("Microservice Platform Components"): centralized
configuration, service discovery, and a single API entry point. On GCP they
are deployed across **two zones** for high availability — see
`deployment/GCP_CLI_DEPLOYMENT_GUIDE.md` in the workspace root for the exact
`gcloud` commands.

## Technology Stack

- Java 25, Spring Boot 4.0.8, Spring Cloud 2025.1.3
- Git submodules (polyrepo architecture)
- PM2 for process management on each VM

## Setup / Getting Started

```bash
git clone --recurse-submodules https://github.com/nimilamudalige/pulsefit-platform.git
cd pulsefit-platform
# Build and run each submodule in this order: config-server, service-registry, api-gateway
```

If you already cloned without `--recurse-submodules`:

```bash
git submodule update --init --recursive
```

## Student Information

- **Student Name:** Pasan Nimila
- **Student Number:** 2301692034
- **Slack Handle:** pasan_nimila
- **GCP Project ID:** pulsefit-capstone
