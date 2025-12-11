# /02_shell — The Surface / A Superfície

> **EN**: The Crystal's Face. Everything externally touchable.  
> **PT**: A Face do Cristal. Tudo que é tocável externamente.

---

## Purpose / Propósito

| EN | PT |
|----|-----|
| This directory contains **Primary Adapters**: components that receive input from the outside world and translate it into calls to the core domain. | Este diretório contém **Adaptadores Primários**: componentes que recebem entrada do mundo externo e traduzem em chamadas para o domínio core. |

---

## What Lives Here / O Que Vive Aqui

- 🖥️ **UI Components** — React, Vue, Svelte, vanilla HTML/JS
- 🌐 **API Controllers** — REST endpoints, GraphQL resolvers
- ⌨️ **CLI Interfaces** — Command-line handlers
- 📱 **Mobile Views** — React Native, Flutter UI

---

## Directory Structure / Estrutura de Diretórios

```
02_shell/
├── ui/          # User interface components
├── api/         # REST/GraphQL controllers
└── cli/         # Command-line interfaces
```

---

## Dependency Rules / Regras de Dependência

> [!IMPORTANT]
> **CAN import / PODE importar**: `01_core`  
> **CANNOT import / NÃO PODE importar**: `03_infra`

```
✅ 02_shell → 01_core     (use domain logic)
❌ 02_shell → 03_infra    (FORBIDDEN - use 04_wiring for DI)
```

---

## The Shell Never Knows Infrastructure / A Shell Nunca Conhece Infraestrutura

| EN | PT |
|----|-----|
| Shell components should NEVER directly access databases, make network calls, or interact with the file system. They receive pre-configured services through dependency injection. | Componentes da Shell NUNCA devem acessar bancos de dados diretamente, fazer chamadas de rede ou interagir com o sistema de arquivos. Eles recebem serviços pré-configurados através de injeção de dependência. |

---

## Example / Exemplo

```typescript
/**
 * Crystalline Lineage / Linhagem Cristalina
 * @spec 00_nucleo/specs/user-registration.md
 */

// ✅ CORRECT - Imports from core / CORRETO - Importa do core
import { validateEmail } from '../../01_core/domain/validation';

// ❌ WRONG - Direct infra import / ERRADO - Import direto de infra
// import { Database } from '../../03_infra/database'; // FORBIDDEN!

export function UserRegistrationForm({ userService }) {
  // userService is injected via 04_wiring
  // userService é injetado via 04_wiring
}
```
