# Priyansh Patel

AI Engineer. MSc Artificial Intelligence, London Metropolitan University (Distinction). Based in Surat, India.

I've shipped two production systems from scratch: one runs on GPU servers in a retail environment, one runs in a browser tab with no internet connection. Both are live and in use.

---

## Projects

### Chitr &mdash; Real-Time Loss Prevention

Retail theft detection for a live deployment. Two models run in sequence: YOLOv8 scores body pose in under 500ms, and only if posture crosses a suspicion threshold does VideoMAE run async analysis on the full clip. The reason for this architecture is that false alarms are the actual business problem &mdash; every spurious alert that goes nowhere erodes trust in the system until someone turns it off. Keeping the fast model as a gate means VideoMAE only fires on real candidates, which is what pushed the false alarm rate down to 2.7%.

The system runs locally, not in the cloud. Latency requirements made remote inference impractical for a live retail feed. MLflow tracks every training run. PostgreSQL collects the edge cases operators flag, which feed back into the next training cycle. The model improves from its own mistakes in production.

**0.941 ROC-AUC &nbsp;&middot;&nbsp; 93.3% accuracy &nbsp;&middot;&nbsp; 2.7% false alarm rate**  
PyTorch &nbsp;&middot;&nbsp; VideoMAE &nbsp;&middot;&nbsp; SlowFast R101 &nbsp;&middot;&nbsp; YOLOv8 &nbsp;&middot;&nbsp; FastAPI &nbsp;&middot;&nbsp; PostgreSQL &nbsp;&middot;&nbsp; MLflow

Trained model checkpoints exist. This is a live system.

---

### JalaSai Auto Garage &mdash; Production Business System

Full workshop management for an established two-wheeler repair business in Surat. Jobs, stock, mechanics, expenses, analytics, QR label printing, WhatsApp billing.

The entire application is a single HTML file. No server, no npm, no build step. It runs from a USB drive if needed. LocalStorage is the database. The owner needed something that works on the shop floor without relying on internet, and that he could hand to a mechanic without any training overhead.

The QR encoder is written from scratch in vanilla JS &mdash; a full Reed-Solomon implementation. No library because there was no CDN available offline and bundling a QR library into a single file without a build tool is more trouble than writing the encoder. Part SKUs follow a structured pattern (`OLA-BRA-PAD-FRT`) so mechanics can read them without looking up a reference. WhatsApp billing uses `wa.me` deep links with pre-filled messages in Hindi/Hinglish because that is the language the customers speak. Mechanic commission is calculated on labour (only), not parts, because that is how the business actually works.

Vanilla JS &nbsp;&middot;&nbsp; localStorage &nbsp;&middot;&nbsp; BarcodeDetector API &nbsp;&middot;&nbsp; Browser Print API &nbsp;&middot;&nbsp; WhatsApp deep links

---

## Experience

| Period | Role | Company |
|---|---|---|
| Jan 2026 &ndash; Present | Agentic AI Developer | Labelbox |
| Nov 2025 &ndash; Feb 2026 | Senior AI Generalist | Outlier |
| Aug 2023 &ndash; Jan 2026 | Junior Data Scientist | D'light Technologies |
| Sep 2022 &ndash; Sep 2023 | MSc Artificial Intelligence (Distinction) | London Metropolitan University |
| Dec 2021 &ndash; Aug 2022 | Technical Analyst Intern | Deserve Industrial Automation |
| Aug 2018 &ndash; May 2022 | BE Electronics & Communications (6.79 CGPA) | Gujarat Technological University |

---

## Skills

Python &nbsp;&middot;&nbsp; PyTorch &nbsp;&middot;&nbsp; FastAPI &nbsp;&middot;&nbsp; PostgreSQL &nbsp;&middot;&nbsp; MLflow &nbsp;&middot;&nbsp; YOLOv8 &nbsp;&middot;&nbsp; VideoMAE &nbsp;&middot;&nbsp; Vanilla JS &nbsp;&middot;&nbsp; HTML/CSS &nbsp;&middot;&nbsp; Git &nbsp;&middot;&nbsp; Linux

---

[![GitHub Stats](https://github-readme-stats.vercel.app/api?username=priyansh1221&show_icons=true&theme=dark&hide_border=true)](https://github.com/priyansh1221)
