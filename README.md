---
title: "FPGA and Digital Design with Verilog - Collaboration Guide"
description: "Contributing guide for FPGA and Digital Design with Verilog course content"
tableOfContents: true
sidebar:
  order: 999
---

# FPGA and Digital Design with Verilog

![Build](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Contributors Welcome](https://img.shields.io/badge/contributors-welcome-orange)

**Read this course at:** [https://siliconwit.com/education/fpga-digital-design-verilog/](https://siliconwit.com/education/fpga-digital-design-verilog/)

A practical course on designing digital hardware in Verilog and running it on an FPGA. It assumes the [Digital Electronics and Logic](https://siliconwit.com/education/digital-electronics/) course as a prerequisite and starts from how to describe logic in Verilog, then takes the reader through simulation, state machines, real FPGA hardware, building microcontroller-style peripherals, memory and clock-domain crossing, a mini CPU, FPGA plus MCU co-design, and a capstone push from RTL to an ASIC with the Sky130 PDK and OpenLane.

## Status

This course is scaffolded and open for contribution. Each lesson file contains the full structure (headings, learning objectives, project, worked-example format, and summary) with contributor notes marked `{/* CONTRIBUTOR ... */}` showing exactly what to write in each section. Pick a lesson, follow the notes, and keep within the format below.

## Lessons

| # | Title | File |
|---|-------|------|
| 1 | Verilog Fundamentals | `verilog-fundamentals.mdx` |
| 2 | Simulation and Testbenches | `simulation-and-testbenches.mdx` |
| 3 | State Machines in Verilog | `state-machines-verilog.mdx` |
| 4 | First Design on a Real FPGA | `first-fpga-design-ice40.mdx` |
| 5 | Building MCU-Style Peripherals | `building-mcu-peripherals.mdx` |
| 6 | Memory, FIFOs, and Clock-Domain Crossing | `memory-fifos-clock-domain-crossing.mdx` |
| 7 | Building a Mini CPU | `building-a-mini-cpu.mdx` |
| 8 | FPGA plus MCU Co-Design | `fpga-mcu-codesign.mdx` |
| 9 | From FPGA to ASIC | `fpga-to-asic-sky130-openlane.mdx` |

## File Structure

```
fpga-digital-design-verilog/
├── index.mdx
├── verilog-fundamentals.mdx
├── simulation-and-testbenches.mdx
├── state-machines-verilog.mdx
├── first-fpga-design-ice40.mdx
├── building-mcu-peripherals.mdx
├── memory-fifos-clock-domain-crossing.mdx
├── building-a-mini-cpu.mdx
├── fpga-mcu-codesign.mdx
├── fpga-to-asic-sky130-openlane.mdx
└── README.md
```

## How to Contribute

All commands below work on Linux, macOS, and Windows (using Git Bash, PowerShell, or Command Prompt with Git installed).

### For Team Members (with push access)

**First time setup (clone the repo once):**

```bash
git clone https://github.com/SiliconWit/fpga-digital-design-verilog.git
cd fpga-digital-design-verilog
```

**Every time you start working:**

```bash
git pull origin main
```

Always pull before making changes. This avoids conflicts with other contributors.

**After making your changes:**

```bash
git add .
git commit -m "Brief description of what you changed"
git push origin main
```

**If you get a push error** (someone pushed before you):

```bash
git pull origin main
```

Git will merge the changes automatically in most cases. If there is a conflict, Git will mark the conflicting lines in the file. Open the file, choose which version to keep, then:

```bash
git add .
git commit -m "Resolve merge conflict"
git push origin main
```

**Tips to avoid conflicts:**

- Always `git pull origin main` before you start working
- Push your changes as soon as you are done, do not hold onto uncommitted work for long
- Coordinate with other contributors so two people are not editing the same file at the same time

### For External Contributors (without push access)

1. Fork the repository: [SiliconWit/fpga-digital-design-verilog](https://github.com/SiliconWit/fpga-digital-design-verilog)
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR-USERNAME/fpga-digital-design-verilog.git
   cd fpga-digital-design-verilog
   ```
3. Make your changes and commit:
   ```bash
   git add .
   git commit -m "Brief description of what you changed"
   git push origin main
   ```
4. Open a Pull Request against `main` on the original repository
5. Describe what you changed and why in the PR description

## Content Standards

- All lesson files use `.mdx` format
- Do not use `<BionicText>` in this course (it is an embedded and electronics course)
- No em dashes. Use commas, colons, semicolons, periods, or parentheses
- Minimal emojis, professional tone
- No `$` for currency (it triggers LaTeX parsing). Write `30 USD` instead
- Lesson intros must stand alone, with no assumptions about prior lessons, and end with about three hashtags
- Code blocks must include a title attribute:
  ````mdx
  ```verilog title="uart_tx.v"
  module uart_tx (input wire clk, ...);
  ```
  ````
- Keep large code blocks outside `<Steps>` (code inside Steps can break MDX parsing)
- Avoid `<=` inside markdown tables (it triggers JSX parsing). Use "or below" or "to" instead. It is fine inside code blocks
- Use Starlight components (`<Tabs>`, `<TabItem>`, `<Steps>`, `<Card>`, `<CardGrid>`) where appropriate
- Use the collapsible `<details>` plus `<Steps>` pattern for worked Application Questions and Solutions
- Where a lesson builds real hardware, include a short `:::tip[Instrument it]` callout: what to measure, the part, where it mounts, and a soft link to siliconwit.io
- Keep paragraphs concise and focused on practical application
- Include working Verilog (and Python or C where relevant) that readers can run

## Local Development

Clone the main site repository and initialize submodules:

```bash
git clone --recurse-submodules <main-repo-url>
cd siliconwit-com
npm install
npm run dev
```

To test a production build:

```bash
npm run build
```

## License

This course content is released under the [MIT License](LICENSE).
