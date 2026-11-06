<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,100:1f6feb&height=200&section=header&text=Harit%20Thakkar&fontSize=60&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Digital%20Hardware%20%7C%20FPGA%20%7C%20Verification&descAlignY=60&descSize=20" width="100%" alt="Harit Thakkar banner" />

<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=22&duration=3000&pause=1000&color=58A6FF&center=true&vCenter=true&width=700&lines=Computer+Engineering+%40+University+of+Waterloo;I+build+FPGA+projects+from+scratch;Learning+formal+verification;Looking+for+hardware+and+silicon+co-ops" alt="Typing animation" /></a>

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-harit--thakkar-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/harit-thakkar)
[![GitHub](https://img.shields.io/badge/GitHub-HThakkar23-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/HThakkar23)
![Waterloo](https://img.shields.io/badge/University%20of%20Waterloo-Computer%20Engineering-FFD54F?style=for-the-badge)

</div>

---

## About me

I'm a Computer Engineering co-op student at the University of Waterloo. I like digital hardware, especially the parts where you have to prove a design really works. I build small FPGA projects from scratch, measure what they do, and write down how they work.

I'm also a member of **UWASIC**, the UW student chip design team, where I work on digital design in SystemVerilog.

## Right now

- Building on a **Real Digital Blackboard** (AMD Zynq-7007S) with Verilog and Vivado
- Learning formal verification with SystemVerilog assertions and SymbiYosys
- Working as a software engineer co-op at Shoplogix

---

## Featured projects

<table>
<tr>
<td width="33%" valign="top">

### UART to VGA Terminal
[`uart-vga-terminal`](https://github.com/HThakkar23/uart-vga-terminal)

Text terminal with two clock domains.

- 100 MHz UART logic, 25 MHz VGA pixel clock
- 80x30 text at 640x480 using 2 of 50 block RAM tiles
- Baud rate within 0.47% of 115200
- Built-in loopback self-test

</td>
<td width="33%" valign="top">

### Logic Analyzer
[`logic-analyzer`](https://github.com/HThakkar23/logic-analyzer)

8 channels, 100 Sa/s to 100 MSa/s.

- 4096-sample buffer with pre and post trigger
- Binary command protocol over UART
- Full dump measured at 355.6 ms
- Caught an off-by-one in the trigger counter

</td>
<td width="33%" valign="top">

### PDM Audio DSP
[`pdm-audio-dsp`](https://github.com/HThakkar23/pdm-audio-dsp)

Mic to speaker with no codec chip.

- 3rd-order CIC filter, 3.125 MHz PDM to 16-bit audio
- Delta-sigma DAC drives the speaker pin directly
- 101.95 dB calculated SNR
- Python models of every stage

</td>
</tr>
</table>

<details>
<summary><b>How the terminal crosses clock domains</b> (click to open)</summary>

<br/>

```mermaid
flowchart LR
    A[UART RX<br/>100 MHz] --> B[Text logic<br/>100 MHz]
    B -->|write port| C[(Dual-clock<br/>block RAM)]
    C -->|read port| D[VGA timing<br/>25 MHz]
    B -. toggle synchronizer .-> D
    D --> E[640x480 video out]
```

The write side and the read side of the RAM run on different clocks. A toggle synchronizer carries control signals across, so no vendor FIFO or CDC IP is needed.

</details>

<details>
<summary><b>A bug I found in the logic analyzer</b> (click to open)</summary>

<br/>

The post-trigger counter was off by one. It undercounted the trigger window by a single sample and put the ring buffer base address in the wrong place. I found it by tracing a tiny case by hand (depth 8, pre-trigger 4) before trusting the full design, then wrote a testbench that checks that exact case.

</details>

---

## Skills

![Verilog](https://img.shields.io/badge/Verilog-1F6FEB?style=for-the-badge)
![SystemVerilog](https://img.shields.io/badge/SystemVerilog-0D47A1?style=for-the-badge)
![Vivado](https://img.shields.io/badge/Vivado-ED1C24?style=for-the-badge&logo=amd&logoColor=white)
![FPGA](https://img.shields.io/badge/FPGA-Zynq--7000-ED1C24?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=for-the-badge&logo=espressif&logoColor=white)

| Area | What I use |
| --- | --- |
| Digital design | FSM design, clock domain crossing, simulation, waveform debugging |
| Interfaces | UART, VGA, PDM audio |
| Signal processing | CIC decimation, delta-sigma, fixed-point sizing |
| Learning now | SVA, SymbiYosys |

---

## GitHub stats

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=HThakkar23&show_icons=true&theme=tokyonight&hide_border=true" alt="GitHub stats" />
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=HThakkar23&layout=compact&theme=tokyonight&hide_border=true" alt="Top languages" />

<img src="https://github-readme-activity-graph.vercel.app/graph?username=HThakkar23&theme=tokyo-night&hide_border=true" width="100%" alt="Contribution graph" />

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,100:1f6feb&height=100&section=footer" width="100%" alt="footer" />

</div>
