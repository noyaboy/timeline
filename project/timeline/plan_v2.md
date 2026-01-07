# Plan V2: Safe Visualization Optimization (No Information Loss)

## Principles

1. **Additive only** - Add visual elements, never remove or truncate text
2. **Preserve all original content** - Every bullet point remains intact
3. **Expand page space** - Use 2 pages or landscape if needed
4. **No rewording** - Keep original phrasing; only add clarifications in parentheses

---

## Safe Optimizations to Implement

### 1. Graphical Timeline Spine with Nodes

**What:** Add a vertical TikZ line with circular nodes at each date entry

**Implementation:**
- Draw vertical spine on left side
- Place colored circular node at each date
- Keep all existing text content to the right of spine
- No text changes required

```
    ●──── 2024.11–2025.1
    │     • Established the traccc environment
    │
    ●──── 2025.2–2025.3
    │     • Studied traccc code...
    │     • Analyzed next steps...
```

**Risk:** None - purely additive

---

### 2. Speedup Achievement Badges

**What:** Add small colored badges/boxes next to speedup numbers

**Implementation:**
- Wrap speedup percentages in `\fbox` or TikZ node with background
- Keep inline with existing text
- Badge appears alongside, not replacing, the text

**Example:**
```
• Split the fit kernel, increasing throughput by [10%]  ← boxed badge
```

**Risk:** None - same text with visual emphasis

---

### 3. Continuous Ongoing Work Sidebar

**What:** Replace repeated "Ongoing:" italic text with a single continuous visual bar

**Implementation:**
- Draw a colored vertical bar spanning 2025.9 to 2026.1 on the margin
- Label it once: "NCU Profile Flow Optimization"
- Remove only the redundant italic "Ongoing:" lines (4 instances)
- Keep "Begin:" and "End:" markers

**Content removed (redundant only):**
- `\textit{Ongoing: NCU Profile Flow Optimization}` × 4 instances

**Risk:** Minimal - removes redundancy, information preserved in sidebar label

---

### 4. Expand to 2 Pages

**What:** Allow content to flow to 2 pages for better readability

**Implementation:**
- Increase font from 9pt to 10pt
- Increase line spacing
- Add more whitespace between entries
- Use `longtable` for automatic page break

**Risk:** None - more space, same content

---

### 5. Category Color Dots (Not Icons)

**What:** Add small colored dots before bullet items to indicate category

**Implementation:**
- Green dot: Optimization/Performance work
- Orange dot: Conference/Paper activity
- Blue dot: Tooling/Environment setup
- Gray dot: Other (coursework, collaboration)

**Example:**
```
• ● Set up the Nvidia Nsight Systems environment     ← blue dot
• ● Profiled traccc to identify bottlenecks          ← green dot
• ● Created figures for YunChen's paper              ← orange dot
```

**Risk:** None - dots supplement, don't replace text

---

### 6. First-Mention Clarifications (Parenthetical Only)

**What:** Add brief parenthetical clarifications on first mention of technical terms

**Implementation:** Add parentheses after term, never reword original

| Term | Clarification to Add |
|------|---------------------|
| traccc | (GPU track reconstruction) |
| Nsight Systems | (NVIDIA profiler) |
| Nsight Compute | (NVIDIA kernel profiler) |
| NCU | (Nsight Compute) |
| Kalman gain matrix | (track fitting computation) |
| VLSICAD | (conference) |
| TJCAS | (conference) |
| FastML | (workshop) |

**Example:**
```
Before: "Established the traccc environment"
After:  "Established the traccc (GPU track reconstruction) environment"
```

**Risk:** None - original text preserved, clarification added

---

### 7. Descriptive Title

**What:** Make title more specific

**Current:** "Research Timeline: November 2024 -- January 2026"

**New:** "GPU Track Reconstruction Optimization Timeline: November 2024 -- January 2026"

**Risk:** None - expansion only

---

## Optimizations NOT Implementing (Information Loss Risk)

| Optimization | Why Excluded |
|--------------|--------------|
| Swim lane diagram | Forces extreme brevity |
| Multi-track columns | Narrow columns truncate text |
| Rewording entries | May alter original meaning |
| Removing "attempted incorrect approaches" | Loses authenticity |
| Quantifying accuracy degradation | Don't have exact number |
| Explaining what issues were | Speculation without facts |

---

## Implementation Order

1. **Expand to 2 pages** (creates space for other changes)
2. **Add timeline spine with nodes** (major visual improvement)
3. **Add speedup badges** (highlight achievements)
4. **Add continuous sidebar for ongoing work** (cleaner than repeated text)
5. **Add category color dots** (visual organization)
6. **Add parenthetical clarifications** (accessibility)
7. **Update title** (quick change)

---

## File Changes

| File | Changes |
|------|---------|
| `timeline.tex` | Complete rewrite with TikZ timeline structure |
| `timeline.pdf` | Recompile (expect 2 pages) |

---

## Expected Result

- 2-page PDF with graphical timeline
- All original content preserved verbatim
- Enhanced visual hierarchy for speedup achievements
- Cleaner ongoing work representation
- Better accessibility for non-expert readers
- Professional appearance suitable for thesis/presentation
