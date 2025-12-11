# The Crystalline Architecture Manifesto
# O Manifesto da Arquitetura Cristalina

**Version / Versão**: 1.0 (Nucleation Revision / Revisão de Nucleação)  
**Context / Contexto**: Era of AI-Assisted Development / Era do Desenvolvimento Assistido por Inteligência Artificial

---

## Preamble / Preâmbulo

> **EN**: Modern software engineering faces "AI Entropy": the statistical tendency of models to generate functional but structurally amorphous and fragile code. The Crystalline Architecture combats entropy through **Nucleation**: the process of imposing a strict geometric order from a stable central point, forcing code to grow like a perfect crystal, not as a disordered organic mass.

> **PT**: A engenharia de software moderna enfrenta a "Entropia da IA": a tendência estatística de modelos gerarem código funcional, mas estruturalmente amorfo e frágil. A Arquitetura Cristalina combate a entropia através da **Nucleação**: o processo de impor uma ordem geométrica estrita a partir de um ponto central estável, forçando o código a crescer como um cristal perfeito, não como uma massa orgânica desordenada.

---

## The Physics of Code Principles / Os Princípios da Física de Código

### 1. Law of Nucleation / Lei da Nucleação

| EN | PT |
|----|-----|
| Order does not arise from nothing; it radiates from a center. Code (structure) is merely the crystallized manifestation of decisions made in the Nucleus. Without a clear seed, crystallization fails and generates structural defects. | A ordem não surge do nada; ela irradia de um centro. O código (a estrutura) é apenas a manifestação cristalizada das decisões tomadas no Núcleo. Sem uma semente clara, a cristalização falha e gera defeitos estruturais. |

### 2. Containment Topology / Topologia de Contenção

| EN | PT |
|----|-----|
| In a generative environment, folder structure is a physical barrier. If the path doesn't exist, AI energy cannot flow there. Architecture imposes rigid limits to guide growth. | Em um ambiente gerativo, a estrutura de pastas é uma barreira física. Se o caminho não existe, a energia da IA não pode fluir para lá. A arquitetura impõe limites rígidos para guiar o crescimento. |

### 3. Dependency Gravity / Gravidade de Dependência

| EN | PT |
|----|-----|
| Stability flows from center to edge. Outer layers (Shell, Infra) depend on inner ones (Core), but the inverse never occurs. The Nucleus never knows the edge exists. | A estabilidade flui do centro para a borda. As camadas externas (Shell, Infra) dependem das internas (Core), mas o inverso jamais ocorre. O Núcleo nunca sabe que a borda existe. |

### 4. Laboratory Darwinism / Darwinismo de Laboratório

| EN | PT |
|----|-----|
| Evolution is separated from production. Dirty experimentation occurs in isolation (Lab). Only algorithms that prove their thermodynamic efficiency survive and are "purified" to integrate the main system. | A evolução é separada da produção. A experimentação suja ocorre isolada (Lab). Apenas algoritmos que provam sua eficiência termodinâmica sobrevivem e são "purificados" para integrar o sistema principal. |

---

## The Lattice / O Retículo

The canonical crystallization structure. The project follows strict numbering (00-04). AI must process context in this order, ensuring the seed (00) defines form before matter (01-04) is allocated.

A estrutura canônica de cristalização. O projeto segue uma numeração estrita (00-04). A IA deve processar o contexto nesta ordem, garantindo que a semente (00) defina a forma antes que a matéria (01-04) seja alocada.

```
project/
├── 00_nucleo/    # The Seed / A Semente
├── 01_core/      # Pure Crystal / O Cristal Puro
├── 02_shell/     # The Surface / A Superfície
├── 03_infra/     # The Support / O Suporte
├── 04_wiring/    # The Energy / A Energia
└── _lab/         # The Arena / A Rinha
```

---

### /00_nucleo — The Seed / A Semente

**EN**: The Source of Truth. Ground zero: Specifications, Business Rules, ADRs (Architecture Decision Records), and Interface Contracts. This is the initial genetic material. If it's not in the Nucleus, it cannot crystallize in code. AI must "read the seed" before generating any structure.

**PT**: A Fonte da Verdade. O ponto zero: Especificações, Regras de Negócio, ADRs (Architecture Decision Records) e Contratos de Interface. É o material genético inicial. Se não está no Núcleo, não pode cristalizar no código. A IA deve "ler a semente" antes de gerar qualquer estrutura.

---

### /01_core — Pure Crystal / O Cristal Puro

**EN**: Platonic Logic. Entities, Pure Mathematics, Algorithms, Domain Rules.

**PT**: A Lógica Platônica. Entidades, Matemática Pura, Algoritmos, Regras de Domínio.

> [!CAUTION]
> **Absolute Restriction / Restrição Absoluta**: Zero I/O. No database access, network, UI frameworks, or system clock. Pure language only (Vanilla JS, C++ STL, Python Standard Lib).
>
> Zero I/O. Sem acesso a banco de dados, rede, frameworks de UI ou relógio do sistema. Apenas a linguagem pura.

---

### /02_shell — The Surface / A Superfície

**EN**: The Crystal's Face. Everything externally touchable: UI (React/Vue), API (REST/GraphQL), CLI.

**PT**: A Face do Cristal. Tudo que é tocável externamente: UI (React/Vue), API (REST/GraphQL), CLI.

> [!IMPORTANT]
> **Dependency Rule / Regra de Dependência**: Can import `01_core`. Forbidden to import `03_infra`.
>
> Pode importar `01_core`. É proibido de importar `03_infra`.

---

### /03_infra — The Support / O Suporte

**EN**: The Physical World. Database, File System, GPU Drivers, Network Requests. The "Dirty World" implementing clean interfaces defined in `01_core` (Dependency Inversion).

**PT**: O Mundo Físico. Banco de Dados, Sistema de Arquivos, Drivers de GPU, Requisições de Rede. O "Mundo Sujo" que implementa interfaces limpas definidas no `01_core` (Inversão de Dependência).

---

### /04_wiring — The Energy / A Energia

**EN**: The Connection. Dependency Injection, Environment Configuration, `main()`, Entry Points. The only directory that "sees" the entire crystal and connects parts to give life to the system.

**PT**: A Conexão. Injeção de Dependência, Configuração de Ambiente, `main()`, Entry Points. O único diretório que "vê" todo o cristal e conecta as partes para dar vida ao sistema.

---

### /_lab — The Arena / A Rinha

**EN**: Controlled Chaos. Isolated sandbox for benchmarks and proof of concept.

**PT**: O Caos Controlado. Sandbox isolado para benchmarks e prova de conceito.

> [!WARNING]
> **Quarantine Rule / Regra de Quarentena**: The main system (00-04) never imports `/_lab`. Code here is volatile. A winning algorithm in Lab must be rewritten from scratch when promoted to `01_core`.
>
> O sistema principal (00-04) jamais importa o `/_lab`. O código aqui é volátil. Um algoritmo vencedor no Lab deve ser reescrito do zero ao ser promovido para o `01_core`.

---

## Operating Protocols (For AI Agents) / Protocolos de Operação (Para Agentes de IA)

To ensure structural integrity, AI must obey these triggers:

Para garantir a integridade estrutural, a IA deve obedecer a estes gatilhos:

### 1. Nucleation Lock / Trava de Nucleação

| EN | PT |
|----|-----|
| **Command**: "IMPLEMENT" | **Comando**: "IMPLEMENTAR" |
| AI is forbidden from generating executable code (`.cpp`, `.py`, `.ts`) until the corresponding specification file exists in `/00_nucleo` and has been validated by the Human Architect. | A IA está proibida de gerar código executável (`.cpp`, `.py`, `.ts`) até que o arquivo de especificação correspondente exista em `/00_nucleo` e tenha sido validado pelo Arquiteto Humano. |

### 2. Lineage Traceability / Rastreabilidade de Linhagem

| EN | PT |
|----|-----|
| Every code file must be able to answer: "Which Nucleus document am I materializing?" Orphan code (without nucleus seed) is considered a defect. | Todo arquivo de código deve ser capaz de responder: "Qual documento do Núcleo eu estou materializando?". Código órfão (sem semente no núcleo) é considerado defeito. |

### 3. Isomorphism Audit / Auditoria de Isomorfismo

| EN | PT |
|----|-----|
| AI must periodically verify if implementation has diverged from the seed's original intent (functional hallucination) and correct code to realign with `/00_nucleo`. | A IA deve verificar periodicamente se a implementação divergiu da intenção original da semente (alucinação funcional) e corrigir o código para realinhar com o `/00_nucleo`. |

---

## Industry Standard Mapping / Mapeamento para Padrões de Mercado

| Crystalline | Industry Standard |
|-------------|-------------------|
| Manifesto / Philosophy | Clean Architecture + Functional Core / Imperative Shell |
| /00_nucleo | Specification / Single Source of Truth (SSOT) |
| /01_core | Domain Layer / Entities (Pure Business Logic) |
| /02_shell | Presentation Layer / Primary Adapters |
| /03_infra | Infrastructure Layer / Secondary Adapters |
| /04_wiring | Composition Root / Dependency Injection Container |
| /_lab | Spikes / POCs / Playground |
| Anti-Hallucination Protocol | Chain-of-Thought Prompting + RAG |

---

> [!NOTE]
> **This document is the project's Constitution. Violations to this structure compromise system stability.**
>
> **Este documento é a Constituição do projeto. Violações a esta estrutura comprometem a estabilidade do sistema.**
