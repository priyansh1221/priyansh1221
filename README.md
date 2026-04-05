<div align="center">

# Priyansh Patel

**AI Engineer who builds things that work in the real world, under real constraints.**

MSc Artificial Intelligence (Distinction) Â· London Met &nbsp;|&nbsp; BE Electronics (Distinction) Â· GTU

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/priyansh-1221)
[![Email](https://img.shields.io/badge/Email-1.priyannsh%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:1.priyannsh@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-priyansh1221.github.io-000?style=flat-square&logo=github)](https://priyansh1221.github.io/Priyansh/)

</div>

---

## How I think

Most AI work lives in notebooks. Mine ships to real environments with real constraints â devices that might lose internet, businesses that cannot afford cloud bills, security systems where a false alarm at 3am means someone ignores the next real one.

My design process starts with **what breaks the system in production**, not what maximises the benchmark. That shapes every technical decision I make.

---

## Projects

### Chitr â Real-Time Loss Prevention Platform
*2025 â Present*

A multi-model video intelligence system for detecting violence and theft on live CCTV.

**The hard problem was not accuracy â it was false alarms.**

Security guards who get 20 false alerts per hour stop trusting the system. I designed explicitly for a 2.7% false alarm rate, not just raw accuracy.

**Why two models?**

VideoMAE (masked autoencoder transformer) understands global context across 16-frame windows. SlowFast R101 has two pathways â one for slow semantic content, one for fast motion bursts. They fail in *different situations*, so ensembling them catches what each misses alone. Result: **0.941 ROC-AUC Â· 93.3% accuracy** on real CCTV footage.

**Why two-stage inference?**

A security guard needs to know *now*, not after a 3-second deep model run. So:
- YOLOv8 detects each person â instant pose-based heuristic score in **<0.5s**
- VideoMAE runs asynchronously and updates the confidence score

The guard sees something immediately. The accurate score arrives a moment later.

**Why fully local?**

CCTV footage contains footage of customers. Sending it to any cloud creates legal and privacy liability. The system runs entirely on-site â no data leaves the building.

**Why active learning via PostgreSQL?**

Every human review correction gets written back as a training signal. The model improves from every mistake a reviewer catches. This is the difference between a deployed AI system and a research project.

> Trained model checkpoints exist. This is a live system, not architecture code.

```
Stack: Python Â· PyTorch Â· VideoMAE Â· SlowFast R101 Â· YOLOv8 Â· FastAPI Â· PostgreSQL Â· OpenCV Â· MLflow
```

---

### JalaSai Auto Garage â Production Business System
*2024 â Present*

A complete management system for an established two-wheeler repair garage in Surat, Gujarat, India.

**The deployment constraint came first.**

The garage owner needed something that: works on a cheap Android phone, survives power cuts (offline = still works), costs nothing monthly, and can be updated by sending a WhatsApp message with the new file attached.

That constraint â not preference â is why the entire system is a **single HTML file with zero dependencies**.

**The QR encoder problem.**

The garage uses thermal printers for part sticker labels with QR codes. I needed QR generation that worked offline with no external library. I implemented the full **Reed-Solomon error correction + QR matrix encoding** algorithm from scratch in vanilla JS. No npm. No CDN. It lives inside the file.

**The SKU system is designed to be invented, not looked up.**

Every part follows `{BIKE}-{CAT}-{VARIANT}` â e.g. `OLA-BRA-PAD-FRT` for the Ola Electric front brake pad. A mechanic can create a new SKU on the spot without training or a lookup table. The code describes itself.

**WhatsApp over email â because I read the actual user.**

The bill goes out as a WhatsApp message in Hindi/Hinglish, the way a garage owner actually texts a customer. Not a PDF. Not email. A warm, informal message that feels like it came from a person.

**Google Sheets as the backend â because the owner already knows it.**

Rather than building a custom analytics dashboard requiring training, stock changes sync to Google Sheets via Apps Script. The owner already knows how to filter and sort in Sheets.

**Commission on labour only â because that is how garages in India actually work.**

Parts are billed at cost to the customer. A mechanic earns a percentage of their skilled labour, not of the parts they bolt on. I learned this by sitting with the business owner.

```
Stack: Vanilla HTML Â· CSS Â· JavaScript Â· localStorage Â· BarcodeDetector API Â· Browser Print API
```

[![View Repo](https://img.shields.io/badge/View_Repo-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/priyansh1221/JalaSai-Garage)

---

## Experience

| Period | Role | Company |
|--------|------|---------|
| Jan 2026 â Present | Agentic AI Developer | **Labelbox** (Remote) |
| Nov 2025 â Feb 2026 | Senior AI Generalist | **Outlier** (Remote) |
| Aug 2023 â Jan 2026 | Junior Data Scientist | **D'light Technologies** (London, UK) |
| Dec 2021 â Aug 2022 | Technical Analyst Intern | **Deserve Industrial Automation** (Surat) |

---

## Skills

**AI / CV:** Python Â· PyTorch Â· TensorFlow Â· OpenCV Â· VideoMAE Â· SlowFast Â· YOLOv8 Â· Scikit-learn

**Infra:** FastAPI Â· Docker Â· Kubernetes Â· PostgreSQL Â· Azure Â· AWS Â· MLflow Â· Git

**Data:** NumPy Â· Pandas Â· Tableau Â· Power BI Â· SQL Â· R

---

## GitHub Stats

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=priyansh1221&show_icons=true&theme=dark&hide_border=true&bg_color=0d1117&title_color=00c896&icon_color=00c896&count_private=true)

</div>

---

<div align="center">

*Open to AI/ML Engineering Â· Computer Vision Â· Production AI Systems Â· Remote or Relocation*

ð Surat, Gujarat, India &nbsp;Â·&nbsp; ð§ 1.priyannsh@gmail.com

</div>
