<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="Abhinav Tarigoppula — AI/ML Engineer · Open-Source Contributor"/>
</p>

<p align="center">
  <i>Final-year B.Tech CSE (AI/ML), GITAM University · Visakhapatnam, India</i>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/abhinav0702/">LinkedIn</a> &nbsp;·&nbsp;
  <a href="https://www.researchgate.net/profile/Abhinav-Tarigoppula">ResearchGate</a> &nbsp;·&nbsp;
  <a href="https://www.abhinavbuilds.online/">Portfolio</a> &nbsp;·&nbsp;
  <a href="mailto:abhinaaavvv07187@gmail.com">Email</a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=kratos0718&label=profile%20views&style=flat-square&color=2dd4bf&labelColor=0d1117" alt="profile views"/>
  &nbsp;
  <a href="https://www.researchgate.net/profile/Abhinav-Tarigoppula"><img src="https://img.shields.io/badge/IEEE_ISED_2026-accepted-1f6feb?style=flat-square&labelColor=0d1117" alt="IEEE ISED 2026 accepted"/></a>
  &nbsp;
  <a href="https://github.com/search?q=is%3Apr+author%3Akratos0718+is%3Amerged&type=pullrequests"><img src="https://img.shields.io/badge/merged_PRs-17-2dd4bf?style=flat-square&labelColor=0d1117" alt="17 merged PRs"/></a>
</p>

---

I build tools that make AI/ML systems more reliable. Most AI demos are slick; most AI in production is messy — I like working in that gap, close enough to the real problem to build something that doesn't fall apart outside a notebook. Author of [codehound](https://github.com/kratos0718/codehound), **17 PRs merged** into major AI frameworks with a combined 300k+ stars.

<table>
<tr>
<td valign="top" width="52%">

**Currently**

- 🔭 built **DocGuard-VLM** — QLoRA fine-tuned Qwen2-VL for document extraction + forgery detection
- 🐕 building **codehound** — a static analyzer that finds real bugs in AI codebases
- 📄 co-author paper **accepted at IEEE ISED 2026**, NIT Warangal
- 🌱 learning: LoRA/PEFT fine-tuning, vision-language models
- 🎯 targeting AI/ML research roles & a funded MS

</td>
<td valign="top">

**At a glance**

```text
Merged PRs   17  ·  11 orgs  ·  300k+ ⭐
Flagship     codehound (AST analyzer)
Bug classes  async-blocking, task GC,
             resource leaks, B006
Research     accepted @ IEEE ISED 2026
Stack        Python · Java · PyTorch · LLMs
```

</td>
</tr>
</table>

---

### 🐕 codehound — [github.com/kratos0718/codehound](https://github.com/kratos0718/codehound)

An AST-based Python static analyzer — **~750 LOC, zero dependencies, CI on Python 3.9–3.12.** It detects six real bug classes: event-loop-blocking calls inside `async` functions, fire-and-forget tasks that can be garbage-collected mid-run, mutable default arguments, unclosed file handles, and deprecated event-loop APIs. Several of the merged fixes below were surfaced by it.

<a href="https://github.com/kratos0718/codehound"><img src="https://img.shields.io/badge/View_repository-24292f?style=flat-square&logo=github&logoColor=white" alt="View repository"/></a>

---

### 🔧 Open-source contributions

Real bug fixes across widely-used AI/ML repositories. One change shipped in a HuggingFace production release; one came from a founder's invitation to contribute (Future AGI).

<p align="center">
  <img src="https://img.shields.io/badge/Merged_PRs-17-1a7f37?style=for-the-badge&logo=git&logoColor=white" alt="17 merged PRs"/>
  <img src="https://img.shields.io/badge/Organizations-11-0969da?style=for-the-badge&logo=github&logoColor=white" alt="11 organizations"/>
  <img src="https://img.shields.io/badge/Combined_stars-300k+-e3b341?style=for-the-badge&logo=starship&logoColor=white" alt="300k+ combined stars"/>
  <img src="https://img.shields.io/badge/Shipped_in-huggingface__hub_v1.17.0-ffce3a?style=for-the-badge&logo=huggingface&logoColor=black" alt="shipped in huggingface_hub v1.17.0"/>
</p>

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
<img src="https://github.com/unslothai.png" width="34"/><br/>
<b>unsloth</b><br/><sub>69k⭐</sub>
</td>
<td valign="top">
Blocking <code>time.sleep</code> (up to 30s) freezing the async event loop in the model-export route — <b>found by codehound</b>.<br/>
<a href="https://github.com/unslothai/unsloth/pull/6135">#6135</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/pydantic.png" width="34"/><br/>
<b>pydantic-ai</b><br/><sub>18k⭐</sub>
</td>
<td valign="top">
Shared mutable-default <code>deque</code> in <code>process_tool_calls</code> leaking one run's result into the next — <b>found by codehound</b>. Merged same day.<br/>
<a href="https://github.com/pydantic/pydantic-ai/pull/6189">#6189</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/prowler-cloud.png" width="34"/><br/>
<b>prowler</b><br/><sub>14k⭐</sub>
</td>
<td valign="top">
Azure Flexible Server check reading log-retention from the wrong config key, with a regression test. Merged by a maintainer.<br/>
<a href="https://github.com/prowler-cloud/prowler/pull/11761">#11761</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/agno-agi.png" width="34"/><br/>
<b>agno</b><br/><sub>41k⭐</sub>
</td>
<td valign="top">
Blocking <code>time.sleep</code> / <code>requests.get</code> in async, plus a file-handle leak in <code>transcribe_audio</code>. Discord-handler bug <b>found by codehound</b>.<br/>
<a href="https://github.com/agno-agi/agno/pull/8158">#8158</a> · <a href="https://github.com/agno-agi/agno/pull/8186">#8186</a> · <a href="https://github.com/agno-agi/agno/pull/8161">#8161</a> · <a href="https://github.com/agno-agi/agno/pull/8138">#8138</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/mem0ai.png" width="34"/><br/>
<b>mem0</b><br/><sub>62k⭐</sub>
</td>
<td valign="top">
Mutable default arguments (B006) in <code>Completions.create</code> and <code>BaseEmbedderConfig</code>, with a regression test.<br/>
<a href="https://github.com/mem0ai/mem0/pull/5302">#5302</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/huggingface.png" width="34"/><br/>
<b>HuggingFace</b><br/><sub>hub · accelerate · peft</sub>
</td>
<td valign="top">
Documented undocumented public-API parameters. The hub change <b>shipped in release v1.17.0</b> — live on PyPI.<br/>
<a href="https://github.com/huggingface/huggingface_hub/pull/4289">hub #4289</a> · <a href="https://github.com/huggingface/accelerate/pull/4051">accelerate #4051</a> · <a href="https://github.com/huggingface/peft/pull/3271">peft #3271</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/marimo-team.png" width="34"/><br/>
<b>marimo</b><br/><sub>22k⭐ · YC</sub>
</td>
<td valign="top">
Shipped a <b>new public-API feature</b> — a <code>filter</code> argument on <code>mo.ui.file_browser()</code>.<br/>
<a href="https://github.com/marimo-team/marimo/pull/9667">#9667</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/weaviate.png" width="34"/><br/>
<b>Weaviate · Xorbits</b><br/><sub>vector DB · inference</sub>
</td>
<td valign="top">
Blocking <code>time.sleep</code> in async <code>wait_for_weaviate</code> — <b>found by codehound</b>, merged by a maintainer. Same bug class fixed at <b>Xorbits</b>.<br/>
<a href="https://github.com/weaviate/weaviate-python-client/pull/2104">weaviate #2104</a> · <a href="https://github.com/xorbitsai/inference/pull/5055">xinference #5055</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
<tr>
<td valign="top" align="center">
<img src="https://github.com/apache.png" width="34"/><br/>
<b>Apache Maven · Mercari</b><br/><sub>Java · build &amp; data</sub>
</td>
<td valign="top">
Test asserting on the wrong path so it could not fail, in the Maven source plugin. At <b>Mercari</b>, Avro <code>timestamp-micros</code> truncated to milliseconds on the JDBC path, silently losing sub-millisecond data.<br/>
<a href="https://github.com/apache/maven-source-plugin/pull/318">maven-source-plugin #318</a> · <a href="https://github.com/mercari/pipeline/pull/119">pipeline #119</a> · <img src="https://img.shields.io/badge/merged-1a7f37?style=flat-square&logo=github&logoColor=white" alt="merged"/>
</td>
</tr>
</table>

<sub><b>17 PRs merged</b> · <b>11 organizations</b> · <b>300k+ combined stars</b> — all reviewed and merged by core maintainers.</sub>

<p>
  <a href="https://github.com/search?q=is%3Apr+author%3Akratos0718+is%3Amerged&type=pullrequests"><img src="https://img.shields.io/badge/View_all_17_merged_PRs-1a7f37?style=flat-square&logo=github&logoColor=white" alt="View all 17 merged PRs"/></a>
  <a href="https://github.com/search?q=is%3Apr+author%3Akratos0718+is%3Aopen&type=pullrequests"><img src="https://img.shields.io/badge/View_open_PRs-0969da?style=flat-square&logo=github&logoColor=white" alt="View open PRs"/></a>
</p>

**Currently under review** — beyond Python/AI, into new languages and domains:

<p>
  <a href="https://github.com/lextudio/pysnmp/pull/248"><img src="https://img.shields.io/badge/pysnmp-SNMP_index_decoding-3572A5?style=flat-square&logo=python&logoColor=white" alt="pysnmp"/></a>
  <a href="https://github.com/vllm-project/vllm/pull/45249"><img src="https://img.shields.io/badge/vLLM-87k⭐-000000?style=flat-square" alt="vllm"/></a>
  <a href="https://github.com/microsoft/autogen/pull/7825"><img src="https://img.shields.io/badge/Microsoft_autogen-60k⭐-0078D4?style=flat-square&logo=microsoft&logoColor=white" alt="autogen"/></a>
  <a href="https://github.com/BerriAI/litellm/pull/34711"><img src="https://img.shields.io/badge/litellm-55k⭐-1a7f37?style=flat-square" alt="litellm"/></a>
  <a href="https://github.com/dask/dask/pull/12482"><img src="https://img.shields.io/badge/Dask-13k⭐-FDA061?style=flat-square&logo=dask&logoColor=black" alt="dask"/></a>
  <a href="https://github.com/agentscope-ai/agentscope-java/pull/2543"><img src="https://img.shields.io/badge/AgentScope_Java-4.8k⭐-b07219?style=flat-square&logo=openjdk&logoColor=white" alt="agentscope-java"/></a>
</p>

---

### 📄 Research

Co-authored with Dr. Chandrakanta Mahanty (GITAM). *(Full list on [ResearchGate](https://www.researchgate.net/profile/Abhinav-Tarigoppula))*

- **Machine Learning-Based Student Performance Prediction: A Comparative Study Using Ensemble Methods and Explainable AI**
  <br/><img src="https://img.shields.io/badge/accepted-1a7f37?style=flat-square" alt="accepted"/> 14th International Conference on Intelligent Systems and Embedded Design (**ISED 2026**), NIT Warangal · Publisher: **IEEE**
- **Behavior-Driven Adaptive Learning Agents for Personalized Education** — *under review, IEEE*
- **HAPS: Hybrid AI Proctoring (dual-stream CNNs + YOLO)** — *preprint*

<a href="https://www.researchgate.net/profile/Abhinav-Tarigoppula"><img src="https://img.shields.io/badge/View_full_publication_list-00CCBB?style=flat-square&logo=researchgate&logoColor=white" alt="View full publication list"/></a>

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

<br/><br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/kratos0718/kratos0718/output/github-contribution-grid-snake-dark.svg"/>
  <img alt="contribution snake" src="https://raw.githubusercontent.com/kratos0718/kratos0718/output/github-contribution-grid-snake.svg"/>
</picture>

</div>
