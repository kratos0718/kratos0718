<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="Abhinav Tarigoppula — AI/ML Engineer · Open-Source Contributor"/>
</p>

<p align="center">
  <i>Final-year B.Tech CSE (AI/ML), GITAM University · Visakhapatnam, India</i>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/abhinav0702/">LinkedIn</a> &nbsp;·&nbsp;
  <a href="https://orcid.org/0009-0005-1542-0221">ORCID</a> &nbsp;·&nbsp;
  <a href="https://www.abhinavbuilds.online/">Portfolio</a> &nbsp;·&nbsp;
  <a href="mailto:abhinaaavvv07187@gmail.com">Email</a>
</p>

---

I build tools that make AI/ML systems more reliable. Most AI demos are slick; most AI in production is messy — I like working in that gap, close enough to the real problem to build something that doesn't fall apart outside a notebook. Author of [codehound](https://github.com/kratos0718/codehound), **14 PRs merged** into major AI frameworks, and a computer-vision research intern.

<table>
<tr>
<td valign="top" width="52%">

**Currently**

- 🔭 CV research intern @ **APEPDCL** — YOLOv8 + MiDaS defect detection for a state power utility
- 🐕 building **codehound** — a static analyzer that finds real bugs in AI codebases
- 📄 co-authoring research (ML for education, AI proctoring) — under review / preprint
- 🌱 learning: LoRA/PEFT fine-tuning, vision-language models
- 🎯 targeting AI/ML research roles & a funded MS

</td>
<td valign="top">

**At a glance**

```text
Merged PRs   14  ·  18+ orgs
Flagship     codehound (AST analyzer)
Bug classes  async-blocking, task GC,
             resource leaks, B006
Research     3 papers (IEEE, under review)
Stack        Python · PyTorch · CV · LLMs
```

</td>
</tr>
</table>

---

### 🐕 codehound — [github.com/kratos0718/codehound](https://github.com/kratos0718/codehound)

An AST-based Python static analyzer — **~750 LOC, zero dependencies, CI on Python 3.9–3.12.** It detects six real bug classes: event-loop-blocking calls inside `async` functions, fire-and-forget tasks that can be garbage-collected mid-run, mutable default arguments, unclosed file handles, and deprecated event-loop APIs. Several of the merged fixes below were surfaced by it.

---

### 🔧 Open-source contributions

Real bug fixes across widely-used AI/ML repositories. One change shipped in a HuggingFace production release; one came from a founder's invitation to contribute (Future AGI).

<table>
<tr>
<td valign="top" width="150" align="center">
<img src="https://github.com/unslothai.png" width="34"/><br/>
<b>unsloth</b><br/><sub>40k⭐</sub>
</td>
<td valign="top">
Blocking <code>time.sleep</code> (up to 30s) freezing the async event loop in the model-export route — <b>found by codehound</b>.<br/>
<a href="https://github.com/unslothai/unsloth/pull/6135">#6135</a> · <b>merged</b>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/pydantic.png" width="34"/><br/>
<b>pydantic-ai</b><br/><sub>11k⭐</sub>
</td>
<td valign="top">
Shared mutable-default <code>deque</code> in <code>process_tool_calls</code> leaking one run's result into the next — <b>found by codehound</b>. Merged same day.<br/>
<a href="https://github.com/pydantic/pydantic-ai/pull/6189">#6189</a> · <b>merged</b>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/prowler-cloud.png" width="34"/><br/>
<b>prowler</b><br/><sub>14k⭐</sub>
</td>
<td valign="top">
Azure Flexible Server check reading log-retention from the wrong config key, with a regression test. Merged by a maintainer.<br/>
<a href="https://github.com/prowler-cloud/prowler/pull/11761">#11761</a> · <b>merged</b>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/agno-agi.png" width="34"/><br/>
<b>agno</b><br/><sub>25k⭐</sub>
</td>
<td valign="top">
Blocking <code>time.sleep</code> / <code>requests.get</code> in async, plus a file-handle leak in <code>transcribe_audio</code>. Discord-handler bug <b>found by codehound</b>.<br/>
<a href="https://github.com/agno-agi/agno/pull/8158">#8158</a> · <a href="https://github.com/agno-agi/agno/pull/8186">#8186</a> · <a href="https://github.com/agno-agi/agno/pull/8161">#8161</a> · <a href="https://github.com/agno-agi/agno/pull/8138">#8138</a> · <b>merged</b>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/mem0ai.png" width="34"/><br/>
<b>mem0</b><br/><sub>35k⭐</sub>
</td>
<td valign="top">
Mutable default arguments (B006) in <code>Completions.create</code> and <code>BaseEmbedderConfig</code>, with a regression test.<br/>
<a href="https://github.com/mem0ai/mem0/pull/5302">#5302</a> · <b>merged</b>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/huggingface.png" width="34"/><br/>
<b>HuggingFace</b><br/><sub>hub · accelerate · peft</sub>
</td>
<td valign="top">
Documented undocumented public-API parameters. The hub change <b>shipped in release v1.17.0</b> — live on PyPI.<br/>
<a href="https://github.com/huggingface/huggingface_hub/pull/4289">hub #4289</a> · <a href="https://github.com/huggingface/accelerate/pull/4051">accelerate #4051</a> · <b>merged</b>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/marimo-team.png" width="34"/><br/>
<b>marimo</b><br/><sub>11k⭐ · YC</sub>
</td>
<td valign="top">
Shipped a <b>new public-API feature</b> — a <code>filter</code> argument on <code>mo.ui.file_browser()</code>.<br/>
<a href="https://github.com/marimo-team/marimo/pull/9667">#9667</a> · <b>merged</b>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/vllm-project.png" width="34"/><br/>
<b>vLLM · autogen</b><br/><sub>Weaviate · Future AGI</sub>
</td>
<td valign="top">
Open PRs: fire-and-forget <code>asyncio</code> tasks at <b>vLLM</b> and <b>Microsoft autogen</b>; blocking sleep in an async retry loop at <b>Weaviate</b>; background-task tracking at <b>Future AGI</b> (founder invite). <b>Found by codehound</b>.<br/>
<a href="https://github.com/vllm-project/vllm/pull/45249">vllm #45249</a> · <a href="https://github.com/microsoft/autogen/pull/7825">autogen #7825</a> · <a href="https://github.com/weaviate/weaviate-python-client/pull/2104">weaviate #2104</a> · <i>under review</i>
</td>
</tr>
</table>

<sub><b>14 PRs merged</b> · <b>18+ organizations</b> · classes: event-loop blocking, fire-and-forget tasks, resource leaks, mutable defaults.</sub>

---

### 📄 Research

Co-authored with Dr. Chandrakanta Mahanty (GITAM). *(Full list: [ORCID](https://orcid.org/0009-0005-1542-0221) · [ResearchGate](https://www.researchgate.net/profile/Abhinav-Tarigoppula))*

- **Student-Performance Prediction with Ensemble Methods & XAI** — *submitted, IEEE ISED 2026 (NIT Warangal)* · first author
- **Behavior-Driven Adaptive Learning Agents for Personalized Education** — *under review, IEEE*
- **HAPS: Hybrid AI Proctoring (dual-stream CNNs + YOLO)** — *preprint*

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

<p align="center"><sub>More at <a href="https://www.abhinavbuilds.online/">abhinavbuilds.online</a></sub></p>

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

<br/><br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/kratos0718/kratos0718/output/github-contribution-grid-snake-dark.svg"/>
  <img alt="contribution snake" src="https://raw.githubusercontent.com/kratos0718/kratos0718/output/github-contribution-grid-snake.svg"/>
</picture>

</div>
