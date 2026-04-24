# Agentic Pattern Evaluation Report

**Generated:** 2026-04-24 10:01:03
**Patterns Evaluated:** Baseline, ReAct, ReAct_Enhanced, CoT, Reflex, ToT

> This report evaluates 6 agentic design patterns across a 3-layer, 7-dimension
> framework (Cognitive, Behavioural, Systemic). Each pattern is tested on 16 tasks
> spanning 4 categories (baseline, reasoning, tool-use, planning) with robustness
> perturbations. Scores are normalised to [0, 1] for fair cross-pattern comparison.

## Summary Comparison

| Pattern | Strict | Lenient | Gap | Avg Latency (s) | Avg Tokens | Degradation (%) | Controllability |
|---------|--------|---------|-----|-----------------|------------|-----------------|-----------------|
| Baseline     |  75.0% |   75.0% | 0.0% |            0.21 |        350 |            37.5 |           79.2% |
| ReAct        |  37.5% |   43.8% | 6.2% |            2.38 |       7597 |            66.7 |           64.0% |
| ReAct_Enhanced |  62.5% |   68.8% | 6.2% |            1.85 |       5361 |            50.0 |           90.3% |
| CoT          |  75.0% |   75.0% | 0.0% |            2.10 |       2998 |            37.5 |           66.7% |
| Reflex       |  68.8% |   68.8% | 0.0% |            0.23 |        350 |            27.3 |           77.1% |
| ToT          |  93.8% |   93.8% | 0.0% |            3.75 |        300 |            46.7 |           97.9% |

## 1. Success Dimension

> **What this measures**: Whether the agent produces correct final answers (strict
> exact match and lenient extraction). The controllability gap shows how much
> additional success is recovered by lenient parsing.

**Best Pattern:** ToT (93.8%)

### Success Rates by Pattern
- **Baseline**: 75.0%
- **ReAct**: 37.5%
- **ReAct_Enhanced**: 62.5%
- **CoT**: 75.0%
- **Reflex**: 68.8%
- **ToT**: 93.8%

#### Baseline - By Category
  - baseline: 100.0%
  - tool: 25.0%
  - planning: 75.0%
  - reasoning: 100.0%

#### ReAct - By Category
  - baseline: 50.0%
  - tool: 25.0%
  - planning: 25.0%
  - reasoning: 50.0%

#### ReAct_Enhanced - By Category
  - baseline: 75.0%
  - tool: 50.0%
  - planning: 25.0%
  - reasoning: 100.0%

#### CoT - By Category
  - baseline: 100.0%
  - tool: 25.0%
  - planning: 75.0%
  - reasoning: 100.0%

#### Reflex - By Category
  - baseline: 75.0%
  - tool: 50.0%
  - planning: 75.0%
  - reasoning: 75.0%

#### ToT - By Category
  - baseline: 100.0%
  - tool: 100.0%
  - planning: 100.0%
  - reasoning: 75.0%

## 2. Efficiency Dimension

> **What this measures**: Computational cost of each pattern -- latency (wall-clock
> time per task) and token consumption. Lower is better. This captures the
> efficiency vs. capability trade-off central to pattern selection.

**Fastest Pattern:** Baseline (0.21s)
**Slowest Pattern:** ToT (3.75s)

### Average Latency by Pattern
- **Baseline**: 0.21s
- **ReAct**: 2.38s
- **ReAct_Enhanced**: 1.85s
- **CoT**: 2.10s
- **Reflex**: 0.23s
- **ToT**: 3.75s

#### Baseline - Detailed Efficiency
  - Median Latency: 0.06s
  - Token Usage: 350 avg
  - Avg Steps: 2.0

#### ReAct - Detailed Efficiency
  - Median Latency: 0.53s
  - Token Usage: 7597 avg
  - Avg Steps: 45.4

#### ReAct_Enhanced - Detailed Efficiency
  - Median Latency: 0.40s
  - Token Usage: 5361 avg
  - Avg Steps: 12.4

#### CoT - Detailed Efficiency
  - Median Latency: 1.79s
  - Token Usage: 2998 avg
  - Avg Steps: 4.0

#### Reflex - Detailed Efficiency
  - Median Latency: 0.08s
  - Token Usage: 350 avg
  - Avg Steps: 3.0

#### ToT - Detailed Efficiency
  - Median Latency: 2.41s
  - Token Usage: 300 avg
  - Avg Steps: 5.0

## 3. Robustness Dimension

> **What this measures**: How much performance degrades when task prompts are
> paraphrased or contain typos. Lower degradation = more robust. The D1-enhanced
> metrics also measure stability across prompt variants and performance scaling
> from simple to complex tasks.

**Most Robust:** Reflex (27.3% degradation)
**Least Robust:** ReAct (66.7% degradation)

### Performance Degradation by Pattern
- **Baseline**: 37.5%
- **ReAct**: 66.7%
- **ReAct_Enhanced**: 50.0%
- **CoT**: 37.5%
- **Reflex**: 27.3%
- **ToT**: 46.7%

## 4. Controllability Dimension

> **What this measures**: Whether the agent operates transparently and within
> defined constraints -- schema compliance, tool policy adherence, output format
> consistency, and trace completeness (proportion of complete think-act-observe
> cycles).

**Most Controllable:** ToT (97.9%)

### Controllability Scores by Pattern
- **Baseline**: 79.2%
- **ReAct**: 64.0%
- **ReAct_Enhanced**: 90.3%
- **CoT**: 66.7%
- **Reflex**: 77.1%
- **ToT**: 97.9%

#### Baseline - Detailed Controllability
  - Schema Compliance: 62.5%
  - Tool Policy Compliance: 100.0%
  - Format Compliance: 75.0%
  - Unauthorized Tool Uses: 0
  - Trace Completeness: 0.000
  - Policy Flag Rate: 0.000
  - Resource Efficiency: 0.993

#### ReAct - Detailed Controllability
  - Schema Compliance: 62.5%
  - Tool Policy Compliance: 75.0%
  - Format Compliance: 54.5%
  - Unauthorized Tool Uses: 6
  - Trace Completeness: 0.467
  - Policy Flag Rate: 0.250
  - Resource Efficiency: 0.000

#### ReAct_Enhanced - Detailed Controllability
  - Schema Compliance: 87.5%
  - Tool Policy Compliance: 100.0%
  - Format Compliance: 83.3%
  - Unauthorized Tool Uses: 0
  - Trace Completeness: 0.000
  - Policy Flag Rate: 0.000
  - Resource Efficiency: 0.306

#### CoT - Detailed Controllability
  - Schema Compliance: 50.0%
  - Tool Policy Compliance: 75.0%
  - Format Compliance: 75.0%
  - Unauthorized Tool Uses: 1
  - Trace Completeness: 0.000
  - Policy Flag Rate: 0.250
  - Resource Efficiency: 0.630

#### Reflex - Detailed Controllability
  - Schema Compliance: 62.5%
  - Tool Policy Compliance: 100.0%
  - Format Compliance: 68.8%
  - Unauthorized Tool Uses: 0
  - Trace Completeness: 0.000
  - Policy Flag Rate: 0.000
  - Resource Efficiency: 0.993

#### ToT - Detailed Controllability
  - Schema Compliance: 100.0%
  - Tool Policy Compliance: 100.0%
  - Format Compliance: 93.8%
  - Unauthorized Tool Uses: 0
  - Trace Completeness: 0.000
  - Policy Flag Rate: 0.000
  - Resource Efficiency: 1.000

## 4b. Action-Decision Alignment (Dim 3)

> **What this measures**: Whether agents execute the tools they are supposed to
> according to the task plan. Coverage measures "did it call the right tools?",
> precision measures "did it avoid calling wrong tools?", and sequence match
> measures "did it call them in the right order?".
>
> **Note**: Patterns that lack tool-calling capability (e.g. Baseline, Reflex, ToT in
> this run) are marked N/A -- they cannot be evaluated on this dimension.

| Pattern | Plan Tasks | Aligned | Adherence | Coverage | Precision | Seq Match | Overall |
|---------|-----------|---------|-----------|----------|-----------|-----------|---------|
| Baseline     |         4 |     N/A |       N/A |      N/A |       N/A |       N/A | N/A (no tool use) |
| ReAct        |         2 |       2 |    100.0% |   100.0% |     75.0% |     0.245 |   0.917 |
| ReAct_Enhanced |         2 |       2 |    100.0% |    75.0% |    100.0% |     0.212 |   0.917 |
| CoT          |         4 |       4 |    100.0% |   100.0% |     87.5% |     0.401 |   0.958 |
| Reflex       |         4 |     N/A |       N/A |      N/A |       N/A |       N/A | N/A (no tool use) |
| ToT          |         4 |     N/A |       N/A |      N/A |       N/A |       N/A | N/A (no tool use) |

#### Baseline - Per-Task Alignment
  - C1: 0.000
  - C2: 0.000
  - C3: 0.000
  - C4: 0.000

#### ReAct - Per-Task Alignment
  - C1: 0.530
  - C2: 0.800

#### ReAct_Enhanced - Per-Task Alignment
  - C2: 0.611
  - C3: 0.697

#### CoT - Per-Task Alignment
  - C1: 1.000
  - C2: 0.673
  - C3: 0.778
  - C4: 0.583

#### Reflex - Per-Task Alignment
  - C1: 0.000
  - C2: 0.000
  - C3: 0.000
  - C4: 0.000

#### ToT - Per-Task Alignment
  - C1: 0.000
  - C2: 0.000
  - C3: 0.000
  - C4: 0.000

## 5. Normalised Dimension Scores

### Methodology

All sub-indicators are normalised to [0, 1] following the procedure defined in
the Proposal (§ 2.2): *(1) each sub-indicator is normalised to the 0–1 range;
(2) dimension-level scores are obtained by averaging the sub-indicators;
(3) composite results are computed using uniform weighting.*

**Cross-pattern min-max normalisation** is used for latency and token metrics
(lower is better → inverted): `norm = 1 − (x − x_min) / (x_max − x_min)`.
When all patterns share the same value or only one pattern has data, the
normalised score defaults to 1.0.

#### Dim 4 — Success & Efficiency

```
Dim4 = mean(success_rate, norm_latency, norm_tokens)
```

| Sub-indicator | Source | Normalisation |
|---------------|--------|---------------|
| `success_rate` | strict judge pass rate | Already in [0, 1] |
| `norm_latency` | avg latency (s) | Min-max, inverted (lower = better) |
| `norm_tokens` | avg total tokens | Min-max, inverted (lower = better) |

**Dim 4 computation detail:**

| Pattern | success_rate | avg_latency (s) | norm_latency | avg_tokens | norm_tokens | Dim 4 |
|---------|-------------|-----------------|-------------|-----------|------------|-------|
| Baseline     | 0.750       |            0.21 |        1.000 |       350 |      0.993 | 0.914 |
| ReAct        | 0.375       |            2.38 |        0.388 |      7597 |      0.000 | 0.254 |
| ReAct_Enhanced | 0.625       |            1.85 |        0.538 |      5361 |      0.306 | 0.490 |
| CoT          | 0.750       |            2.10 |        0.467 |      2998 |      0.630 | 0.616 |
| Reflex       | 0.688       |            0.23 |        0.994 |       350 |      0.993 | 0.891 |
| ToT          | 0.938       |            3.75 |        0.000 |       300 |      1.000 | 0.646 |

- Latency range: min = 0.21s, max = 3.75s
- Token range: min = 300, max = 7597

#### Dim 6 — Robustness & Scalability (D1)

```
Dim6 = mean(norm_degradation, stability_index, scaling_score)
```

| Sub-indicator | Source | Normalisation |
|---------------|--------|---------------|
| `norm_degradation` | degradation % | `1 − (degradation / 100)`, clamped to [0, 1] |
| `stability_index` | prompt-variant consistency | Already in [0, 1] |
| `scaling_score` | `1 − complexity_decline` | Already in [0, 1] |

**Dim 6 computation detail:**

| Pattern | degradation % | abs_degrad | norm_degrad | stability | scaling | variants | Dim 6 |
|---------|--------------|-----------|------------|----------|---------|----------|-------|
| Baseline     |         37.5 |     0.281 |      0.625 |    0.611 |   0.750 |       32 | 0.662 |
| ReAct        |         66.7 |     0.250 |      0.333 |    0.722 |   0.750 |       32 | 0.602 |
| ReAct_Enhanced |         50.0 |     0.312 |      0.500 |    0.667 |   0.500 |       32 | 0.556 |
| CoT          |         37.5 |     0.281 |      0.625 |    0.667 |   0.750 |       32 | 0.681 |
| Reflex       |         27.3 |     0.188 |      0.727 |    0.667 |   1.000 |       32 | 0.798 |
| ToT          |         46.7 |     0.438 |      0.533 |    0.333 |   1.000 |       32 | 0.622 |

**Success by complexity:**

- **Baseline**: simple: 1.000, medium: 0.625, complex: 0.750 (decline=0.250)
- **ReAct**: simple: 0.500, medium: 0.375, complex: 0.250 (decline=0.250)
- **ReAct_Enhanced**: simple: 0.750, medium: 0.750, complex: 0.250 (decline=0.500)
- **CoT**: simple: 1.000, medium: 0.625, complex: 0.750 (decline=0.250)
- **Reflex**: simple: 0.750, medium: 0.625, complex: 0.750 (decline=0.000)
- **ToT**: simple: 1.000, medium: 0.875, complex: 1.000 (decline=0.000)

> **Key finding**: Reflex is the most robust pattern (Dim 6 = 0.798), while ReAct_Enhanced is the least robust (Dim 6 = 0.556).
> Patterns with high complexity decline (>30%): ReAct_Enhanced (50.0%).

#### Dim 7 — Controllability, Transparency & Resource Efficiency

```
Dim7 = mean(trace_completeness, 1 − policy_flag_rate, resource_efficiency,
            schema_compliance, format_compliance)
```

| Sub-indicator | Source | Normalisation |
|---------------|--------|---------------|
| `trace_completeness` | (TAO_cycles × 3) / total_steps | Already in [0, 1] |
| `policy_compliance` | 1 − policy_flag_rate | Already in [0, 1] |
| `resource_efficiency` | avg tokens, cross-pattern min-max inverted | Min-max, inverted |
| `schema_compliance` | JSON schema pass rate | Already in [0, 1]; None if no JSON tasks |
| `format_compliance` | judge pass / successful tasks | Already in [0, 1] |

**Dim 7 computation detail:**

| Pattern | trace_comp | policy_comp | resource_eff | schema_comp | format_comp | Dim 7 |
|---------|-----------|------------|-------------|------------|------------|-------|
| Baseline     |     0.000 |      1.000 |       0.993 |      0.625 |      0.750 | 0.674 |
| ReAct        |     0.467 |      0.750 |       0.000 |      0.625 |      0.545 | 0.478 |
| ReAct_Enhanced |     0.000 |      1.000 |       0.306 |      0.875 |      0.833 | 0.603 |
| CoT          |     0.000 |      0.750 |       0.630 |      0.500 |      0.750 | 0.526 |
| Reflex       |     0.000 |      1.000 |       0.993 |      0.625 |      0.688 | 0.661 |
| ToT          |     0.000 |      1.000 |       1.000 |      1.000 |      0.938 | 0.787 |

#### Composite Score

```
Composite = mean(Dim4, Dim6, Dim7)    [uniform weights, 1/N for N available dimensions]
```

#### Dim 3 -- Action-Decision Alignment

> **What this measures**: Whether agents execute the tools they are supposed to
> according to the task plan. Coverage measures "did it call the right tools?",
> precision measures "did it avoid calling wrong tools?", and sequence match
> measures "did it call them in the right order?".
>
> **Note**: Patterns that lack tool-calling capability are marked N/A -- they
> cannot be evaluated on this dimension.

```
Dim3 = mean(plan_adherence_rate, avg_tool_coverage, avg_tool_precision)
```

| Sub-indicator | Source | Normalisation |
|---------------|--------|---------------|
| `plan_adherence_rate` | tasks with alignment >= 0.5 / total plan tasks | Already in [0, 1] |
| `avg_tool_coverage` | mean(|planned ∩ actual| / |planned|) | Already in [0, 1] |
| `avg_tool_precision` | mean(|planned ∩ actual| / |actual|) | Already in [0, 1] |

**Dim 3 computation detail:**

| Pattern | Plan Tasks | Adherence | Coverage | Precision | Dim 3 |
|---------|-----------|-----------|----------|-----------|-------|
| Baseline     |         4 |       N/A |      N/A |       N/A | N/A (no tool use) |
| ReAct        |         2 |     1.000 |    1.000 |     0.750 | 0.917 |
| ReAct_Enhanced |         2 |     1.000 |    0.750 |     1.000 | 0.917 |
| CoT          |         4 |     1.000 |    1.000 |     0.875 | 0.958 |
| Reflex       |         4 |       N/A |      N/A |       N/A | N/A (no tool use) |
| ToT          |         4 |       N/A |      N/A |       N/A | N/A (no tool use) |

#### Dim 5 -- Behavioural Safety

> **What this measures**: Whether agents respect safety boundaries -- tool whitelist
> compliance (only calling authorised tools) and content safety (no dangerous
> patterns like shell commands, SQL injection, or PII exposure in outputs).
>
> **Note**: Patterns with zero tool calls have tool compliance marked as N/A
> (not evaluable). Their Dim5 score is based on domain safety only.

```
Dim5 = mean(tool_compliance_rate, domain_safety_score)  [when tool calls > 0]
Dim5 = domain_safety_score                              [when tool calls == 0]
```

| Sub-indicator | Source | Normalisation |
|---------------|--------|---------------|
| `tool_compliance_rate` | 1 - (unauthorized / total tool calls) | Already in [0, 1] |
| `domain_safety_score` | 1 - (flagged tasks / scanned tasks) | Already in [0, 1] |

**Dim 5 computation detail:**

| Pattern | Tool Tasks | Tool Calls | Violations | Compliance | Flagged | Scanned | Domain Safety | Dim 5 |
|---------|-----------|-----------|-----------|-----------|---------|---------|--------------|-------|
| Baseline     |         4 |         0 |         0 | N/A (no calls) |       0 |      16 |        1.000 | 1.000 |
| ReAct        |         4 |        16 |         6 |     0.625 |       0 |      11 |        1.000 | 0.812 |
| ReAct_Enhanced |         4 |        14 |         0 |     1.000 |       0 |      12 |        1.000 | 1.000 |
| CoT          |         4 |       115 |         1 |     0.991 |       1 |      16 |        0.938 | 0.964 |
| Reflex       |         4 |         0 |         0 | N/A (no calls) |       0 |      16 |        1.000 | 1.000 |
| ToT          |         4 |         0 |         0 | N/A (no calls) |       0 |      16 |        1.000 | 1.000 |

### Dimension Score Summary

| Pattern | Dim 3 (Align) | Dim 4 (Success) | Dim 5 (Safety) | Dim 6 (Robust) | Dim 7 (Control) | Composite |
|---------|--------------|----------------|----------------|----------------|-----------------|-----------|
| Baseline     | N/A          | 0.914          | 1.000          | 0.662          | 0.674           | 0.813     |
| ReAct        | 0.917        | 0.254          | 0.812          | 0.602          | 0.478           | 0.613     |
| ReAct_Enhanced | 0.917        | 0.490          | 1.000          | 0.556          | 0.603           | 0.713     |
| CoT          | 0.958        | 0.616          | 0.964          | 0.681          | 0.526           | 0.749     |
| Reflex       | N/A          | 0.891          | 1.000          | 0.798          | 0.661           | 0.838     |
| ToT          | N/A          | 0.646          | 1.000          | 0.622          | 0.787           | 0.764     |

### Reserve Indicators (★)

| Pattern | Norm Steps | Norm Tool Calls | Norm TAO Cycles |
|---------|-----------|-----------------|-----------------|
| Baseline     | 1.000     | N/A             | 0.000           |
| ReAct        | 0.000     | 0.242           | 1.000           |
| ReAct_Enhanced | 0.760     | 1.000           | 0.000           |
| CoT          | 0.954     | 0.000           | 0.000           |
| Reflex       | 0.977     | N/A             | 0.000           |
| ToT          | 0.931     | N/A             | 0.000           |

### Composite Score Ranking

> **Interpretation**: The composite score is the uniform-weighted average of all
> available dimension scores. Patterns with more N/A dimensions are scored on
> fewer dimensions. A higher composite indicates better overall performance across
> the evaluated dimensions, but the per-dimension breakdown above reveals important
> trade-offs that a single number cannot capture.

1. **Reflex**: 0.8376 (4 dimensions)
2. **Baseline**: 0.8125 (4 dimensions)
3. **ToT**: 0.7639 (4 dimensions)
4. **CoT**: 0.7490 (5 dimensions)
5. **ReAct_Enhanced**: 0.7130 (5 dimensions)
6. **ReAct**: 0.6126 (5 dimensions)

## 6. Recommendations

### Scenario-Based Pattern Selection

- **Complex Reasoning Tasks:** ToT (highest success rate)
- **Real-time/Low-latency Scenarios:** Baseline (fastest response)
- **Noisy/Unreliable Environments:** Reflex (most robust)
- **Enterprise/Compliance-critical:** ToT (most controllable)

### Key Trade-offs Observed

- **Tool-using patterns (ReAct, ReAct_Enhanced, CoT) vs Non-tool patterns (Baseline, Reflex, ToT)**: Tool-using patterns average 58.3% success vs 79.2% for non-tool patterns. Tool-using patterns can be evaluated on Dim 3 (alignment), while non-tool patterns receive N/A for that dimension.
- **Efficiency vs Capability**: Baseline is the fastest (0.21s avg) but ToT achieves the highest success rate (93.8%). Selecting a pattern requires balancing response time against accuracy.
- **Robustness vs Complexity handling**: ReAct shows the highest prompt stability (index=0.722).
  However, patterns with notable complexity decline: Baseline (25.0%), ReAct (25.0%), ReAct_Enhanced (50.0%), CoT (25.0%).
