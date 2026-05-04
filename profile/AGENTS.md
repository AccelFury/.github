# AccelFury agent instructions

This file gives AI coding agents and automated analysis tools stable context for AccelFury repositories.

## Repository-specific note

If you are operating inside `accelfury/.github`, treat `profile/README.md` as the main public-facing organization profile and keep `llms.txt`, `CONTACT.md`, and `COMMERCIAL-LICENSE.md` aligned with it.

## Project identity

AccelFury builds portable FPGA IP cores, FPGA devices, and hardware acceleration engineering assets.

Primary domains:

- FPGA IP cores
- Verilog RTL
- audio and DSP pipelines
- cryptography and zero-knowledge primitives
- edge AI preprocessing
- embedded FPGA devices
- reproducible verification and synthesis workflows

## Engineering rules

When modifying or generating AccelFury FPGA cores:

- Prefer portable Verilog-2001.
- Do not introduce vendor primitives into generic RTL cores.
- Put vendor-specific logic into wrappers.
- Use explicit `clk` and `rst`.
- Avoid implicit clocking.
- Document reset polarity and reset timing.
- Document all clock domains.
- Document all CDC paths.
- Do not claim timing closure without a report.
- Do not claim board validation without board evidence.
- Do not claim formal verification without proof logs.
- Do not claim portability without at least attempted multi-tool or multi-family evidence.
- Keep interfaces simple, explicit, and documented.

## Preferred repository layout

Use this layout when possible:

```text
rtl/
tb/
sim/
formal/
docs/
scripts/
examples/
boards/
ci/
README.md
LICENSE
COMMERCIAL-LICENSE.md
```

## Documentation expectations

Each FPGA IP repository should eventually contain:

```text
docs/spec.md
docs/architecture.md
docs/interface.md
docs/reset.md
docs/clocking.md
docs/verification.md
docs/portability.md
docs/integration.md
docs/limitations.md
```

## Verification expectations

Prefer layered evidence:

1. static review;
2. lint;
3. simulation;
4. randomized simulation where useful;
5. formal checks where practical;
6. synthesis experiment;
7. board-level test where feasible.

## Commercial and legal caution

Public source code does not automatically mean commercial usage is permitted.

Always read:

- `LICENSE`
- `COMMERCIAL-LICENSE.md`
- repository README licensing section

For commercial use, contact:

`mail@accelfury.com`

## Do not do

Do not add marketing claims without evidence.

Do not invent benchmark numbers.

Do not state support for FPGA families unless supported by repository documentation or actual test reports.

Do not add hidden dependencies on proprietary vendor IP inside generic cores.

Do not remove existing warnings, limitations, or licensing notices.
