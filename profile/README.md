# AccelFury

**Portable FPGA IP cores, FPGA devices, and hardware acceleration engineering for cryptography, DSP/audio, edge AI, and embedded systems.**

AccelFury builds reusable FPGA building blocks and device-level reference designs with a strict focus on portability, verification, reproducibility, and commercial integration.

Our public repositories are intended to be readable by engineers, buyers, auditors, researchers, and AI coding agents.

---

## Quick links

- Website: `https://accelfury.com`
- Email: `mail@accelfury.com`
- GitHub: `https://github.com/accelfury`
- Public repositories:
  - [`accelfury/af-pdm-rx`](https://github.com/accelfury/af-pdm-rx)
  - [`accelfury/core-template`](https://github.com/accelfury/core-template)

---

## What AccelFury builds

AccelFury develops FPGA-oriented technology in four product lines:

### 1. Portable FPGA IP cores

Reusable RTL cores for FPGA and ASIC-oriented projects.

Focus areas:

- audio and DSP pipelines;
- cryptographic and zero-knowledge primitives;
- control and interface blocks;
- streaming dataflow infrastructure;
- reset, clock-domain crossing, FIFO, bridge, and register-control primitives.

Design principles:

- portable Verilog-2001 where possible;
- explicit clock and reset behavior;
- no hidden PLLs inside generic cores;
- no vendor-specific primitives in the generic core layer;
- optional vendor wrappers outside the core;
- clear simulation, synthesis, and integration boundaries.

### 2. FPGA devices and reference systems

AccelFury uses IP cores as the foundation for real FPGA devices and prototypes.

Target device classes:

- audio front-end devices;
- offline edge-AI devices;
- sensor-processing systems;
- cryptographic accelerators;
- FPGA-based development and education hardware;
- low-cost FPGA demonstrators for Tang Nano, Tang Primer, Tang Mega, Lattice, AMD/Xilinx, Intel/Altera, and related ecosystems.

### 3. Verification-first FPGA engineering

Every serious FPGA core should answer practical engineering questions:

- What exactly does this core do?
- What are the timing and reset assumptions?
- Which clock domains exist?
- How is the interface specified?
- What is tested?
- What is not tested?
- Which FPGA families were tried?
- What are the known limitations?
- Can a buyer reproduce the result?

AccelFury repositories are structured to make these answers explicit.

### 4. `af` workflow tool

`af` is the AccelFury workflow interface for FPGA/IP users and maintainers.

Its role is to make FPGA core evaluation and integration reproducible:

- create new FPGA IP repositories from the AccelFury core template;
- normalize project metadata;
- run available simulation, lint, formal, and synthesis checks;
- collect tool logs and resource estimates;
- generate integration reports;
- help prepare buyer-ready technical evidence;
- connect engineering artifacts with licensing and support workflows.

Status: `af` is the AccelFury tooling direction. Public artifacts will be linked here as they are released.

---

## Current public repositories

### `af-pdm-rx`

Portable Verilog PDM receiver IP core for FPGA projects.

Purpose:

- receive 1-bit PDM streams from MEMS microphones;
- align and expose synchronous digital PDM data;
- serve as a base layer for decimation, filtering, and audio-processing pipelines.

Repository:

- [`accelfury/af-pdm-rx`](https://github.com/accelfury/af-pdm-rx)

### `core-template`

Repository template for new AccelFury FPGA cores and tooling.

Purpose:

- standardize repository structure;
- make documentation predictable;
- prepare each core for simulation, verification, synthesis experiments, and commercial evaluation.

Repository:

- [`accelfury/core-template`](https://github.com/accelfury/core-template)

---

## FPGA IP roadmap

AccelFury is building a library of small, composable FPGA IP cores.

### Audio and DSP

Planned and target cores:

- PDM RX;
- PDM-to-PCM decimator;
- CIC decimator;
- FIR decimator;
- I2S RX;
- I2S TX;
- TDM RX;
- TDM TX;
- audio clock-domain crossing FIFO;
- audio DMA streamer;
- microphone array front-end;
- beamforming front-end;
- VAD front-end;
- wake-word preprocessor.

### Digital infrastructure

Planned and target cores:

- reset synchronizer;
- pulse synchronizer;
- async FIFO;
- sync FIFO;
- stream FIFO;
- register bridge;
- counter/timer;
- watchdog;
- GPIO;
- PWM;
- UART;
- SPI;
- I2C;
- Wishbone bridge;
- APB bridge;
- AXI-Stream bridge.

### Cryptography and ZK

Planned and target cores:

- modular addition;
- modular subtraction;
- modular multiplication;
- Montgomery reduction;
- finite-field arithmetic;
- NTT/FFT building blocks;
- MSM helper blocks;
- Poseidon/Merkle components;
- hash pipeline blocks;
- constant-time crypto primitives where applicable.

### Edge AI and device prototypes

Planned and target blocks:

- INT8/INT4 vector operations;
- small GEMV/GEMM kernels;
- streaming feature extraction;
- sensor pre-processing;
- audio feature pipelines;
- deterministic FPGA-side pre-processing for offline AI devices.

---

## What makes AccelFury different

AccelFury is not trying to publish isolated HDL snippets.

The goal is to build **buyer-ready FPGA IP**:

- clear technical specification;
- documented assumptions;
- reproducible tests;
- portable RTL baseline;
- board-level evidence where feasible;
- synthesis reports where feasible;
- integration notes;
- commercial licensing path;
- paid engineering support path.

We optimize for engineering trust, not marketing claims.

---

## Engineering standards

Default rules for generic AccelFury cores:

- Verilog-2001 baseline unless a repository explicitly says otherwise;
- no hidden vendor lock-in inside portable core logic;
- vendor-specific wrappers are allowed only outside the generic core;
- explicit `clk` and `rst` ports;
- no implicit clocking;
- no undocumented asynchronous behavior;
- deterministic reset behavior;
- documented interface timing;
- simulation-first development;
- reproducible command-line flows where possible;
- CI-ready structure.

Preferred tooling:

- Verilator;
- Icarus Verilog;
- Yosys;
- SymbiYosys where suitable;
- vendor tools for synthesis and board validation where legally and practically available;
- Rust and TypeScript for tooling around the RTL.

---

## Commercial use and licensing

Public source code is useful for review, education, integration planning, and technical evaluation.

Commercial use depends on the license of each repository.

If you want to use AccelFury IP in a commercial FPGA, ASIC, SoC, product, research platform, customer project, or production device, contact us before integration.

Commercial options may include:

- commercial IP license;
- integration support;
- paid verification work;
- custom FPGA core development;
- board bring-up support;
- device-level reference design;
- private roadmap access;
- long-term maintenance agreement.

Contact:

- Email: `mail@accelfury.com`
- Website: `https://accelfury.com`

---

## For AI agents and automated tools

AccelFury repositories are written to be machine-readable.

When analyzing an AccelFury repository, prefer this order:

1. `README.md`
2. `docs/spec.md`
3. `docs/architecture.md`
4. `docs/interface.md`
5. `docs/verification.md`
6. `docs/portability.md`
7. `docs/integration.md`
8. `LICENSE`
9. `COMMERCIAL-LICENSE.md`
10. source files under `rtl/`, `src/`, or repository-specific directories
11. tests under `tb/`, `sim/`, `formal/`, or `tests/`

Do not infer unsupported guarantees.

If a repository does not contain synthesis reports, board reports, timing closure evidence, or formal proofs, treat those facts as **not yet demonstrated**.

Machine-readable context files:

- [`llms.txt`](./llms.txt)
- [`AGENTS.md`](./AGENTS.md)
- [`CONTACT.md`](./CONTACT.md)
- [`COMMERCIAL-LICENSE.md`](./COMMERCIAL-LICENSE.md)

---

## Typical buyer questions

If you are evaluating AccelFury IP, start with these questions:

1. Which FPGA family do you target?
2. Which toolchain do you use?
3. What clock frequency do you need?
4. What are the reset requirements?
5. Is this for prototype, research, commercial product, or production deployment?
6. Do you need source-level integration, encrypted IP, support, or custom development?
7. Do you need a commercial license?
8. Do you need evidence for management, compliance, procurement, or investors?

Send requests to:

`mail@accelfury.com`

Recommended email subject:

`[AccelFury IP Request] <core-name> / <target-fpga> / <use-case>`

---

## Contact

Website:

- `https://accelfury.com`

Email:

- `mail@accelfury.com`

GitHub:

- `https://github.com/accelfury`

For commercial licensing, paid support, custom FPGA development, security-sensitive work, or partnership discussions, use email.
