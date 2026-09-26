Ferramentas 
====================

# 1. Quadro das ferramentas


| Ferramenta                           | Categoria principal          | Característica                                      |
| ------------------------------------ | ---------------------------- | --------------------------------------------------- |
| **Domo**                             | Data Integration / Analytics | Integração e disponibilização de dados para análise |
| **Airbyte**                          | Data Integration / ELT       | Conectores para movimentação de dados               |
| **Fivetran**                         | Data Integration / ELT       | Pipelines gerenciados e automatizados               |
| **Informatica PowerCenter**          | ETL / Data Integration       | Plataforma tradicional de integração de dados       |
| **Talend Data Integration**          | ETL / Data Integration       | Integração e transformação de dados                 |
| **Qlik Replicate**                   | Data Replication / CDC       | Replicação contínua e captura de alterações         |
| **Oracle GoldenGate**                | Replication / CDC            | Replicação de dados em tempo real                   |
| **Google Cloud DMS**                 | Database Migration           | Migração de bancos para Google Cloud                |
| **Azure Database Migration Service** | Database Migration           | Migração de bancos para Azure                       |
| **AWS Database Migration Service**   | Database Migration           | Migração e replicação de bancos para AWS            |


> **Não devemos comparar essas ferramentas como se todas fossem concorrentes diretas.**

Por exemplo:

**Airbyte / Fivetran**

```text
Fontes → Pipeline → Destino
```

são mais associados à **integração/movimentação de dados**.

Enquanto:

**Qlik Replicate / GoldenGate**

```text
Banco Origem
     │
     │ CDC
     ▼
Banco Destino
```

são fortemente associados à **replicação e CDC**.

E:

**AWS DMS / Azure DMS / Google Cloud DMS**

```text
Banco A
   │
   │ Migration Service
   ▼
Banco B / Cloud
```

são voltados especificamente para **migração de bancos de dados**.

---

# 2. Descrição resumida das ferramentas

### 2.1 Domo

A **Domo** combina integração, preparação, gerenciamento e análise de dados em uma plataforma orientada à disponibilização das informações para usuários de negócio.

**Papel no contexto:**

```text
Fontes → Integração → Dados → Analytics
```

É interessante apresentar a Domo como uma **plataforma mais ampla de dados e analytics**, e não simplesmente como uma ferramenta de migração.

---

### 2.2 Airbyte

O **Airbyte** é uma plataforma de movimentação e integração de dados baseada em conectores.

Sua função conceitual pode ser representada por:

```text
Fonte A ─┐
Fonte B ─┼──→ Airbyte ──→ Destino
Fonte C ─┘
```

É particularmente interessante no contexto de **ELT moderno**, em que os dados podem ser carregados e posteriormente transformados.

---

### 4.3 Fivetran

O **Fivetran** é uma plataforma de integração de dados orientada à automação dos pipelines.

Conceitualmente:

```text
Sistemas de origem
       │
       ▼
    Fivetran
       │
       ▼
Data Warehouse / Lake
```

Um dos seus conceitos importantes é reduzir a quantidade de desenvolvimento necessário para manter pipelines de ingestão.

---

### 2.4 Informatica PowerCenter

O **PowerCenter**, da Informatica, representa uma abordagem tradicional de **ETL e integração de dados corporativos**.

```text
Extract
   ↓
Transform
   ↓
Load
```

É um exemplo importante para explicar a evolução das arquiteturas de integração: plataformas ETL tradicionais versus ferramentas modernas de ELT e cloud.

---

### 2.5 Talend Data Integration

O **Talend Data Integration** também está associado à integração e transformação de dados.

Pode ser utilizado para construir fluxos envolvendo:

```text
Extract
   ↓
Transform
   ↓
Validate
   ↓
Load
```

É útil no material principalmente como exemplo de plataforma de **ETL/Data Integration**.

---

### 2.6 Qlik Replicate

O **Qlik Replicate** está associado à **replicação de dados e CDC**.

A ideia central é:

```text
Banco Origem
     │
     │ alterações
     ▼
    CDC
     │
     ▼
Banco Destino
```

Em vez de necessariamente mover todo o banco repetidamente, a tecnologia pode trabalhar com as alterações ocorridas na origem.

---

### 2.7 Oracle GoldenGate

O **Oracle GoldenGate** é uma tecnologia de replicação e movimentação de dados, especialmente conhecida pelo suporte a cenários de **replicação contínua e baixa latência**.

Conceitualmente:

```text
SOURCE
   │
   │ Change Data
   ▼
GoldenGate
   │
   ▼
TARGET
```

É um exemplo importante quando o assunto é **migração com necessidade de reduzir downtime**.

---

### 2.8 Google Cloud Database Migration Service

O **Google Cloud Database Migration Service** é direcionado à migração de bancos de dados para o ambiente Google Cloud.

O conceito é:

```text
Database
   │
   ▼
Google Cloud DMS
   │
   ▼
Google Cloud
```

É importante diferenciá-lo das plataformas genéricas de integração: aqui o foco é **database migration**.

---

### 2.9 Azure Database Migration Service

O **Azure Database Migration Service** fornece recursos para migração de bancos de dados para o ecossistema Azure.

Conceitualmente:

```text
Source Database
       │
       ▼
Azure DMS
       │
       ▼
Azure Database
```

É um exemplo de serviço gerenciado de migração dentro de um provedor de cloud.

---

### 2.10 AWS Database Migration Service

O **AWS Database Migration Service (DMS)** é o serviço da AWS para migração e replicação de bancos de dados.

A arquitetura conceitual é:

```text
Source
Database
   │
   ▼
 AWS DMS
   │
   ├── Migração inicial
   │
   └── CDC
        │
        ▼
 Target
 Database
```
