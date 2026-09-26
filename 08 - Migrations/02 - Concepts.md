Terminologia
====================

## 1. Resumo da terminologia

| Termo                     | Definição resumida                                                    | Característica principal                                        |
| ------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------- |
| **Data Migration**        | Transferência de dados de uma plataforma, sistema ou banco para outro | Normalmente associada a uma mudança de ambiente                 |
| **ETL**                   | Extract, Transform, Load                                              | Os dados são transformados antes de serem carregados no destino |
| **ELT**                   | Extract, Load, Transform                                              | Os dados são carregados primeiro e transformados no destino     |
| **Data Integration**      | Integração de dados provenientes de diferentes fontes                 | Geralmente representa um processo contínuo                      |
| **Data Replication**      | Cópia/sincronização de dados entre sistemas                           | Mantém dados de origem e destino sincronizados                  |
| **CDC**                   | Change Data Capture                                                   | Captura somente as alterações ocorridas na origem               |
| **Schema Mapping**        | Correspondência entre estruturas de origem e destino                  | Define como campos/tabelas serão convertidos                    |
| **Data Transformation**   | Alteração da estrutura ou conteúdo dos dados                          | Padronização, conversão, agregação etc.                         |
| **Data Quality**          | Verificação da qualidade dos dados migrados                           | Completude, consistência, precisão e integridade                |
| **Data Validation**       | Verificação de que a migração produziu o resultado esperado           | Compara origem e destino                                        |
| **Cutover**               | Momento de mudança definitiva para o novo ambiente                    | Pode ocorrer de uma vez ou gradualmente                         |
| **Cloud Migration**       | Migração de dados/sistemas para uma plataforma de nuvem               | Ex.: on-premises → AWS                                          |
| **Database Migration**    | Migração entre bancos de dados                                        | Ex.: Oracle → PostgreSQL                                        |
| **Application Migration** | Migração relacionada a aplicações                                     | Ex.: migração de um sistema para outra plataforma               |
| **Storage Migration**     | Transferência entre sistemas de armazenamento                         | Ex.: storage local → cloud storage                              |
| **Data Warehouse**        | Ambiente estruturado para análise de dados                            | Destino frequente de processos ETL/ELT                          |
| **Data Lake**             | Repositório para dados em diferentes formatos                         | Aceita dados estruturados e não estruturados                    |
| **Data Lineage**          | Rastreamento da origem e transformação dos dados                      | Mostra o caminho percorrido pelo dado                           |
| **Reconciliation**        | Comparação dos dados de origem e destino                              | Confirma se a migração ocorreu corretamente                     |

### Uma forma simples de explicar

```text
MIGRATION
    │
    ├── ETL / ELT
    │      └── movimentar + transformar
    │
    ├── REPLICATION
    │      └── manter sincronização
    │
    ├── CDC
    │      └── capturar alterações
    │
    ├── VALIDATION
    │      └── verificar resultado
    │
    └── GOVERNANCE
           └── controlar e rastrear dados
```

---

# 2. Quadro das abordagens

**abordagem de migração não é a mesma coisa que ferramenta**.

| Abordagem                 | Como funciona                                                        | Quando utilizar                                                         |
| ------------------------- | -------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Big Bang Migration**    | Todo o ambiente é migrado de uma vez                                 | Ambientes menores ou quando uma janela de indisponibilidade é aceitável |
| **Phased Migration**      | Migração realizada por etapas                                        | Ambientes grandes e complexos                                           |
| **Parallel Migration**    | Sistemas antigo e novo funcionam simultaneamente durante a transição | Quando é necessário reduzir riscos                                      |
| **Incremental Migration** | Dados são transferidos gradualmente                                  | Grandes volumes ou necessidade de reduzir impacto                       |
| **ETL**                   | Extrai, transforma e depois carrega                                  | Quando a transformação precisa ocorrer antes do destino                 |
| **ELT**                   | Extrai, carrega e transforma no destino                              | Data warehouses/lakes modernos                                          |
| **Replication**           | Replica dados continuamente                                          | Sincronização entre ambientes                                           |
| **CDC**                   | Captura apenas alterações                                            | Migrações com baixo downtime                                            |
| **Hybrid Migration**      | Combina diferentes técnicas                                          | Projetos complexos                                                      |
| **Cloud Migration**       | Transfere dados/sistemas para cloud                                  | Modernização de infraestrutura                                          |
| **Database Migration**    | Migra estruturas e dados entre bancos                                | Troca ou modernização do SGBD                                           |

Uma maneira didática de resumir:

```text
                 ESTRATÉGIA
                     │
        ┌────────────┼────────────┐
        │            │            │
     Big Bang      Phased      Parallel
        │            │            │
        └────────────┼────────────┘
                     │
                MOVIMENTAÇÃO
                     │
             ┌───────┴───────┐
             │               │
            ETL             ELT
             │               │
             └───────┬───────┘
                     │
              SINCRONIZAÇÃO
                     │
             Replication / CDC
```

---
