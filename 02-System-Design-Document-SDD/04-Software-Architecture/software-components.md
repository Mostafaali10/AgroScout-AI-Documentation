# Software Component Architecture

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Layered package and module organization.

## Clean Architecture Layers

- **Domain Layer**: Entities, Value Objects, Domain Exceptions, Repository Interfaces.
- **Use Case / Application Layer**: Business orchestrators, Command/Query handlers.
- **Infrastructure Layer**: Database models, ORM mappings, HTTP clients, external API adapters.
- **Presentation / API Layer**: FastAPI routers, Pydantic schemas, Flutter screens & state widgets.
