# Eugine Agolla

**Backend & Payments Infrastructure Engineer** · Nairobi, Kenya

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/eugine-agolla/)
[![Medium](https://img.shields.io/badge/Medium-000000?style=flat&logo=medium&logoColor=white)](https://medium.com/@agollaeugine)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:agollaeugine@gmail.com)

I build financial backends that stay correct under concurrency: idempotent payment ingestion, double-entry ledgers, and database-enforced invariants in PostgreSQL.

- **Focus:** concurrency control (row-level locking, unique-constraint idempotency), double-entry accounting, reconciliation, event-driven workflows.
- **Ask me about:** PostgreSQL locking behaviour, idempotency key design, testing race conditions against a real database.
- **Open to:** Roles in backend and payments infrastructure.

---

### Stack
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="Java" height="20"/>
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat&logo=springboot&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat&logo=sqlalchemy&logoColor=white)
![Alembic](https://img.shields.io/badge/Alembic-6BA539?style=flat)
![Celery](https://img.shields.io/badge/Celery-37814A?style=flat&logo=celery&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat&logo=laravel&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Pytest](https://img.shields.io/badge/Pytest-0A9EDC?style=flat&logo=pytest&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)

Also comfortable with: Node.js, MySQL, MongoDB, Elasticsearch, AWS, Vue.js, React.

---

### Featured projects

#### [Idempotent Payment Ingestion Engine](https://github.com/E-ugine/idempotent-ingestion-engine)
Exactly-once payment processing under simultaneous duplicate requests, network retries, and mid-transaction crashes.

- **Idempotency at the database layer:** a unique constraint makes Postgres arbitrate between concurrent duplicates, with no application-side locks.
- **Crash recovery:** a two-step reserve/complete flow with SHA-256 request fingerprinting (so a reused key with a different payload is rejected) and staleness-bound polling to recover requests orphaned by a server failure.
- **Tenant isolation:** idempotency keys are scoped per account, so cross-tenant collisions are impossible by design and don't depend on key randomness.
- **Verified with:** a threaded test suite that fires genuinely simultaneous requests at a real PostgreSQL instance.

`FastAPI` `PostgreSQL` `SQLAlchemy` `Alembic` `Pytest`

#### [Double-Entry Ledger](https://github.com/E-ugine/double-entry-accounting-ledger)
An accounting ledger whose debit/credit invariants hold even if the application layer is bypassed.

- **Invariants in the database:** four PostgreSQL triggers block unbalanced postings, direct-insert bypasses, and changes to finalized transactions.
- **Fast reads, checkable truth:** a cached balance column serves reads, and an independent SQL reconciliation function detects drift between the cache and the ledger.
- **Tests run on real migrations:** the test database is built from the same Alembic migrations as production. This caught a trigger-induced timestamp gap that ORM-generated test schemas missed.

`FastAPI` `PostgreSQL` `SQLAlchemy` `Alembic` `Pytest`

---
### GitHub activity

<p align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=E-ugine&show_icons=true&hide_border=true&include_all_commits=true&count_private=true" alt="GitHub stats" height="165"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=E-ugine&layout=compact&hide_border=true" alt="Top languages" height="165"/>
</p>

<p align="left">
  <img src="https://streak-stats.demolab.com?user=E-ugine&hide_border=true" alt="GitHub streak"/>
</p>
