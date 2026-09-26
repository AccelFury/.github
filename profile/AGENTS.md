# AccelFury agent instructions

This file gives AI coding agents and automated analysis tools stable context for AccelFury repositories.

## Repository-specific note

If you are operating inside the AccelFury `.github` repository, treat `profile/README.md` as the main public-facing organization profile and keep `llms.txt`, `CONTACT.md`, and `COMMERCIAL-LICENSE.md` aligned with it.

## Project identity

AccelFury is a hardware acceleration company developing reusable IP and development tools for specialized compute. FPGA is the current implementation foundation.

Public description centers on acceleration, specialized compute and portability. Portability is an architectural principle: separate reusable component logic and contracts from target-specific integration; qualify support per component, version and target. Do not infer future target support.

Current offers are IP components, the af development toolchain and scoped engineering. Industrial/instrumentation and edge AI/robotics are workload directions; cryptography/ZK is a research direction. These are not a list of completed products or customer systems.

Use concise English prose, specific nouns and direct statements. Avoid slogans stacked into paragraphs, superlatives, invented benchmarks and long capability lists. Keep the rendered profile within 90 words: one category line, one introduction, three offer links, one portability statement and direct contacts. Link to product records for access, lifecycle, licensing and evidence. Do not add badge walls, invented product imagery, repeated slogans or internal editorial explanations. Material product limitations must remain accessible.

Canonical website messaging: `accelfury/webapp/scripts/content/messaging.mjs`; visual and voice rules: `accelfury/brand/BRANDBOOK.md`. Relative locations depend on the workspace. Public fact reference: https://accelfury.com/data/products.json.

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
