# /_lab — The Arena / A Rinha

> **EN**: Controlled Chaos. The quarantined experimentation zone.  
> **PT**: O Caos Controlado. A zona de experimentação em quarentena.

---

## Purpose / Propósito

| EN | PT |
|----|-----|
| This directory is a **sandbox** for experiments, benchmarks, and proofs of concept. Code here is volatile and can be deleted at any time. | Este diretório é um **sandbox** para experimentos, benchmarks e provas de conceito. Código aqui é volátil e pode ser deletado a qualquer momento. |

---

## The Quarantine Rule / A Regra de Quarentena

> [!CAUTION]
> **ABSOLUTE QUARANTINE / QUARENTENA ABSOLUTA**
>
> The main system (00-04) **NEVER** imports anything from `_lab`.
>
> O sistema principal (00-04) **NUNCA** importa nada de `_lab`.

---

## What Lives Here / O Que Vive Aqui

- 🧪 **Experiments** — Try new approaches freely
- 📊 **Benchmarks** — Performance comparisons
- 🎯 **Spikes** — Quick exploration of unknowns
- 🔬 **Proofs of Concept** — Validate ideas before committing

---

## Lifecycle / Ciclo de Vida

```
1. EXPERIMENT      → Write messy code to explore
2. BENCHMARK       → Measure and compare approaches
3. DECIDE          → Choose winning approach
4. CRYSTALLIZE     → Rewrite from scratch in 01_core
5. DELETE          → Remove lab experiment
```

> [!IMPORTANT]
> A winning algorithm in Lab must be **REWRITTEN FROM SCRATCH** when promoted to `01_core`. Direct copy is prohibited.
>
> Um algoritmo vencedor no Lab deve ser **REESCRITO DO ZERO** ao ser promovido para `01_core`. Cópia direta é proibida.

---

## Why Rewrite? / Por Que Reescrever?

| EN | PT |
|----|-----|
| Lab code is optimized for **exploration speed**, not **production quality**. It may have shortcuts, missing error handling, or dependencies that violate the Zero I/O rule. Rewriting ensures the promoted code meets production standards. | Código de lab é otimizado para **velocidade de exploração**, não **qualidade de produção**. Pode ter atalhos, tratamento de erro faltando ou dependências que violam a regra de Zero I/O. Reescrever garante que o código promovido atenda padrões de produção. |

---

## File Naming Convention / Convenção de Nomes

Use prefixes to indicate experiment status:

```
_lab/
├── WIP_experiment_name/     # Work in progress
├── TESTED_algorithm_v2/     # Tested, pending decision
├── WINNER_fast_sort/        # Winner, ready to crystallize
└── ARCHIVED_old_approach/   # Kept for reference
```

---

## Freedom Zone / Zona de Liberdade

| Allowed / Permitido | 
|---------------------|
| ✅ Any external library |
| ✅ I/O operations |
| ✅ Messy code |
| ✅ Copy-paste from internet |
| ✅ AI-generated code without spec |
| ✅ Hardcoded values |
| ✅ No tests |

> [!NOTE]
> This is the ONLY place where AI can generate code without a prior specification in `00_nucleo`.
>
> Este é o ÚNICO lugar onde a IA pode gerar código sem uma especificação prévia em `00_nucleo`.
