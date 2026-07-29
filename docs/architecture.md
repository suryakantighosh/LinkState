# Architecture Overview

LinkState is organized as a layered platform that separates user interaction, simulation state, and automation workflows.

## Core Layers

1. Presentation Layer
   - The browser-based topology editor and console provide the user experience.
   - The UI is intentionally lightweight and runs with standard web technologies.

2. Application Layer
   - FastAPI exposes REST endpoints for topology operations, CLI execution, packet capture, tutoring, and automation.
   - Each request is routed against an isolated workspace object.

3. Simulation Engine
   - The core engine models devices, interfaces, links, routing, switching, security, wireless, WAN, and packet behavior.
   - It is deterministic and designed to be explainable rather than fully vendor-accurate.

4. Automation and Learning Layer
   - A configuration rendering and validation layer supports labs-as-code, drift detection, and intent-driven automation.
   - The tutor subsystem combines deterministic analysis with optional on-device inference.

## Runtime Model

- A workspace contains a topology, device sessions, positions, and baseline snapshots.
- The service currently keeps state in memory, which keeps the experience simple and predictable.
- The design is suitable for local use, demos, and education, with a clear path toward shared state and persistence.

## Design Principles

- Deterministic behavior for reliable teaching and evaluation.
- Clear separation between simulation, control plane, and presentation.
- Extensibility for new protocols, labs, and automation capabilities.
