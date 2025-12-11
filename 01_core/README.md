# /01_core — Pure Crystal / O Cristal Puro

> **EN**: Platonic Logic. The heart of pure business rules.  
> **PT**: A Lógica Platônica. O coração das regras de negócio puras.

---

## Purpose / Propósito

| EN | PT |
|----|-----|
| This directory contains **pure domain logic**: entities, algorithms, mathematical functions, and business rules with **absolutely no I/O**. | Este diretório contém **lógica de domínio pura**: entidades, algoritmos, funções matemáticas e regras de negócio com **absolutamente nenhum I/O**. |

---

## The Zero I/O Rule / A Regra de Zero I/O

> [!CAUTION]
> **ABSOLUTE RESTRICTION / RESTRIÇÃO ABSOLUTA**
>
> Code in this directory MUST NOT:
> - Access databases / Acessar bancos de dados
> - Make network requests / Fazer requisições de rede
> - Read/write files / Ler/escrever arquivos
> - Access system clock / Acessar relógio do sistema
> - Use UI frameworks / Usar frameworks de UI
> - Import external libraries / Importar bibliotecas externas

---

## Allowed / Permitido

✅ Language standard library only / Apenas biblioteca padrão da linguagem  
✅ Pure functions / Funções puras  
✅ Immutable data structures / Estruturas de dados imutáveis  
✅ Interfaces for external dependencies / Interfaces para dependências externas  
✅ Business rule validation / Validação de regras de negócio  
✅ Mathematical algorithms / Algoritmos matemáticos  

---

## Directory Structure / Estrutura de Diretórios

```
01_core/
├── entities/        # Domain entities / Entidades de domínio
├── algorithms/      # Pure algorithms / Algoritmos puros
└── domain/          # Business rules / Regras de negócio
```

### /entities
- Domain models / Modelos de domínio
- Value objects / Objetos de valor
- Aggregates / Agregados

### /algorithms
- Pure mathematical functions / Funções matemáticas puras
- Sorting, searching, transformations / Ordenação, busca, transformações
- Stateless computations / Computações sem estado

### /domain
- Business rule validators / Validadores de regras de negócio
- Domain services (pure) / Serviços de domínio (puros)
- Use case logic (without I/O) / Lógica de casos de uso (sem I/O)

---

## Dependency Rule / Regra de Dependência

```
01_core can import:    00_nucleo (specs as reference)
01_core CANNOT import: 02_shell, 03_infra, 04_wiring, _lab
```

---

## Example / Exemplo

```typescript
/**
 * Crystalline Lineage / Linhagem Cristalina
 * @spec 00_nucleo/specs/user-validation.md
 */

// ✅ CORRECT - Pure function / CORRETO - Função pura
export function validateEmail(email: string): boolean {
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailRegex.test(email);
}

// ❌ WRONG - Uses external dependency / ERRADO - Usa dependência externa
// import axios from 'axios'; // FORBIDDEN!
```
