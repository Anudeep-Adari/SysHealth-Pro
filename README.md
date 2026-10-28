<div align="center">

# 🩺 SysHealth-Pro

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&duration=3000&pause=1000&color=2EA043&center=true&vCenter=true&width=620&lines=Modular+Operating+System+Diagnostics;Hardware+Telemetry+%26+Metric+Collectors;Extensible+Plugin-Based+Sensor+Architecture;Cross-Platform+System+Health+Monitoring" alt="Typing SVG" />
</p>

<p align="center">
  <strong>High-Frequency System Diagnostics, Hardware Metric Collection & Extensible Health Telemetry Architecture</strong>
</p>

<!-- Badges -->
<p align="center">
  <a href="https://www.python.org/downloads/"><img src="https://img.shields.io/badge/Python-3.11%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.11+" /></a>
  <a href="https://github.com/Anudeep-Adari/SysHealth-Pro"><img src="https://img.shields.io/badge/Platform-Windows_%7C_Linux-0078D4?style=for-the-badge&logo=windows&logoColor=white" alt="Platform" /></a>
  <a href="https://coderabbit.ai"><img src="https://img.shields.io/badge/CodeRabbit-AI_Reviewed-FF5C00?style=for-the-badge&logo=coderabbit&logoColor=white" alt="CodeRabbit" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="License" /></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Architecture-Modular_Collectors-8957E5?style=flat-square" />
  <img src="https://img.shields.io/badge/Design-Domain--Driven-10B981?style=flat-square" />
  <img src="https://img.shields.io/badge/Overhead-%3C_1%25_CPU-brightgreen?style=flat-square" />
</p>

---

</div>

## 📌 Architecture & Metric Ingestion Pipeline

```mermaid
flowchart TD
    subgraph Sensors ["🔌 Metric Collectors (collectors/)"]
        CPU["CPU Frequency & Thermal Collector"]
        RAM["RAM & Working-Set Pooler"]
        Disk["Disk I/O & IOPS Collector"]
        Net["Network Throughput & Socket Monitor"]
    end

    subgraph CoreEngine ["⚙️ Core Telemetry Engine (core/)"]
        Aggregator["Metric Aggregation & Sliding Window"]
        Anomaly["Threshold & Anomaly Evaluator"]
        Storage["Local In-Memory Circular Buffer"]
    end

    subgraph Outbound ["📊 Presentation & Reporting (ui/)"]
        Dashboard["PySide / CLI Telemetry Dashboard"]
        Alerts["Event Warning & Telemetry Log Dispatcher"]
    end

    Sensors --> Aggregator
    Aggregator --> Anomaly
    Anomaly --> Storage
    Storage --> Dashboard
    Anomaly -.->|Threshold Breach| Alerts
```

---

## ⚡ Key Architectural Capabilities

* **Decoupled Collector Plugins:** Each hardware subsystem operates in isolation under `collectors/`, allowing custom sensor drivers without altering core analysis logic.
* **Non-Blocking Sampling:** Utilizes asynchronous pooling to maintain high-frequency telemetry without creating thread contention.
* **Minimal Runtime Footprint:** Optimized for continuous background operation with minimal memory overhead (<30MB) and near-zero CPU usage.

---

## 🖥️ Live Telemetry Mockup

```
================================================================================
  SysHealth-Pro Telemetry Monitor ─ [● LIVE CAPTURE]
================================================================================
  HOST: Workstation-01  │  UPTIME: 9d 14h 22m  │  POLL_INTERVAL: 1000ms
--------------------------------------------------------------------------------
  CPU  Usage: 14.2%   │ Base Clock: 3.8 GHz   │ Current: 4.62 GHz  [TEMP: 48°C]
  RAM  Usage: 42.1%   │ Committed: 13.4 GB    │ Total: 32.0 GB
  DISK Activity: 2%   │ Read: 1.2 MB/s        │ Write: 0.4 MB/s   [HEALTH: 100%]
  NET  In: 142 KB/s   │ Out: 48 KB/s          │ Active Connections: 64
================================================================================
```

---

## 🚀 Quickstart & Setup

```bash
# Clone the repository
git clone https://github.com/Anudeep-Adari/SysHealth-Pro.git
cd SysHealth-Pro

# Create virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install psutil pydantic
```

---

<div align="center">

Crafted with high engineering precision by **[Anudeep Adari](https://github.com/Anudeep-Adari)**  
Continuous AI Code Reviews powered by **CodeRabbit**

</div>
