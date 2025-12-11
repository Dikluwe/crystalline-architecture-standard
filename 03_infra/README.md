# /03_infra — The Support / O Suporte

> **EN**: The Physical World. The "Dirty" layer that talks to external systems.  
> **PT**: O Mundo Físico. A camada "Suja" que fala com sistemas externos.

---

## Purpose / Propósito

| EN | PT |
|----|-----|
| This directory contains **Secondary Adapters**: implementations of interfaces defined in `01_core` that interact with the physical world. | Este diretório contém **Adaptadores Secundários**: implementações de interfaces definidas em `01_core` que interagem com o mundo físico. |

---

## What Lives Here / O Que Vive Aqui

- 🗃️ **Database Adapters** — PostgreSQL, MongoDB, Redis clients
- 🌐 **Network Clients** — HTTP clients, WebSocket connections
- 📁 **File System** — File readers/writers, storage services
- 🔌 **External APIs** — Third-party service integrations
- 🖥️ **Hardware Drivers** — GPU, sensors, peripherals

---

## Directory Structure / Estrutura de Diretórios

```
03_infra/
├── database/       # Database adapters
├── filesystem/     # File system operations
└── network/        # Network clients and APIs
```

---

## Dependency Rules / Regras de Dependência

> [!IMPORTANT]
> **CAN import / PODE importar**: `01_core`  
> **CANNOT import / NÃO PODE importar**: `02_shell`

```
✅ 03_infra → 01_core     (implement interfaces from core)
❌ 03_infra → 02_shell    (FORBIDDEN - never import UI)
```

---

## Dependency Inversion Principle / Princípio de Inversão de Dependência

| EN | PT |
|----|-----|
| Infra implements interfaces defined in Core. Core defines WHAT it needs; Infra defines HOW to provide it. | Infra implementa interfaces definidas no Core. Core define O QUE precisa; Infra define COMO fornecer. |

```
01_core: interface IUserRepository { findById(id): User }
03_infra: class PostgresUserRepository implements IUserRepository { ... }
```

---

## Example / Exemplo

```typescript
/**
 * Crystalline Lineage / Linhagem Cristalina
 * @spec 00_nucleo/specs/user-persistence.md
 * @contract 00_nucleo/contracts/user-repository.md
 */

// ✅ CORRECT - Implements interface from core
import { IUserRepository, User } from '../../01_core/domain/user';

export class PostgresUserRepository implements IUserRepository {
  constructor(private pool: Pool) {}
  
  async findById(id: string): Promise<User | null> {
    const result = await this.pool.query(
      'SELECT * FROM users WHERE id = $1',
      [id]
    );
    return result.rows[0] ? this.toEntity(result.rows[0]) : null;
  }
}
```
