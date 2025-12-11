# /04_wiring — The Energy / A Energia

> **EN**: The Connection. Where all parts come together.  
> **PT**: A Conexão. Onde todas as partes se unem.

---

## Purpose / Propósito

| EN | PT |
|----|-----|
| This directory is the **Composition Root**: the only place that knows about ALL layers and wires them together. It contains `main()`, dependency injection configuration, and environment setup. | Este diretório é o **Composition Root**: o único lugar que conhece TODAS as camadas e as conecta. Contém `main()`, configuração de injeção de dependência e setup de ambiente. |

---

## What Lives Here / O Que Vive Aqui

- ⚡ **Entry Points** — `main()`, `index.ts`, `app.py`
- 💉 **Dependency Injection** — Container configuration
- ⚙️ **Environment Config** — `.env` loaders, config objects
- 🚀 **Bootstrap Logic** — Server startup, app initialization

---

## The Only Omniscient Layer / A Única Camada Onisciente

> [!NOTE]
> This is the ONLY directory that can import from ALL numbered layers (00-03).
>
> Este é o ÚNICO diretório que pode importar de TODAS as camadas numeradas (00-03).

```
✅ 04_wiring → 00_nucleo  (read specs)
✅ 04_wiring → 01_core    (import domain)
✅ 04_wiring → 02_shell   (import UI/API)
✅ 04_wiring → 03_infra   (import implementations)
```

---

## Responsibility / Responsabilidade

| EN | PT |
|----|-----|
| 1. Read configuration from environment | 1. Ler configuração do ambiente |
| 2. Instantiate infrastructure implementations | 2. Instanciar implementações de infraestrutura |
| 3. Wire core interfaces to infra implementations | 3. Conectar interfaces do core às implementações de infra |
| 4. Inject dependencies into shell components | 4. Injetar dependências nos componentes da shell |
| 5. Start the application | 5. Iniciar a aplicação |

---

## Example / Exemplo

```typescript
/**
 * Crystalline Lineage / Linhagem Cristalina
 * @spec 00_nucleo/specs/application-bootstrap.md
 */

// Import from ALL layers / Importar de TODAS as camadas
import { IUserRepository } from '../01_core/domain/user';
import { UserController } from '../02_shell/api/user-controller';
import { PostgresUserRepository } from '../03_infra/database/postgres-user-repository';

// Environment configuration / Configuração de ambiente
const config = {
  database: {
    host: process.env.DB_HOST,
    port: parseInt(process.env.DB_PORT || '5432'),
  },
};

// Dependency Injection / Injeção de Dependência
const userRepository: IUserRepository = new PostgresUserRepository(config.database);
const userController = new UserController(userRepository);

// Bootstrap / Inicialização
export function main() {
  const app = createServer();
  app.use('/users', userController.routes);
  app.listen(3000);
}

main();
```

---

## Anti-Pattern / Anti-Padrão

> [!WARNING]
> Wiring code should be THIN. If you find yourself writing business logic here, it belongs in `01_core`.
>
> Código de wiring deve ser FINO. Se você está escrevendo lógica de negócio aqui, ela pertence ao `01_core`.
