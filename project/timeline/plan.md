# Implementation Plan: Research Timeline Chart

## Overview

Create a LaTeX-based research timeline chart documenting work from November 2024 to January 2026, compile to PDF, and push to repository.

---

## 1. Content Analysis

### Time Range
- **Start**: November 2024
- **End**: January 2026
- **Total Duration**: 15 months

### Entry Density by Month
| Period | Number of Items |
|--------|-----------------|
| 2024.11–2025.1 | 1 |
| 2025.2–2025.3 | 3 |
| 2025.4 | 3 |
| 2025.5 | 4 |
| 2025.6 | 5 |
| 2025.7 | 3 |
| 2025.8 | 4 |
| 2025.9 | 4 |
| 2025.10 | 2 |
| 2025.11 | 5 |
| 2025.12 | 4 |
| 2026.1 | 5 |

### Content Categories
1. **Technical Optimization** (primary focus)
   - Kernel splitting (10% speedup)
   - INT8 MLP replacement (186% speedup, accuracy degradation)
   - Multi-event batching (93% speedup, no loss)
   - Conditional Jacobian aggregation (18% speedup)

2. **Environment/Tooling**
   - traccc environment setup
   - Nsight Systems setup
   - Nsight Compute setup (with noted difficulties)

3. **Conferences & Papers**
   - YunChen's paper revisions
   - VLSICAD 2025 (submission, oral, attendance)
   - TJCAS (submission, oral, poster, attendance)
   - FastML (poster, attendance)

4. **Ongoing Work**
   - NCU Profile Flow Optimization (2025.9 → 2026.1, continuous)

5. **Other**
   - Weak Lensing competition
   - Coursework

### Special Elements
- **Ongoing bar**: "NCU Profile Flow Optimization" spans 2025.9–2026.1 and must be visually represented as a continuous element
- **Metrics highlighting**: Speedup percentages should be visually emphasized
- **Accuracy notes**: Some optimizations had accuracy trade-offs (should be indicated)

---

## 2. LaTeX Approach

### Recommended Package: TikZ (Custom Timeline)

**Rationale**:
- Full control over positioning and styling
- Can handle variable-density entries
- Supports continuous bars for ongoing work
- Professional appearance
- No external dependencies beyond standard TikZ

### Alternative Considered: `pgfgantt`
- Better for Gantt-style charts
- More verbose syntax
- Harder to customize text-heavy entries

### Visual Design

```
Layout: Vertical timeline (top-to-bottom, chronological)

         [Date]  ●━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
                 │  • Item 1
                 │  • Item 2
                 │
         [Date]  ●━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
                 │  • Item 1
                 │
        ...

    [Ongoing bar for NCU work shown as parallel colored stripe]
```

### Color Scheme
| Category | Color |
|----------|-------|
| Timeline spine | Dark gray |
| Date nodes | Blue |
| Optimization achievements | Green |
| Conferences | Orange |
| Ongoing work bar | Light blue (semi-transparent) |
| Accuracy warnings | Red text |

### Typography
- **Document class**: `article` or `standalone`
- **Font**: Default LaTeX (Computer Modern) or `helvet` for sans-serif
- **Date format**: YYYY.MM (as in source document)

---

## 3. File Structure

```
/home/noah/project/timeline/
├── README.md          (existing)
├── request.md         (existing, source requirements)
├── plan.md            (this file)
├── timeline.tex       (to create)
└── timeline.pdf       (to generate)
```

---

## 4. Implementation Steps

### Step 1: Verify LaTeX Environment
```bash
which pdflatex
pdflatex --version
```
- Confirm `pdflatex` is available
- Check for TikZ package availability

### Step 2: Create `timeline.tex`

Structure:
```latex
\documentclass[a4paper,11pt]{article}

% Packages
\usepackage[margin=1in]{geometry}
\usepackage{tikz}
\usetikzlibrary{positioning, calc, backgrounds}
\usepackage{xcolor}
\usepackage{fontenc}

% Color definitions
% ...

% Document
\begin{document}
\begin{tikzpicture}[...]
  % Timeline spine
  % Date nodes and entries
  % Ongoing work bar
\end{tikzpicture}
\end{document}
```

### Step 3: Content Mapping

Each timeline entry maps to:
```latex
\node[date] at (0, -Y) {YYYY.MM};
\node[entry, anchor=west] at (1, -Y) {
  \begin{itemize}
    \item Entry text
  \end{itemize}
};
```

### Step 4: Compile to PDF
```bash
cd /home/noah/project/timeline
pdflatex timeline.tex
```
- May need to run twice for proper positioning
- Check for errors in `.log` file

### Step 5: Git Commit and Push
```bash
git add timeline.tex timeline.pdf
git commit -m "Add research timeline chart"
git push origin main
```

---

## 5. Content Transcript (for LaTeX)

### 2024.11 – 2025.1
- Established the traccc environment

### 2025.2 – 2025.3
- Studied traccc code and algorithms (over 70,000 lines)
- Analyzed next steps and reported to the European team
- Revised the manuscript for YunChen's paper

### 2025.4
- Set up the Nvidia Nsight Systems environment
- Profiled traccc to identify bottlenecks
- Created figures for YunChen's paper

### 2025.5
- Analyzed bottlenecks
- Attempted code modifications and debugging
- Split the fit kernel, increasing throughput by **10%**
- Assisted YunChen with the VLSICAD submission

### 2025.6
- Replaced Kalman gain matrix operations with INT8 MLP
- Achieved **186% speedup** but observed physics accuracy degradation
- Reported results to the European team
- Assisted YunChen with the TJCAS submission
- Attempted to set up Nvidia Nsight Compute environment (encountered severe environmental issues)

### 2025.7
- Prepared slides and English/Chinese scripts for YunChen's VLSICAD 2025 oral presentation
- Prepared slides and scripts for the TJCAS oral presentation
- Successfully established the Nvidia Nsight Compute environment

### 2025.8
- Created the poster for TJCAS
- Created the poster for FastML
- Attended VLSICAD and TJCAS

### 2025.9
- Attended FastML
- Started planning for the Weak Lensing competition
- Assisted Edwin with low-level hardware profiling of Token Reduction using Nvidia Nsight Compute
- Established a basic flow with Flow Optimization to analyze very large profile data
- **[START]** Ongoing: NCU Profile Flow Optimization

### 2025.10
- Put coursework aside to focus entirely on the Weak Lensing competition (solo sprint)
- Ongoing: NCU Profile Flow Optimization

### 2025.11
- Continued the Weak Lensing sprint until mid-November
- Caught up on coursework progress
- Conducted NCU profiling on traccc
- Gained a deeper understanding of bottlenecks and identified the potential for batching
- Ongoing: NCU Profile Flow Optimization

### 2025.12
- Completed multi-event batching optimization by mid-month
- Achieved **93% speedup** with no physics accuracy loss
- Researched next steps (post-mid-month) and attempted several incorrect approaches
- Ongoing: NCU Profile Flow Optimization

### 2026.1
- Successfully implemented conditional Jacobian matrix aggregation (**18% speedup**, no degradation)
- Observation: Discovered that due to batching, the find/fit stage shifted from memory-bound to compute-bound
- Analysis: High FLOPS tasks cannot be migrated to FPGA due to strict FP64 requirements (even FP32 causes accuracy degradation), making FPGA hardware resources unfeasible
- Future Direction: The thesis direction will focus on remaining on the GPU and addressing register pressure
- **[END]** Ongoing: NCU Profile Flow Optimization

---

## 6. Risk Considerations

| Risk | Mitigation |
|------|------------|
| LaTeX not installed | Use `apt install texlive-full` or minimal `texlive-latex-base texlive-pictures` |
| TikZ positioning issues with dense months | Adjust Y-spacing dynamically or group items |
| PDF too long for single page | Use multi-page or landscape orientation |
| Ongoing bar overlaps content | Place bar in background layer with transparency |

---

## 7. Expected Output

A single-page (or multi-page if needed) PDF containing:
- Professional vertical timeline
- All 15 months of entries with bullet points
- Visual emphasis on speedup metrics
- Continuous bar showing ongoing NCU work
- Clean, readable typography

---

## 8. Deliverables Checklist

- [ ] `timeline.tex` created
- [ ] Compiles without errors
- [ ] `timeline.pdf` generated
- [ ] All content from `request.md` included
- [ ] Ongoing work bar visible
- [ ] Committed to git
- [ ] Pushed to `noyaboy/timeline`
