<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="Abhinav Tarigoppula — AI/ML Engineer · Open-Source Contributor"/>
</p>

<p align="center">
  <i>Final-year B.Tech CSE (AI/ML), GITAM University · Visakhapatnam, India</i>
</p>

<p align="center">
  🟢 <b>Open to AI engineer roles</b> — internships now, full-time from 2027 · remote or on-site · <a href="mailto:abhinaaavvv07187@gmail.com">get in touch</a>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/abhinav0702/">LinkedIn</a> &nbsp;·&nbsp;
  <a href="https://www.researchgate.net/profile/Abhinav-Tarigoppula">ResearchGate</a> &nbsp;·&nbsp;
  <a href="https://scholar.google.com/citations?user=2LcRmRcAAAAJ">Google Scholar</a> &nbsp;·&nbsp;
  <a href="https://www.abhinavbuilds.online/">Portfolio</a> &nbsp;·&nbsp;
  <a href="mailto:abhinaaavvv07187@gmail.com">Email</a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=kratos0718&label=profile%20views&style=flat-square&color=2dd4bf&labelColor=0d1117" alt="profile views"/>
  &nbsp;
  <a href="https://www.researchgate.net/profile/Abhinav-Tarigoppula"><img src="https://img.shields.io/badge/IEEE_ISED_2026-accepted-1f6feb?style=flat-square&labelColor=0d1117" alt="IEEE ISED 2026 accepted"/></a>
  &nbsp;
  <a href="https://github.com/kratos0718?tab=achievements"><img src="https://img.shields.io/badge/GitHub_achievements-6-a371f7?style=flat-square&labelColor=0d1117" alt="6 GitHub achievements"/></a>
</p>

---

I build tools that make AI/ML systems more reliable. Most AI demos are slick; most AI in production is messy — I like working in that gap, close enough to the real problem to build something that doesn't fall apart outside a notebook. Author of [codehound](https://github.com/kratos0718/codehound), and an open-source contributor to JAX (Google), pydantic, Black and asyncpg.

<table>
<tr>
<td valign="top" width="52%">

**Currently**

- 🤖 built **[AgentDesk](https://github.com/kratos0718/agentdesk)** — multi-agent assistant with tool calling, RAG, guardrails and evals
- 🔭 built **DocGuard-VLM** — QLoRA fine-tuned Qwen2-VL for document extraction + forgery detection
- 🐕 building **codehound** — a static analyzer that finds real bugs in AI codebases
- 📄 co-author paper **accepted at IEEE ISED 2026**, NIT Warangal
- 🌱 learning: LoRA/PEFT fine-tuning, vision-language models
- 🎯 targeting AI/ML research roles & a funded MS

</td>
<td valign="top">

**At a glance**

```text
Open source  JAX (Google) · pydantic · Black · asyncpg
Domains      AI frameworks · message queues · IoT
             test doubles (fake fs, fake Redis)
             databases · build tooling
             network security · data pipelines
Languages    Python · Java · PHP
Flagship     codehound (104-check AST analyzer)
Bug classes  async task GC, blocking I/O,
             resource leaks, shared state
Research     accepted @ IEEE ISED 2026
Stack        Python · Java · PyTorch · LLMs
```

</td>
</tr>
</table>

---

### 🐕 codehound — [github.com/kratos0718/codehound](https://github.com/kratos0718/codehound)

An AST-based Python static analyzer — **104 checks, zero dependencies, CI on Python 3.9–3.12.** Each check is distilled from a real bug found and fixed in a popular open-source project: fire-and-forget tasks that get garbage-collected mid-run, event-loop-blocking calls inside `async` functions, mutable default arguments, unclosed resources, and more. Several of the merged fixes below were surfaced by it. Try it on any GitHub repo or local folder at the [playground](https://kratos0718.github.io/codehound/) — no install needed.

<a href="https://github.com/kratos0718/codehound"><img src="https://img.shields.io/badge/View_repository-24292f?style=flat-square&logo=github&logoColor=white" alt="View repository"/></a>
<a href="https://kratos0718.github.io/codehound/"><img src="https://img.shields.io/badge/Try_the_playground-2dd4bf?style=flat-square&logo=vercel&logoColor=black" alt="Try the playground"/></a>

---

### 🔧 Open-source contributions

Open-source contributor to **JAX (Google)**, **pydantic**, **Black** and **asyncpg**. A few fixes I can walk through line by line:

<p align="center">
  <img src="https://img.shields.io/badge/async_event--loop_blocking-8250df?style=flat-square" alt=""/>
  <img src="https://img.shields.io/badge/fire--and--forget_task_GC-8250df?style=flat-square" alt=""/>
  <img src="https://img.shields.io/badge/resource_leaks-8250df?style=flat-square" alt=""/>
  <img src="https://img.shields.io/badge/mutable_defaults_(B006)-8250df?style=flat-square" alt=""/>
  <img src="https://img.shields.io/badge/timestamp_precision_(Java)-cf222e?style=flat-square" alt=""/>
  <img src="https://img.shields.io/badge/SNMP_index_decoding-cf222e?style=flat-square" alt=""/>
</p>

<table>
<tr>
<td valign="top" width="150" align="center">
<img src="https://github.com/jax-ml.png" width="34"/><br/>
<b>JAX</b><br/><sub>Google · 36k⭐</sub>
</td>
<td valign="top">
<code>jax.random.choice</code> dropped every non-sampled dimension when asked for zero samples, so <code>choice(key, a, shape=(0,), axis=1)</code> on a 3×4 array returned <code>(0,)</code> where NumPy returns <code>(3, 0)</code>. The output shape is now computed once for both paths, and the existing NumPy-comparison test covers empty shapes.<br/>
<a href="https://github.com/jax-ml/jax/pull/42430">jax #42430</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/pytest-dev.png" width="34"/><br/>
<b>pyfakefs</b><br/><sub>pytest-dev</sub>
</td>
<td valign="top">
The fake <code>os.rename</code> dropped a trailing separator before checking it, so <code>rename("foo", "bar/")</code> on a regular file silently renamed it where Linux and macOS fail. Now raises the errno each OS raises, verified against the real filesystem on both.<br/>
<a href="https://github.com/pytest-dev/pyfakefs/pull/1344">pyfakefs #1344</a> · <a href="https://github.com/pytest-dev/pyfakefs/pull/1343">#1343</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/MagicStack.png" width="34"/><br/>
<b>asyncpg</b><br/><sub>PostgreSQL driver · 8k⭐</sub>
</td>
<td valign="top">
<code>Connection.query_logger()</code> removed its logger only when the block exited cleanly, so an exception inside it left the logger attached and logging every later query on that connection.<br/>
<a href="https://github.com/MagicStack/asyncpg/pull/1373">asyncpg #1373</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/pydantic.png" width="34"/><br/>
<b>pydantic · black</b><br/><sub>29k⭐ · 42k⭐</sub>
</td>
<td valign="top">
A bare <code>isinstance(...)</code> statement in pydantic's decorator collection that checked the wrong variable and discarded its result, turned into a real invariant. And two grammar-file handles in black's <code>blib2to3</code> converter that were opened and never closed — <b>found by codehound</b>.<br/>
<a href="https://github.com/pydantic/pydantic/pull/13858">pydantic #13858</a> · <a href="https://github.com/psf/black/pull/5432">black #5432</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/secdev.png" width="34"/><br/>
<b>scapy · pymodbus</b><br/><sub>12.6k⭐ · 2.8k⭐</sub>
</td>
<td valign="top">
In <b>pymodbus</b>, every device identity shared one class-level dict, so creating any identity changed what a running Modbus server reported. The maintainer merged it within the hour: <i>"one that have been on my list for a long time"</i>. In <b>scapy</b>, a missing <code>tcpreplay</code> surfaced as an <code>UnboundLocalError</code> instead of scapy's own "is it installed?" message.<br/>
<a href="https://github.com/pymodbus-dev/pymodbus/pull/3036">pymodbus #3036</a> · <a href="https://github.com/secdev/scapy/pull/5204">scapy #5204</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
</table>

---

### 📄 Research

Papers with Dr. Chandrakanta Mahanty (GITAM) and solo work. *(Full list on [ResearchGate](https://www.researchgate.net/profile/Abhinav-Tarigoppula))*

- **Async Landmines in the AI Stack: An AST-Based Empirical Study of Concurrency and Resource-Management Defects in Popular Python AI/ML Frameworks** (sole author)
  <br/><a href="https://doi.org/10.5281/zenodo.24367554"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.24367554.svg" alt="DOI 10.5281/zenodo.24367554"/></a> Preprint · 1,377 defects across 29 frameworks; maintainers confirmed 11 of 12 reviewed fixes
- **Five Recurring Defect Patterns in Python AI Infrastructure: Lessons from 51 Merged Upstream Fixes** (sole author)
  <br/><a href="https://doi.org/10.5281/zenodo.24372911"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.24372911.svg" alt="DOI 10.5281/zenodo.24372911"/></a> Technical note · blocked event loops, happy-path-only cleanup, shared state, fire-and-forget tasks, empty inputs
- **Identical Seeds, Coupled Splits: A Post-Mortem on Robustness Evaluation in LoRA Fine-Tuning of Qwen2-VL-2B** (sole author)
  <br/><a href="https://doi.org/10.5281/zenodo.24372913"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.24372913.svg" alt="DOI 10.5281/zenodo.24372913"/></a> Technical report · how identical confusion matrices exposed a seeding bug in DocGuard-VLM's evaluation
- **Merged Open-Source Pull Requests in Python AI/ML and Infrastructure Projects (2026)** (dataset)
  <br/><a href="https://doi.org/10.5281/zenodo.24372797"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.24372797.svg" alt="DOI 10.5281/zenodo.24372797"/></a> 51 merged PRs across 37 repositories in 31 organisations
- **Machine Learning-Based Student Performance Prediction: A Comparative Study Using Ensemble Methods and Explainable AI**
  <br/><img src="https://img.shields.io/badge/accepted-1a7f37?style=flat-square" alt="accepted"/> 14th International Conference on Intelligent Systems and Embedded Design (**ISED 2026**), NIT Warangal · Publisher: **IEEE**
- **From Compression Ratios to Wall-Clock Gains: A Systems-Level Review of Lightweight Deep Learning Deployment on Edge Hardware**
  <br/><img src="https://img.shields.io/badge/abstract_submitted-0969da?style=flat-square" alt="abstract submitted"/> *Lightweight Deep Learning for Efficient AI*, edited volume · Publisher: **Springer** (Scopus) · first author
- **Behavior-Driven Adaptive Learning Agents for Personalized Education** — *under review, IEEE*
- **HAPS: Hybrid AI Proctoring (dual-stream CNNs + YOLO)** — *preprint*

<a href="https://www.researchgate.net/profile/Abhinav-Tarigoppula"><img src="https://img.shields.io/badge/View_full_publication_list-00CCBB?style=flat-square&logo=researchgate&logoColor=white" alt="View full publication list"/></a> <a href="https://scholar.google.com/citations?user=2LcRmRcAAAAJ"><img src="https://img.shields.io/badge/Google_Scholar-4285F4?style=flat-square&logo=googlescholar&logoColor=white" alt="Google Scholar"/></a>

---

### 🚀 Selected projects

<table>
<tr>
<td width="50%" align="center">
<a href="https://www.pathforge.online/"><img src="https://raw.githubusercontent.com/kratos0718/portfolio/main/public/logos/projects/pathforge.svg" width="100%"/></a><br/>
<b>PathForge</b><br/><sub>AI placement-prep platform — RAG over FAISS with a skill-gap scoring layer</sub>
</td>
<td width="50%" align="center">
<a href="https://mark-me-ih3h.vercel.app/"><img src="https://raw.githubusercontent.com/kratos0718/portfolio/main/public/logos/projects/markme.svg" width="100%"/></a><br/>
<b>MarkMe</b><br/><sub>Attendance — face recognition + GPS geo-fencing + rotating session keys</sub>
</td>
</tr>
<tr>
<td width="50%" align="center">
<a href="https://soulsyncfinal.vercel.app/"><img src="https://raw.githubusercontent.com/kratos0718/portfolio/main/public/logos/projects/soulsync.svg" width="100%"/></a><br/>
<b>SoulSync</b><br/><sub>Transformer-based emotion classification for mental-health support (SIH 2024)</sub>
</td>
<td width="50%" align="center">
<a href="https://github.com/kratos0718"><img src="https://raw.githubusercontent.com/kratos0718/portfolio/main/public/logos/projects/papermind.svg" width="100%"/></a><br/>
<b>PaperMind</b><br/><sub>RAG arXiv explainer with streaming responses & D3.js knowledge graphs</sub>
</td>
</tr>
</table>

<p align="center"><a href="https://www.abhinavbuilds.online/"><img src="https://img.shields.io/badge/View_more_projects_·_abhinavbuilds.online-8250df?style=flat-square&logo=vercel&logoColor=white" alt="View more projects · abhinavbuilds.online"/></a></p>

---

### 🛠 Tech

<p>
  <img src="https://skillicons.dev/icons?i=python,java,pytorch,tensorflow,sklearn,opencv,fastapi,react,docker,postgres,git&theme=dark" alt="tech stack" />
</p>

<sub>Python · Java · PyTorch · TensorFlow · scikit-learn · OpenCV · LangChain · FastAPI · React/Node · PostgreSQL · Docker · Git</sub>

---

<div align="center">

<img height="150" src="https://github-readme-stats.vercel.app/api?username=kratos0718&show_icons=true&theme=github_dark&include_all_commits=true&count_private=true&hide_border=true"/>
<img height="150" src="https://github-readme-stats.vercel.app/api/top-langs/?username=kratos0718&layout=compact&langs_count=6&theme=github_dark&hide_border=true"/>
<br/>
<img height="150" src="https://github-readme-streak-stats.herokuapp.com/?user=kratos0718&theme=github-dark-blue&hide_border=true&background=0D1117"/>

<br/><br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/kratos0718/kratos0718/output/github-contribution-grid-snake-dark.svg"/>
  <img alt="contribution snake" src="https://raw.githubusercontent.com/kratos0718/kratos0718/output/github-contribution-grid-snake.svg"/>
</picture>

</div>
