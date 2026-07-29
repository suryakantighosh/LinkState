# Architecture Diagram Specifications

These specifications are written so another AI image generator can create publication-quality engineering visuals for the repository.

## 1. Overall System Architecture

### Purpose
Show the end-to-end structure of the platform as a teaching and simulation system.

### Why this diagram matters
It explains the product at a glance: browser front end, API, simulation engine, automation, tutor, and optional cloud services.

### Recommended size
3000 × 1800 px

### Aspect ratio
5:3

### Visual style
Clean enterprise architecture diagram with soft gradients, rounded rectangles, subtle shadows, and a professional software-product aesthetic.

### Layout
Left to right with four major bands:
- User interaction at the left
- Application and control plane in the center
- Simulation and automation engine on the right
- Optional AI and cloud services on the far right

### Colour palette
- Background: #F8FAFC
- Primary blue: #2563EB
- Secondary teal: #0F766E
- Accent purple: #7C3AED
- Warm orange: #EA580C
- Neutral gray: #475569
- Success green: #16A34A

### Typography
Use Inter or Source Sans for all labels. Titles should be bold and large; component labels should be medium weight.

### Legend
Include a simple legend for:
- User interaction
- Internal services
- Data/state
- Optional cloud services

### Grid layout
Use a 12-column design grid with evenly spaced horizontal bands.

### Background
Soft off-white with a faint grid.

### Boxes
Every box should have a 16 px corner radius and a thin border.

### Components
- Browser client
- Topology UI
- CLI console
- Packet capture viewer
- API gateway layer
- Workspace state
- Simulation engine
- Automation renderer/validator
- Tutor analyzer
- Optional on-device model runtime
- Optional cloud AI fallback

### Connections
Use blue arrows for request/response flow and green arrows for success/validation flow. Dotted arrows indicate optional services.

### Footer
Include the product name “LinkState” and the subtitle “Browser-native networking simulation and automation platform”.

---

## 2. Request Lifecycle Diagram

### Purpose
Show how a user action flows through the system from browser input to engine state and back.

### Why this diagram matters
It helps readers understand how a CLI command, ping, or automation action becomes a deterministic simulation result.

### Recommended size
2400 × 1600 px

### Aspect ratio
3:2

### Layout
Vertical flow: browser input → API endpoint → workspace → engine → response → UI update.

### Boxes
Include:
- UI action button
- FastAPI route
- Workspace lock/state manager
- CLI session or simulation engine
- Result payload
- Front-end update

### Connections
Show arrows labeled with examples such as “POST /api/cli”, “execute”, “state update”, and “render result”.

---

## 3. Deployment Architecture

### Purpose
Show how the service is deployed locally, in containers, and in a cloud environment.

### Why this diagram matters
It clarifies runtime assumptions, especially the in-memory state model and the single-worker deployment guidance.

### Recommended size
2800 × 1800 px

### Aspect ratio
7:4.5

### Layout
Three horizontal zones:
- Local developer workflow
- Container runtime
- Cloud hosting / optional edge services

### Boxes
- Developer laptop
- Docker container
- Uvicorn/FastAPI process
- Browser client
- Optional hosted AI/CDN services

### Annotations
Add callouts such as:
- “Single-process workspace state”
- “No external database required for the default deployment”
- “Future scaling path: shared state and persistence”

---

## 4. AI Tutor Pipeline

### Purpose
Show how the tutoring experience combines deterministic reasoning with optional model inference.

### Why this diagram matters
It helps explain the product’s differentiator: a reliable, educational AI experience that does not depend on an external API for core correctness.

### Recommended size
2800 × 1800 px

### Aspect ratio
7:4.5

### Layout
Top-down pipeline from lab data to browser inference.

### Boxes
- Lab and topology data
- Rule-based analyzer
- Optional cloud model fallback
- Browser inference runtime
- User explanation output

### Connections
Use arrows labeled “grounded findings”, “optional model response”, and “final explanation”.

---

## Combined Prompt for a Publication-Quality Engineering Diagram

Create a polished enterprise-style architecture illustration for LinkState, a browser-native networking simulation and automation platform. Use a modern software architecture aesthetic: soft gray background, subtle grid, rounded rectangles, thin borders, and gentle shadows. The composition should be a 5:3 landscape layout with four horizontal layers: left side for user interaction, center for the application API and workspace state, right side for the simulation engine and automation services, and far right for optional AI and cloud services. Include clearly labeled boxes for Browser Client, Topology Editor, CLI Console, Packet Capture Viewer, FastAPI API, Workspace State Manager, Simulation Engine, Automation Engine, Tutor Analyzer, Optional On-Device Model Runtime, and Optional Cloud AI/CDN Services. Use blue arrows for request/response flow, green arrows for validation and success flow, and dotted arrows for optional services. Add small callouts for key product themes such as deterministic behavior, labs-as-code, and explainable networking. Use a professional blue-teal-purple-orange palette, bold headings, and clean sans-serif typography. The result should feel like a Microsoft, Google, or HashiCorp architecture diagram suitable for a GitHub README and technical documentation.
