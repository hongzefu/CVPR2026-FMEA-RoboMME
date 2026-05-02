# 削减内容对照表（v2 分支正文压缩 → 8 页以内）

下面按 CUT 编号列出每处的「删除前 / 替换后」对照。所有引用的是 LaTeX 源码原文。

---

## CUT-1 ★★★ `sec/1_intro.tex`

**删除前**（原 L25–26）：
```latex
Progress is further limited by the absence of benchmarks that capture diverse and challenging memory requirements.
MemoryBench \cite{fang2025sam2act} is the first benchmark to explicitly evaluate spatial memory, but it contains only three near-solved tasks. MIKASA-Robo \cite{cherepanov2025memory} introduces several history-dependent tasks, yet they remain short-horizon and lack sufficient high-quality demonstrations for effective vision-language-action (VLA) imitation learning. Consequently, existing benchmarks neither capture realistic memory demands nor provide a standardized testbed for systematically evaluating memory-augmented manipulation policies.
```

**替换后**：
```latex
Progress is further limited by the absence of benchmarks that capture diverse and challenging memory requirements: existing benchmarks \cite{fang2025sam2act, cherepanov2025memory} either cover only one memory type or lack sufficient high-quality demonstrations, preventing systematic evaluation of memory-augmented vision-language-action (VLA) policies.
```

**理由**：完整批评在 `2_related_work.tex` L6 已逐字给出，intro 只需一句过渡。

---

## CUT-2 ★★★ `sec/1_intro.tex`

**删除前**（原 L33–37）：
```latex
Differentiable neural representations, including perceptual and recurrent memory, are integrated through three mechanisms:
(1) \textit{memory-as-context}, which appends memory embeddings to the inputs for joint processing;
(2) \textit{memory-as-modulator}, which conditions the action expert via adaptive LayerNorm  \cite{peebles2023scalable} to modulate intermediate activations; and
(3) \textit{memory-as-expert}, which adds a dedicated memory expert that interacts with the action expert through block-wise causal attention \cite{pi0}.
```

**替换后**：
```latex
Differentiable neural representations are integrated through three mechanisms: \textit{memory-as-context}, \textit{memory-as-modulator}, and \textit{memory-as-expert}, with detailed formulations in \cref{sec:method}.
```

**理由**：`4_method.tex` §4.2 与 Fig.3 caption 已完整给出技术细节，intro 不必复述。

---

## CUT-7 ★★ `sec/2_related_work.tex`

**删除前**（原 L18 末句）：
```latex
Despite showing the importance of memory, these approaches vary widely in architecture and evaluation, making systematic comparison difficult. To address this gap, we construct a family of memory-augmented VLA models on the same backbone and evaluate diverse memory representations and integration strategies under a controlled, standardized setting.
```

**替换后**：
```latex
Despite showing the importance of memory, these approaches vary widely in architecture and evaluation, making systematic comparison difficult.
```

**理由**：贡献声明属于 intro（L31–37 已完整陈述），related work 末尾不需重复。

---

## CUT-5 ★★ `sec/3_benchmark.tex`

**删除前**（原 L140–142，§3 开头孤立段落）：
```latex
The aim of \benchname\xspace is to rigorously evaluate history-dependent behavior in robotic manipulation.
All tasks are intentionally constructed to be non-Markovian, requiring models to reason over past observations that are no longer visible at the current step.
Memory is essential for these tasks because identical observations can arise from different histories yet require different actions.
```

**替换后**：直接删除全部 3 句，让 `\subsection{Cognitively-Motivated Task Design}` 紧接上文出现。

**理由**：intro L16–18 + L29 已说明 non-Markovian 必要性，此段为孤立过渡，无新信息。

---

## CUT-9 + CUT-3 ★★★ `sec/3_benchmark.tex`

**删除前**（原 L160–166）：
```latex
These four memory types correspond to the cognitive dimensions of when (temporal), where (spatial), what (object), and how (procedural).
\benchname\xspace is organized around these dimensions into four task suites, \TSone, \TStwo, \TSthree, \TSfour, each emphasizing a primary memory type for controlled evaluation. \cref{fig:teaser} illustrates an overview of \benchname. Specifically, the \TSone\xspace suite targets \textit{temporal memory} by requiring agents to repeat actions a specified number of times, including pick-and-place, linear swinging, and time-critical  tasks.
The \TStwo\xspace suite focuses on \textit{spatial memory}, evaluating object location tracking from pre-recorded videos or during concurrent manipulation.
The \TSthree\xspace suite evaluates \textit{object memory} through persistent identity resolution under visual, action-based, and language-based referential cues.
The \TSfour\xspace suite targets \textit{procedural memory} by requiring agents to reproduce demonstrated motion patterns, such as pushing, inserting, and sequential linear or circular motions.
Together, these suites provide a complementary evaluation of memory-augmented manipulation across diverse memory demands.
\cref{tab:task_overview} summarizes the tasks, with detailed descriptions in \cref{sec:appx_task_desc}.
```

**替换后**：
```latex
\benchname\xspace is organized around these dimensions into four task suites, \TSone, \TStwo, \TSthree, and \TSfour, each emphasizing a primary memory type for controlled evaluation. \cref{fig:teaser} and \cref{tab:task_overview} provide an overview, with detailed descriptions in \cref{sec:appx_task_desc}.
```

**理由**：
- CUT-9：`when/where/what/how` 句是刚刚 4 个 bullet 的修辞性重述，无新信息。
- CUT-3：四个 suite 的描述在 Fig.1 caption (L7–11) 与 Table 1 中已是第二/第三次重复。

---

## CUT-6 ★★ `sec/4_method.tex`

**删除前**（原 L4–6）：
```latex
Building on \benchname, we construct a family of memory-augmented vision-language-action (VLA) models based on the $\pi_{0.5}$ backbone, collectively termed the \textbf{\modelname\xspace suite}.
We systematically compare different memory representations and integration mechanisms under controlled settings, as illustrated in \cref{fig:memory_design}.
More detailed model formulations are provided in \cref{sec:appx_model_design}.
```

**替换后**：
```latex
We construct the \textbf{\modelname\xspace suite} by augmenting $\pi_{0.5}$ with different memory representations and integration mechanisms (\cref{fig:memory_design}); detailed formulations are provided in \cref{sec:appx_model_design}.
```

**理由**：intro L31 已说 "Building on RoboMME, we develop a family of 14 memory-augmented VLA models based on the π0.5 backbone"，逐字重复。

---

## CUT-8 ★ `sec/5_experiment.tex`

**删除前**（原 L4）：
```latex
In this section, we systematically evaluate all \modelname\xspace variants under controlled settings, first outlining the experimental setup and then analyzing the main results.
```

**替换后**：整行删除（直接进入 `\subsection{Experiment Setup}`）。

**理由**：纯模板填充句，节标题已表明内容。

---

## CUT-10 ★ `sec/5_experiment.tex`

**删除前**（原 L43）：
```latex
The main results are summarized in \cref{tab:main}; and complete results are provided in \cref{sec:appx_full_results}. We analyze these results by addressing several key research questions below.
```

**替换后**：
```latex
Main results are summarized in \cref{tab:main} (full results in \cref{sec:appx_full_results}); we analyze them through the questions below.
```

**理由**：两句合并为一句，去掉冗余介绍语气。

---

## CUT-4 ★★★ `sec/6_conclusion.tex`

**删除前**（原 L4）：
```latex
This work introduces \benchname, a unified benchmark for systematically evaluating memory-augmented robotic manipulation across four cognitive dimensions: temporal, spatial, object, and procedural memory. We further develop a family of vision-language-action (VLA) models and conducted controlled comparisons of symbolic, perceptual, and recurrent memory representations with multiple integration mechanisms. Results show that no single design consistently dominates: symbolic memory excels at counting and short-horizon reasoning, while perceptual memory is crucial for motion-centric and time-sensitive behaviors.
```

**替换后**：
```latex
We present \benchname, a unified benchmark spanning four cognitive memory dimensions, together with a family of memory-augmented VLA models on the $\pi_{0.5}$ backbone. Controlled experiments show that memory effectiveness is highly task-dependent, with symbolic and perceptual memory offering complementary strengths.
```

**理由**：与 abstract + intro L38 + experiments Key Takeaways 完全重复，不必再列全部发现。

---

## 削减汇总

| # | 文件 | 原行数 | 新行数 | 净节省 |
|---|------|------|------|------|
| CUT-1 | `1_intro.tex` (MemoryBench/MIKASA 批评) | ~5 | ~2 | ~3 |
| CUT-2 | `1_intro.tex` (三种集成机制) | ~5 | ~2 | ~3 |
| CUT-7 | `2_related_work.tex` (末句贡献声明) | ~2 | 0 | ~2 |
| CUT-5 | `3_benchmark.tex` (§3 开头过渡段) | ~3 | 0 | ~3 |
| CUT-9 + CUT-3 | `3_benchmark.tex` (when/where/what/how + 四个 suite 描述) | ~7 | ~2 | ~5 |
| CUT-6 | `4_method.tex` (§4 开头) | ~3 | ~1 | ~2 |
| CUT-8 | `5_experiment.tex` (§5 模板句) | ~1 | 0 | ~1 |
| CUT-10 | `5_experiment.tex` (主结果过渡句) | ~2 | ~1 | ~1 |
| CUT-4 | `6_conclusion.tex` (首段) | ~4 | ~2 | ~2 |
| **合计** | | | | **~22 行 ≈ 1 列** |

**结果**：正文从越界第 9 页（约 525 行）回缩到第 8 页内，References 从第 8 页右栏开始。
