O que é Cloud Storage?
======================

O armazenamento em nuvem é um modo de armazenamento de dados de computador no qual os dados digitais são armazenados em servidores em locais externos. Os servidores são mantidos por um provedor terceirizado que é responsável por hospedar, gerenciar e proteger os dados armazenados em sua infraestrutura. O provedor garante que os dados em seus servidores estejam sempre acessíveis por meio de conexões de Internet públicas ou privadas.

O armazenamento em nuvem permite que as organizações armazenem, acessem e mantenham os dados de modo que não precisem possuir e operar seus próprios data centers, transferindo as despesas de um modelo de gasto de capital para um modelo operacional. O armazenamento em nuvem é escalonável, permitindo que as organizações expandam ou reduzam sua área de cobertura de dados, dependendo da necessidade. 


Como funciona o armazenamento em nuvem?
----------------------------

O armazenamento em nuvem usa servidores remotos para salvar dados, como arquivos, dados comerciais, vídeos ou imagens. Os usuários fazem upload dos dados para os servidores por meio de uma conexão com a Internet, onde eles são salvos em uma máquina virtual em um servidor físico. Para manter a disponibilidade e oferecer redundância, os provedores de nuvem geralmente distribuem os dados em várias máquinas virtuais em data centers localizados em todo o mundo. Se as necessidades de armazenamento aumentarem, o provedor de nuvem ativará mais máquinas virtuais para lidar com a carga. Os usuários podem acessar os dados no Cloud Storage por meio de uma conexão com a Internet e de um software, como portal da Web, navegador ou aplicativo móvel, por meio de uma interface de programação de aplicativos (API).

O Cloud Storage está disponível em quatro modelos diferentes:

### Público

O armazenamento em nuvem pública é um modelo em que uma organização armazena dados nos data centers de um provedor de serviços que também são utilizados por outras empresas. Os dados no armazenamento em nuvem pública estão espalhados por várias regiões e geralmente são oferecidos por assinatura ou pagamento conforme o uso. O armazenamento em nuvem pública é considerado “elástico”, o que significa que os dados armazenados podem ser ampliados ou reduzidos de acordo com as necessidades da organização. Os provedores de nuvem pública normalmente disponibilizam os dados de qualquer dispositivo, como um smartphone ou um portal da Web.

### Privado

O armazenamento em nuvem privada é um modelo em que uma organização utiliza seus próprios servidores e data centers para armazenar dados em sua própria rede. Como alternativa, as organizações podem negociar com provedores de serviços em nuvem para fornecer servidores dedicados e conexões privadas que não são compartilhadas por nenhuma outra organização. As nuvens privadas são normalmente utilizadas por organizações que exigem mais controle sobre seus dados e têm requisitos rigorosos de conformidade e segurança.

### Híbrida

Um modelo de nuvem híbrida é uma combinação de modelos de armazenamento em nuvem pública e privada. Um modelo de armazenamento em nuvem híbrida permite que as organizações decidam quais dados desejam armazenar em qual nuvem. Dados confidenciais e dados que precisam atender a requisitos rigorosos de conformidade podem ser armazenados em uma nuvem privada, enquanto dados menos confidenciais são armazenados na nuvem pública. Um modelo de armazenamento em nuvem híbrida geralmente tem uma camada de orquestração para integrar as duas nuvens. Uma nuvem híbrida oferece flexibilidade e permite que as organizações ainda aumentem a escala com a nuvem pública, se necessário. 

### Multicloud

Um modelo de armazenamento multicloud é quando uma organização configura mais de um modelo de nuvem de mais de um provedor de serviços em nuvem (pública ou privada). As organizações podem optar por um modelo multinuvem se um fornecedor de nuvem oferecer determinados aplicativos proprietários, se a organização exigir que os dados sejam armazenados em um país específico, se várias equipes forem treinadas em nuvens diferentes ou se a organização precisar atender a requisitos diferentes que não estejam declarados nos contratos de nível de serviço dos prestadores de serviços. Um modelo de várias nuvens oferece flexibilidade e redundância às organizações.


Vantagens do armazenamento em nuvem
---------------------------

### Custo total de propriedade

O armazenamento em nuvem permite que as organizações passem de um modelo de despesas de capital para um modelo de despesas operacionais, permitindo que elas ajustem os orçamentos e os recursos rapidamente.

### Elasticidade

O armazenamento em nuvem é elástico e dimensionável, o que significa que ele pode ser ampliado (mais armazenamento adicionado) ou reduzido (menos armazenamento necessário), dependendo das necessidades da organização. 

### Flexibilidade

O armazenamento em nuvem oferece às organizações flexibilidade sobre como armazenar e acessar dados, implementar e orçar recursos e arquitetar sua infraestrutura de TI.  

### Segurança

A maioria dos provedores de nuvem oferece segurança robusta, incluindo segurança física nos data centers e segurança de ponta nos níveis de software e aplicativos. Os melhores provedores de nuvem oferecem [arquitetura de confiança zero](https://cloud.google.com/learn/what-is-zero-trust?hl=pt-BR), gerenciamento de identidade e [acesso](https://cloud.google.com/iam) e [criptografia](https://cloud.google.com/security-key-management).

### Sustentabilidade

Um dos maiores custos ao operar data centers locais é a sobrecarga do consumo de energia. Os melhores provedores de nuvem [operam com energia sustentável](https://cloud.google.com/sustainability) por meio de recursos renováveis.

### Redundância

A redundância (replicação de dados em vários servidores em diferentes locais) é uma característica inerente às nuvens públicas, permitindo que as organizações se recuperem de desastres e, ao mesmo tempo, mantenham a continuidade dos negócios.


Soluções de Armazenamento de Dados na Nuvem
--------------------------------------------

### AWS (Amazon Web Services)
#### Soluções de Armazenamento de Dados
1. **Amazon S3 (Simple Storage Service)**
   - **Descrição:** Serviço de armazenamento de objetos para qualquer quantidade de dados.
   - **Uso:** Dados não estruturados, backups, arquivos de mídia, big data.

2. **Amazon EBS (Elastic Block Store)**
   - **Descrição:** Armazenamento em bloco para instâncias EC2.
   - **Uso:** Sistemas de arquivos, bancos de dados, aplicações críticas.

3. **Amazon EFS (Elastic File System)**
   - **Descrição:** Sistema de arquivos elástico para múltiplas instâncias EC2.
   - **Uso:** Armazenamento compartilhado, Big Data, servidores de aplicativos.


#### Bancos de Dados Relacionais
1. **Amazon RDS (Relational Database Service)**
   - **Descrição:** Serviço gerenciado para bancos de dados relacionais (MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Amazon Aurora).
   - **Uso:** Aplicações web, ERP, CRM.

2. **Amazon Aurora**
   - **Descrição:** Banco de dados relacional compatível com MySQL e PostgreSQL.
   - **Uso:** Aplicações empresariais críticas, SaaS, alta disponibilidade.

#### Bancos de Dados Não Relacionais
1. **Amazon DynamoDB**
   - **Descrição:** Banco de dados NoSQL rápido e flexível para documentos e chave-valor.
   - **Uso:** Aplicações web e móveis, jogos, IoT.

2. **Amazon DocumentDB**
   - **Descrição:** Banco de dados NoSQL compatível com MongoDB.
   - **Uso:** Aplicações que usam MongoDB, sistemas de gerenciamento de conteúdo.

### Azure (Microsoft Azure)
#### Soluções de Armazenamento de Dados
1. **Azure Blob Storage**
   - **Descrição:** Armazenamento de objetos para grandes quantidades de dados não estruturados.
   - **Uso:** Aplicações móveis e web, distribuição de conteúdo, backup.

2. **Azure Disk Storage**
   - **Descrição:** Armazenamento em bloco de alta performance para máquinas virtuais.
   - **Uso:** Máquinas virtuais, bancos de dados, aplicações críticas.

3. **Azure Files**
   - **Descrição:** Serviço de compartilhamento de arquivos na nuvem via SMB.
   - **Uso:** Compartilhamento de arquivos entre máquinas virtuais e serviços.

4. **Azure Archive Storage**
   - **Descrição:** Armazenamento de arquivamento de baixo custo para longo prazo.
   - **Uso:** Retenção de dados regulamentares, arquivamento de dados.

#### Bancos de Dados Relacionais
1. **Azure SQL Database**
   - **Descrição:** Banco de dados relacional gerenciado baseado no SQL Server.
   - **Uso:** Aplicações web, ERP, CRM.

2. **Azure Database for MySQL/PostgreSQL/MariaDB**
   - **Descrição:** Bancos de dados relacionais gerenciados compatíveis com MySQL, PostgreSQL e MariaDB.
   - **Uso:** Aplicações web e móveis, bancos de dados empresariais.

#### Bancos de Dados Não Relacionais
1. **Azure Cosmos DB**
   - **Descrição:** Banco de dados NoSQL distribuído globalmente compatível com várias APIs.
   - **Uso:** Aplicações com baixa latência, alta disponibilidade e escalabilidade global.

2. **Azure Table Storage**
   - **Descrição:** Armazenamento NoSQL para grandes quantidades de dados estruturados.
   - **Uso:** Dados de catálogos, logs, armazenamento chave-valor.

### Google Cloud Platform (GCP)
#### Soluções de Armazenamento de Dados
1. **Google Cloud Storage**
   - **Descrição:** Armazenamento de objetos unificado para desenvolvedores e empresas.
   - **Uso:** Dados não estruturados, backup, distribuição de conteúdo.

2. **Persistent Disks**
   - **Descrição:** Armazenamento em bloco de alta performance para máquinas virtuais.
   - **Uso:** Dados para instâncias de máquinas virtuais, bancos de dados.

3. **Filestore**
   - **Descrição:** Sistema de arquivos gerenciado e escalável.
   - **Uso:** Compartilhamento de arquivos entre instâncias de máquinas virtuais.

4. **Google Cloud Archive Storage**
   - **Descrição:** Armazenamento de arquivamento de baixo custo para longo prazo.
   - **Uso:** Retenção de dados a longo prazo, arquivamento de dados.

#### Bancos de Dados Relacionais
1. **Cloud SQL**
   - **Descrição:** Banco de dados relacional gerenciado compatível com MySQL, PostgreSQL e SQL Server.
   - **Uso:** Aplicações web, ERP, CRM.

2. **Cloud Spanner**
   - **Descrição:** Banco de dados relacional distribuído globalmente com escalabilidade horizontal.
   - **Uso:** Aplicações críticas, jogos, bancos de dados globais.

#### Bancos de Dados Não Relacionais
1. **Firestore**
   - **Descrição:** Banco de dados NoSQL para desenvolvimento de aplicativos, integrado ao Firebase.
   - **Uso:** Aplicações móveis e web, sincronização em tempo real.

2. **Bigtable**
   - **Descrição:** Banco de dados NoSQL altamente escalável.
   - **Uso:** Análise de dados, IoT, aplicativos financeiros.

Essas soluções abrangem uma ampla gama de necessidades de armazenamento e gerenciamento de dados, permitindo que as empresas escolham a melhor opção para suas especificidades.

### IBM Cloud
#### Soluções de Armazenamento de Dados
1. **IBM Cloud Object Storage**
   - **Descrição:** Serviço de armazenamento de objetos escalável e durável para grandes quantidades de dados não estruturados.
   - **Uso:** Backup e recuperação, arquivamento de dados, distribuição de conteúdo.

2. **IBM Cloud Block Storage**
   - **Descrição:** Armazenamento em bloco de alta performance para instâncias de máquinas virtuais.
   - **Uso:** Sistemas de arquivos, bancos de dados, aplicações de alta performance.

3. **IBM Cloud File Storage**
   - **Descrição:** Sistema de arquivos escalável e de alto desempenho para armazenamento compartilhado.
   - **Uso:** Compartilhamento de arquivos entre máquinas virtuais, big data, servidores de aplicativos.

4. **IBM Cloud Archive Storage**
   - **Descrição:** Armazenamento de arquivamento de baixo custo para retenção de dados a longo prazo.
   - **Uso:** Arquivamento de dados, compliance, backup de longo prazo.

#### Bancos de Dados Relacionais
1. **IBM Db2 on Cloud**
   - **Descrição:** Banco de dados relacional totalmente gerenciado, com alta disponibilidade e recuperação de desastres.
   - **Uso:** Aplicações empresariais, ERP, CRM, análises de dados.

2. **IBM Cloud Databases for PostgreSQL/MySQL**
   - **Descrição:** Bancos de dados relacionais gerenciados compatíveis com PostgreSQL e MySQL.
   - **Uso:** Aplicações web, móveis, bancos de dados empresariais.

#### Bancos de Dados Não Relacionais
1. **IBM Cloudant**
   - **Descrição:** Banco de dados NoSQL baseado em Apache CouchDB para aplicações que requerem escalabilidade horizontal e alta disponibilidade.
   - **Uso:** Aplicações móveis, IoT, aplicativos web que necessitam de sincronização offline.

2. **IBM Cloud Databases for MongoDB**
   - **Descrição:** Banco de dados NoSQL gerenciado compatível com MongoDB.
   - **Uso:** Aplicações de documentos JSON, gerenciamento de conteúdo, aplicações móveis e web.

