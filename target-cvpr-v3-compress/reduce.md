# 现存的缩减版面命令清单

> 扫描时间：基于 `target-cvpr-v2` 仓库的最新文件状态。
> 范围：所有当前**生效**（未被注释）的、用于压缩页面占用或视觉密度的命令。
> 已注释/已废弃的命令单列在文末"已禁用"一节，便于回溯。

`cvpr.sty` 与 `cvpr-ref` 字节级一致（未做任何修改），所有缩减都来自 `preamble.tex`、正文 `sec/*.tex`、`tables/*.tex` 与附录 `sec/appx/*.tex`。

---

## 一、正文（main 论文）

### 1. preamble.tex（全局生效）

| # | 文件:行 | 命令 | 作用 |
|---|---|---|---|
| P1 | [preamble.tex:21](preamble.tex:21) | `\usepackage{microtype}` | 字符级微调（突出/扩张/压缩），唯一具有"省地"效果的全局开关 |
| P2 | [preamble.tex:63–64](preamble.tex:63) | `\setlength{\dashlinedash}{2pt}` / `\setlength{\dashlinegap}{2pt}` | arydshln 虚线节奏压紧（视觉密度，非省地） |
| P3 | [preamble.tex:71](preamble.tex:71) | `\newcommand{\pmstd}[1]{\scriptsize{...}}` | ±std 数值用 `\scriptsize` 行内插入（主表数字行变小） |
| P4 | [preamble.tex:115](preamble.tex:115) | `basicstyle=\ttfamily\footnotesize`（lstdefinelanguage json） | JSON 代码段字号 footnotesize |
| P5 | [preamble.tex:120–128](preamble.tex:120) | `\lstset{ aboveskip=0pt, belowskip=0pt, frame=none, xleftmargin=0pt, ... }` | 全局 lstlisting 紧贴上下文，无边框无左边距 |

**未启用但保留**：[preamble.tex:164–170](preamble.tex:164) 全局浮动间距（`\textfloatsep` 等）与 `\captionsetup` 已被注释；[preamble.tex:174](preamble.tex:174) `\raggedbottom` 仍被注释（保持 `\flushbottom`）。

### 2. sec/3_benchmark.tex

| # | 行 | 命令 | 作用 |
|---|---|---|---|
| B1 | [6](sec/3_benchmark.tex:6) | `\small` | 表 `tab:task_overview` 整表字号小一档 |
| B2 | [7](sec/3_benchmark.tex:7) | `\setlength{\tabcolsep}{3pt}` | 列间距压缩（默认 6pt） |
| B3 | [8](sec/3_benchmark.tex:8) | `\renewcommand{\arraystretch}{1.15}` | 行高 1.15×（轻度放松，配合 small 平衡可读性） |
| B4 | [10](sec/3_benchmark.tex:10) | `\resizebox{\textwidth}{!}{...}` | 表内容横向缩放至栏宽 |
| B5 | [14](sec/3_benchmark.tex:14) | `\hspace*{-10pt}` × 2（表头 "Memory/Type"） | 表头硬负偏移 10pt 拉近左侧 |
| B6 | [100](sec/3_benchmark.tex:100) | `\small` | 表 `tab:dataset_comparison` 字号 |
| B7 | [101](sec/3_benchmark.tex:101) | `\setlength{\tabcolsep}{3.5pt}` | 列间距压缩 |
| B8 | [102](sec/3_benchmark.tex:102) | `\resizebox{\textwidth}{!}{...}` | 横向缩放 |
| B9 | [148](sec/3_benchmark.tex:148) | `\begin{itemize}[itemsep=1pt, topsep=0pt, leftmargin=*]` | 四个 memory type 列表紧凑 |
| B10 | [191](sec/3_benchmark.tex:191) | `{\interfootnotelinepenalty=10000\relax ... \par}` | 防止该段及其脚注被分页/分栏断开（含 MIKASA 脚注） |

### 3. sec/5_experiment.tex

| # | 行 | 命令 | 作用 |
|---|---|---|---|
| E1 | [68](sec/5_experiment.tex:68) | `\includegraphics[width=0.92\linewidth, trim=0 6pt 0 6pt, clip]` | `task_memory_correspondence.pdf` 缩到 92% 并裁剪上下各 6pt 白边 |
| E2 | [71](sec/5_experiment.tex:71) | `\vspace{-4pt}` | 紧接 caption 后向上拉 4pt |
| E3 | [87](sec/5_experiment.tex:87) | `\includegraphics[width=\linewidth, trim=0 4pt 0 4pt, clip]` | `flops_compare.pdf` 上下各裁 4pt 白边 |
| E4 | [90](sec/5_experiment.tex:90) | `\vspace{-4pt}` | caption 后向上拉 4pt |

### 4. tables/main_table.tex（被 sec/5_experiment.tex `\input`）

| # | 行 | 命令 | 作用 |
|---|---|---|---|
| T1 | [257](tables/main_table.tex:257) | `\setlength{\tabcolsep}{2.0pt}` | 17 列主表的极窄列间距（默认 6pt） |
| T2 | [259](tables/main_table.tex:259) | `\resizebox{\textwidth}{!}{%...}` | 表内容横向强制缩放至 `\textwidth` |

---

## 二、附录（supplementary）

### 5. tables/appendix_main_table.tex

| # | 行 | 命令 | 作用 |
|---|---|---|---|
| AT1 | [8](tables/appendix_main_table.tex:8) | `\scriptsize` | 整表字号 scriptsize（约 7pt） |
| AT2 | [9](tables/appendix_main_table.tex:9) | `\setlength{\tabcolsep}{3.5pt}` | 列间距 |
| AT3 | [10](tables/appendix_main_table.tex:10) | `\renewcommand{\arraystretch}{1.15}` | 行高 |
| AT4 | [11](tables/appendix_main_table.tex:11) | `\resizebox{\textwidth}{!}{%...}` | 横向缩放 |

### 6. tables/task_requirement_model_compasion.tex

| # | 行 | 命令 | 作用 |
|---|---|---|---|
| AT5 | [79](tables/task_requirement_model_compasion.tex:79) | `\resizebox{0.9\linewidth}{!}{...}` | 横向缩放至 90% 栏宽 |

### 7. sec/appx/appx_full_result.tex

| # | 行 | 命令 | 作用 |
|---|---|---|---|
| A1 | [24](sec/appx/appx_full_result.tex:24) | `\setlength{\tabcolsep}{2.0pt}` | 列间距极窄 |
| A2 | [26](sec/appx/appx_full_result.tex:26) | `\resizebox{\textwidth}{!}{%...}` | 横向缩放 |
| A3 | [101](sec/appx/appx_full_result.tex:101) | `\small` | 字号 |
| A4 | [104](sec/appx/appx_full_result.tex:104) | `\renewcommand{\arraystretch}{2.25}` | 行高 2.25×（**反向放松**，可能为容纳两行内容） |
| A5 | [105](sec/appx/appx_full_result.tex:105) | `\scalebox{1.0}{...}` | 当前 1.0 无效果（占位） |

### 8. sec/appx/appx_imp_detail.tex

| # | 行 | 命令 | 作用 |
|---|---|---|---|
| A6 | [30](sec/appx/appx_imp_detail.tex:30) | `\small` | 局部小字号块 |
| A7 | [67](sec/appx/appx_imp_detail.tex:67) | `\small` | 同上 |
| A8 | [263](sec/appx/appx_imp_detail.tex:263) | `\begin{lstlisting}[basicstyle=\ttfamily\footnotesize]` | 代码段 footnotesize |
| A9 | [297](sec/appx/appx_imp_detail.tex:297) | `\small` | 局部小字号块 |

### 9. sec/appx/appx_real_robot.tex

| # | 行 | 命令 | 作用 |
|---|---|---|---|
| A10 | [41](sec/appx/appx_real_robot.tex:41) | `\setlength{\tabcolsep}{4pt}` | 列间距 |
| A11 | [42](sec/appx/appx_real_robot.tex:42) | `\renewcommand{\arraystretch}{0.95}` | 行高 0.95×（**真正压缩行间距**） |
| A12 | [43](sec/appx/appx_real_robot.tex:43) | `\small` | 字号 |

### 10. sec/appx/appx_task_desc.tex（同一模式重复 14 处）

每个任务描述表（共 ~14 个）都遵循相同结构：
```latex
\renewcommand{\arraystretch}{1.2}
\resizebox{\linewidth}{!}{ ... }
```
出现位置：[54–55](sec/appx/appx_task_desc.tex:54)、[119–120](sec/appx/appx_task_desc.tex:119)、[183–184](sec/appx/appx_task_desc.tex:183)、[245–246](sec/appx/appx_task_desc.tex:245)、[299–300](sec/appx/appx_task_desc.tex:299)、[363–364](sec/appx/appx_task_desc.tex:363)、[429–430](sec/appx/appx_task_desc.tex:429)、[494–495](sec/appx/appx_task_desc.tex:494)、[553–554](sec/appx/appx_task_desc.tex:553)、[609–610](sec/appx/appx_task_desc.tex:609)、[665–666](sec/appx/appx_task_desc.tex:665)、[718–719](sec/appx/appx_task_desc.tex:718)、[845–846](sec/appx/appx_task_desc.tex:845)（最后一个 `\resizebox{0.8\linewidth}`）、[911](sec/appx/appx_task_desc.tex:911)

部分图也用了 0.6/0.8/0.85/0.9 的非满栏宽度（[202](sec/appx/appx_task_desc.tex:202)、[138](sec/appx/appx_task_desc.tex:138)、[769/806/862](sec/appx/appx_task_desc.tex:769) 等）——属于内容驱动而非省地。

---

## 三、已禁用 / 已注释的紧缩命令（仅供参考）

> 这些曾启用过、现已关闭。恢复前请先了解关闭原因。

| 文件:行 | 命令 | 关闭原因 |
|---|---|---|
| [preamble.tex:164–168](preamble.tex:164) | `\textfloatsep / \dbltextfloatsep / \floatsep / \dblfloatsep / \intextsep = 4pt plus 1pt minus 1pt` | 与 `\flushbottom` 冲突 → 第 2 页左栏出现"巨大空洞" |
| [preamble.tex:169–170](preamble.tex:169) | `\captionsetup{aboveskip=2pt,belowskip=0pt}` 与 `[sub]` 同款 | 覆盖 cvpr.sty 官方 caption 间距，子图标题贴边 |
| [preamble.tex:174](preamble.tex:174) | `\raggedbottom` | 关闭可缓解上述空洞，但破坏双栏 facing-page 对齐 |
| [sec/5_experiment.tex:35](sec/5_experiment.tex:35) | `\begin{itemize}[leftmargin=*,itemsep=4pt,topsep=0pt]` | cvpr.sty 默认已 `noitemsep`；`itemsep=4pt` 反而放松 → 已注释，回归默认 |
| [sec/3_benchmark.tex:202](sec/3_benchmark.tex:202) | `\enlargethispage{2\baselineskip}` | 不再需要（页面已平衡） |
| [sec/3_benchmark.tex:203–207](sec/3_benchmark.tex:203) | 旧版 `interfootnotelinepenalty` 块（重复） | 已挪到 [191](sec/3_benchmark.tex:191) 生效位置 |
| [sec/appx/appx_task_desc.tex:440](sec/appx/appx_task_desc.tex:440) | `\vspace{-0.5cm}` | 单点视觉调整，已废 |
| [sec/appx/appx_full_result.tex:23](sec/appx/appx_full_result.tex:23) | `\scriptsize` | 改用 `\small` |
| [tables/main_table.tex:13–16, 256](tables/main_table.tex:13) | `\scriptsize`（旧版本） | 已删除，主表保留 normalsize |

---

## 四、机制总览（按"省地强度"排序）

| 强度 | 机制类型 | 主要出现位置 |
|---|---|---|
| ★★★ | `\resizebox{\textwidth}{!}` 横向缩放 | 主表、附表、所有 task 描述表 |
| ★★★ | 字号缩小（`\scriptsize` / `\small` / `\footnotesize`） | appendix_main_table、appx_imp_detail、appx_real_robot、3_benchmark 两表 |
| ★★ | `\setlength{\tabcolsep}{2.0pt~3.5pt}` | main_table、appendix_main_table、3_benchmark、appx_full_result |
| ★★ | `microtype`（全局字符微调） | preamble |
| ★ | `\vspace{-4pt}` 局部贴合 | sec/5_experiment.tex × 2 |
| ★ | `\arraystretch{0.95}` 行高压缩 | appx_real_robot 唯一一处真正向下压 |
| ★ | `itemize[itemsep=1pt, topsep=0pt]` | sec/3_benchmark.tex × 1 |
| ★ | `\hspace*{-10pt}` 表头硬负偏移 | sec/3_benchmark.tex |
| ★ | `\interfootnotelinepenalty=10000` | sec/3_benchmark.tex |
| ★ | `lstset aboveskip=0pt/belowskip=0pt` | preamble（影响所有代码段） |
| ★ | `trim=0 Npt 0 Npt, clip` 裁剪图边白 | sec/5_experiment.tex × 2 |

---

## 五、当前未使用但 cvpr.sty 已定义的紧凑设置（无需补）

- `cvpr.sty:38` `\setlength{\bibsep}{1pt plus 1pt minus 1pt}` — 参考文献间距已紧凑
- `cvpr.sty:49` caption `font=small, skip=3pt` — 主图 caption 字号已小一档
- `cvpr.sty:50` subcaption `font=footnotesize, skip=3pt` — 子图更小
- `cvpr.sty:507–508` `\setlist[itemize/enumerate]{noitemsep, leftmargin=*, topsep=0em}` — 列表已默认无间距
- `cvpr.sty:450/453` `\floatpagefraction=0.99 / \dblfloatpagefraction=0.99` — 浮动页利用率已设最高
