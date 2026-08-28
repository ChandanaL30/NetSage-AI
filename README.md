# 🌐 NetSage AI

### AI-Assisted Network Troubleshooting & Responsible Diagnosis

**NetSage AI** is an educational AI-assisted network troubleshooting system designed to simulate the workflow of a network support engineer.

It analyzes network symptoms and diagnostic command outputs to help identify possible root causes, map issues to the appropriate OSI layer, provide supporting evidence, suggest the next troubleshooting command, and recommend safe remediation steps.

> ⚠️ **Important:** NetSage AI is an educational and decision-support project. It does not autonomously modify network configurations or replace human network engineers.

---

## ✨ Why NetSage AI?

Network troubleshooting often requires engineers to manually interpret:

* User-reported symptoms
* Network topology information
* Cisco-style `show` command outputs
* IP addressing and subnet configuration
* VLAN and trunk configuration
* Interface states
* Routing information

NetSage AI brings these signals together into a structured troubleshooting workflow.

Instead of simply returning an answer, the system is designed to produce an explainable diagnosis containing:

```text
Symptom
   ↓
Evidence Analysis
   ↓
Probable Root Cause
   ↓
OSI Layer Identification
   ↓
Confidence Assessment
   ↓
Recommended Next Command
   ↓
Suggested Fix
   ↓
Human Review
```

The goal is not just automation — but **transparent, explainable, and responsible AI-assisted troubleshooting**.

---

# 🚀 Key Features

* 🧠 **Structured AI diagnosis workflow**
* 🌐 **Network troubleshooting case dataset**
* 🔍 **Root cause identification**
* 🧩 **OSI layer mapping**
* 📊 **Confidence-based diagnosis**
* 📌 **Evidence-based explanations**
* 💻 **Cisco-style command analysis**
* 🛡️ **Deterministic Python rule checker**
* 👨‍💻 **Human-in-the-loop review workflow**
* 📋 **Responsible AI logging**
* 📈 **Interactive project dashboard**
* 🧪 **30 structured troubleshooting scenarios**
* ⚠️ **Safe-by-design educational approach**

---

# 🏗️ Project Architecture

```text
                         ┌─────────────────────┐
                         │   Network Symptom   │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Diagnostic Evidence │
                         │  Show Command Data  │
                         └──────────┬──────────┘
                                    │
                                    ▼
                    ┌──────────────────────────────┐
                    │     NetSage AI Diagnosis     │
                    │                              │
                    │ • Root Cause Analysis        │
                    │ • OSI Layer Classification   │
                    │ • Evidence Extraction        │
                    │ • Confidence Assessment      │
                    │ • Next Command Suggestion    │
                    │ • Fix Recommendation         │
                    └──────────────┬───────────────┘
                                   │
                    ┌──────────────┴───────────────┐
                    │                              │
                    ▼                              ▼
         ┌────────────────────┐        ┌────────────────────┐
         │ Deterministic Rule │        │ Human Review       │
         │ Checker            │        │ & Validation       │
         └──────────┬─────────┘        └──────────┬─────────┘
                    │                             │
                    └──────────────┬──────────────┘
                                   ▼
                        ┌─────────────────────┐
                        │ Responsible AI Log │
                        │ & Dashboard        │
                        └─────────────────────┘
```

---

# 📂 Project Structure

```text
NetSage-AI/
│
├── project/
│   ├── cases.csv
│   ├── checker.py
│   ├── diagnose-prompt.md
│   ├── responsible-ai-log.json
│   └── responsible-ai-log.md
│
├── dashboards/
│   └── dashboard.html
│
├── screenshots/
│   ├── NetSage AI #U2014 Human Review Decision Distribution.png
│   ├── netsage_ai_human_review_chart.png
│   ├── Screenshot (1).png
│   ├── Screenshot (3).png
│   ├── Screenshot (4).png
│   └── Screenshot (5).png
│
└── README.md
```

---

# 🧠 How It Works

## 1. Network Issue Input

Each troubleshooting scenario contains structured information such as:

* Network symptom
* Topology information
* Diagnostic command outputs
* Expected fault
* OSI layer
* Severity
* Suggested next command
* Expected remediation
* Human review status

Example:

```text
Symptom:
PC in VLAN 20 cannot communicate with another host.

Diagnostic Evidence:
show vlan brief

Possible Analysis:
The required VLAN may be missing from one of the switch ports.

OSI Layer:
Layer 2 — Data Link

Suggested Next Command:
show interfaces switchport

Recommended Fix:
Verify and correct the access VLAN assignment.
```

---

## 2. AI-Assisted Diagnosis

The structured prompt library guides the AI to generate consistent troubleshooting results.

The diagnosis workflow focuses on producing:

```text
Root Cause
OSI Layer
Confidence
Evidence
Next Command
Fix Steps
Human Review Requirement
```

This makes the output easier to validate compared with an unstructured chatbot response.

---

## 3. Deterministic Rule Validation

In addition to AI-assisted reasoning, NetSage AI includes a lightweight Python-based deterministic rule checker.

The checker validates common network conditions such as:

* Duplicate IP addresses
* Subnet mask mismatches
* Default gateway mismatches
* Interface status
* VLAN availability
* Route presence

Example checks include:

```python
check_duplicate_ips()
check_subnet_mask()
check_gateway()
check_interface_status()
check_vlan()
check_routes()
```

The checker produces interpretable results:

```text
[PASS]
[FAIL]
[WARNING]
[INFO]
```

This hybrid approach combines **structured AI reasoning with deterministic validation**.

---

# 🧪 Running the Rule Checker

Clone the repository:

```bash
git clone https://github.com/ChandanaL30/NetSage-AI.git
```

Navigate to the project:

```bash
cd NetSage-AI/project
```

Run the checker:

```bash
python checker.py
```

Example output:

```text
NetSage AI — Deterministic Rule Checker

CASE: NS-DEMO

[FAIL] Duplicate IP(s) detected
[FAIL] Mask/network mismatch
[PASS] Gateway is in host subnet
[FAIL] Interface is administratively down/down
[PASS] VLAN exists and is active
[WARNING] Route may be missing
```

> The rule checker is intentionally lightweight and educational. It validates selected patterns and does not attempt to function as a complete Cisco configuration parser.

---

# 📊 Troubleshooting Dataset

The project includes a structured dataset of **30 network troubleshooting cases**.

Each case contains fields such as:

| Field                   | Description                            |
| ----------------------- | -------------------------------------- |
| `case_id`               | Unique troubleshooting case identifier |
| `symptom`               | Reported network issue                 |
| `topology_note`         | Simplified topology context            |
| `show_outputs`          | Diagnostic command output              |
| `expected_fault`        | Expected root cause                    |
| `osi_layer`             | Relevant OSI layer                     |
| `concept`               | Networking concept involved            |
| `severity`              | Issue severity                         |
| `expected_next_command` | Recommended troubleshooting command    |
| `expected_fix`          | Suggested remediation                  |
| `human_review_status`   | Human validation status                |

The scenarios cover common networking concepts such as:

* VLAN configuration
* Access ports
* Trunking
* IP addressing
* Subnet masks
* Default gateways
* Interface status
* Routing
* Connectivity failures
* Network segmentation

---

# 🛡️ Responsible AI

NetSage AI follows a **human-in-the-loop** approach.

The system is designed to assist with diagnosis rather than independently making changes to a production network.

### Key principles

* ✅ Explainable diagnosis
* ✅ Evidence-based reasoning
* ✅ Confidence awareness
* ✅ Human review
* ✅ Transparent limitations
* ❌ No autonomous network configuration changes
* ❌ No claim of guaranteed correctness
* ❌ No replacement for qualified network engineers

The project records review and evaluation information in:

```text
responsible-ai-log.json
responsible-ai-log.md
```

---

# 📈 Dashboard

The project includes an HTML dashboard for visualizing project insights and evaluation results.

To view it locally:

```bash
cd dashboards
```

Then open:

```text
dashboard.html
```

The dashboard can be opened directly in a modern web browser.

---

# 📸 Project Preview

## Human Review Distribution

<img width="1580" height="1035" alt="netsage_ai_human_review_chart" src="https://github.com/user-attachments/assets/f156d0f2-a36f-495a-8fb7-fa31c3f22768" />

## NetSage AI Review Decision Analysis

<img width="960" height="540" alt="NetSage AI — Human Review Decision Distribution" src="https://github.com/user-attachments/assets/e14e4535-72ca-4f63-bb71-5cf12d930d62" />

## Project Screenshots

<img width="1920" height="1080" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/d845d75e-ae64-43ac-bb4c-3abb6b0efe60" />
<img width="1920" height="1080" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/73c1f33f-1062-4ebf-9efd-64597f9b423b" />
<img width="1920" height="1080" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/51cfa6b6-2685-401c-8588-324cd0da2538" />
<img width="1920" height="1080" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/38c09c97-e122-488c-8c75-74228fd94479" />

---

# 🔎 Example Troubleshooting Workflow

### Input

```text
Symptom:
A PC cannot communicate with another device in the expected network.

Diagnostic Output:
Interface and VLAN information from network devices.
```

### NetSage AI Analysis

```text
Possible Root Cause:
Incorrect VLAN or interface configuration.

OSI Layer:
Layer 2 — Data Link Layer

Confidence:
Medium

Evidence:
The observed interface/VLAN state does not match
the expected network configuration.

Suggested Next Command:
show interfaces switchport

Suggested Fix:
Verify VLAN assignment and interface configuration.

Human Review:
Recommended before applying configuration changes.
```

---

# 🛠️ Tech Stack

| Category        | Technologies                                    |
| --------------- | ----------------------------------------------- |
| Programming     | Python                                          |
| Networking      | Cisco-style networking concepts and CLI outputs |
| Data            | CSV                                             |
| Validation      | Python `ipaddress`, regular expressions         |
| AI Workflow     | Structured prompt engineering                   |
| Visualization   | HTML Dashboard                                  |
| Governance      | Responsible AI logging                          |
| Version Control | Git & GitHub                                    |

---

# 🎯 Project Goals

NetSage AI was built to explore how AI can assist network troubleshooting while maintaining transparency and human oversight.

The project focuses on answering:

> **Can AI-assisted reasoning, combined with deterministic validation and human review, help structure the network troubleshooting process?**

The project is designed as a practical exploration of:

* AI-assisted diagnostics
* Explainable AI
* Prompt engineering
* Networking fundamentals
* Rule-based validation
* Human-in-the-loop systems
* Responsible AI practices

---

# ⚠️ Limitations

NetSage AI is a prototype and has several limitations.

* The rule checker supports only selected networking patterns.
* It is not a complete Cisco IOS parser.
* AI-generated diagnoses may be incorrect or incomplete.
* Confidence scores should not be treated as guarantees.
* Real production environments may contain significantly more complexity.
* Human validation is recommended before applying any network changes.

---

# 🔮 Future Improvements

Potential future directions include:

* [ ] Interactive Streamlit or React dashboard
* [ ] Automated parsing of Cisco CLI outputs
* [ ] Retrieval-Augmented Generation (RAG) using networking documentation
* [ ] Packet Tracer or virtual lab integration
* [ ] Larger and more diverse troubleshooting dataset
* [ ] Automated evaluation metrics
* [ ] Multi-agent troubleshooting workflow
* [ ] Knowledge graph for network dependencies
* [ ] Network topology visualization
* [ ] REST API for diagnosis requests
* [ ] Unit and integration tests
* [ ] CI/CD with GitHub Actions

---

# 🤝 Contributing

Contributions, ideas, and improvements are welcome!

If you'd like to contribute:

1. Fork this repository
2. Create a new branch

```bash
git checkout -b feature/your-feature-name
```

3. Make your changes
4. Commit your work

```bash
git commit -m "Add your feature"
```

5. Push the branch

```bash
git push origin feature/your-feature-name
```

6. Open a Pull Request

---

# 🌟 Support the Project

If you find **NetSage AI** interesting or useful:

⭐ **Star this repository**

🍴 **Fork it**

🐛 **Report issues**

💡 **Share ideas and improvements**

Your support helps the project grow!

---

# 📄 License

This project is licensed under the **MIT License**.

You are free to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of this software, subject to the terms of the MIT License.

See the [`LICENSE`](LICENSE) file for the complete license text.

---

# 🙌 Acknowledgements

This project was created as an exploration of the intersection between:

* Artificial Intelligence
* Data-driven reasoning
* Computer Networking
* Network Troubleshooting
* Explainable AI
* Responsible AI

---

<div align="center">

### ⭐ If you like the idea behind NetSage AI, consider giving the repository a star!

**Built to explore the future of AI-assisted network troubleshooting.**

</div>
