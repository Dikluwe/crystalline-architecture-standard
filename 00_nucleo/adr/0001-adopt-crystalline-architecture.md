# ADR-0001: Adopt Crystalline Architecture
# ADR-0001: Adotar Arquitetura Cristalina

## Status / Estado

`ACCEPTED`

## Date / Data

2024-01-01

## Context / Contexto

> **EN**: Modern software development increasingly relies on AI-assisted code generation. However, AI models tend to generate functional but structurally inconsistent code, leading to "AI Entropy" — projects that work but become unmaintainable over time.

> **PT**: O desenvolvimento de software moderno depende cada vez mais de geração de código assistida por IA. No entanto, modelos de IA tendem a gerar código funcional mas estruturalmente inconsistente, levando à "Entropia de IA" — projetos que funcionam mas se tornam impossíveis de manter ao longo do tempo.

## Decision / Decisão

> **EN**: We adopt the Crystalline Architecture as our structural standard. This includes:
> 1. A strict folder hierarchy (00-04 + _lab)
> 2. Mandatory specification-first development
> 3. Zero I/O in the core layer
> 4. Quarantine rules for experimental code
> 5. AI protocol files (.cursorrules, .agentrules)

> **PT**: Adotamos a Arquitetura Cristalina como nosso padrão estrutural. Isso inclui:
> 1. Uma hierarquia de pastas estrita (00-04 + _lab)
> 2. Desenvolvimento obrigatório com especificação primeiro
> 3. Zero I/O na camada core
> 4. Regras de quarentena para código experimental
> 5. Arquivos de protocolo de IA (.cursorrules, .agentrules)

## Consequences / Consequências

### Positive / Positivas
- Consistent structure across all projects / Estrutura consistente em todos os projetos
- AI-generated code follows predictable patterns / Código gerado por IA segue padrões previsíveis
- Clear separation of concerns / Separação clara de responsabilidades
- Traceability from specification to implementation / Rastreabilidade da especificação à implementação

### Negative / Negativas
- Initial learning curve / Curva de aprendizado inicial
- More upfront planning required / Mais planejamento antecipado necessário
- May feel restrictive for small projects / Pode parecer restritivo para projetos pequenos

### Neutral / Neutras
- Requires team alignment on conventions / Requer alinhamento do time em convenções

## References / Referências

- [MANIFESTO.md](../../MANIFESTO.md)
- [Clean Architecture - Robert C. Martin](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
- [Hexagonal Architecture - Alistair Cockburn](https://alistair.cockburn.us/hexagonal-architecture/)
