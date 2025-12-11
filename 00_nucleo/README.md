# /00_nucleo — The Seed / A Semente

> **EN**: The Source of Truth. Ground zero of crystallization.  
> **PT**: A Fonte da Verdade. Ponto zero da cristalização.

---

## Purpose / Propósito

| EN | PT |
|----|-----|
| This directory contains the **genetic material** of the project: specifications, business rules, architecture decisions, and interface contracts. | Este diretório contém o **material genético** do projeto: especificações, regras de negócio, decisões de arquitetura e contratos de interface. |

---

## The Nucleation Lock / A Trava de Nucleação

> [!CAUTION]
> **No specification here = No code can be written**
>
> **Sem especificação aqui = Nenhum código pode ser escrito**

Before ANY feature is implemented in `01_core` through `04_wiring`, a corresponding document MUST exist in this directory.

Antes de QUALQUER funcionalidade ser implementada de `01_core` até `04_wiring`, um documento correspondente DEVE existir neste diretório.

---

## Directory Structure / Estrutura de Diretórios

```
00_nucleo/
├── specs/           # Feature specifications / Especificações de features
├── contracts/       # Interface contracts & types / Contratos de interface e tipos
└── adr/             # Architecture Decision Records
```

### /specs
- Feature specifications / Especificações de funcionalidades
- Business rules / Regras de negócio
- User stories / Histórias de usuário

### /contracts
- TypeScript interfaces / Interfaces TypeScript
- API schemas (OpenAPI, GraphQL) / Schemas de API
- Data transfer object definitions / Definições de DTOs

### /adr
- Architecture Decision Records
- Records of significant architectural choices / Registro de escolhas arquiteturais significativas
- Format: `NNNN-title-with-dashes.md`

---

## Rules / Regras

1. **Read-First** — AI must read this directory before any generation
2. **Human Approval** — All specs require human validation
3. **Traceability** — Every code file must trace to a document here
4. **Immutability** — Approved specs should not change without ADR

---

## Template Links / Links de Templates

- [ADR Template](./adr/template.md)
- [Spec Template](./specs/.template.md)
- [Contract Template](./contracts/.template.md)
