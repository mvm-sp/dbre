Arquitetura NoSQL
===================

Os bancos de dados NoSQL são criados especificamente para modelos de dados específicos e armazenam dados em esquemas flexíveis que são facilmente dimensionados para aplicativos modernos. Os bancos de dados NoSQL são amplamente reconhecidos por sua facilidade de desenvolvimento, funcionalidade e desempenho em escala. Esta página inclui recursos para ajudá-lo a entender melhor os bancos de dados NoSQL e a começar.

Quais são as vantagens dos bancos de dados NoSQL?
------------------------------------------

Os aplicativos modernos enfrentam vários desafios que podem ser resolvidos pelos [bancos de dados NoSQL](https://aws.amazon.com/dynamodb/). Por exemplo, os aplicativos processam um grande volume de dados de fontes diferentes, como mídia social, sensores inteligentes e bancos de dados de terceiros. Todos esses dados díspares não se encaixam perfeitamente no modelo relacional. A imposição de estruturas tabulares pode levar à redundância, à duplicação de dados e a problemas de desempenho em escala.

Os bancos de dados NoSQL são criados especificamente para modelos de dados não relacionais e têm esquemas flexíveis para a criação de aplicativos modernos. Eles são amplamente reconhecidos por sua facilidade de desenvolvimento, funcionalidade e desempenho em escala. Os benefícios dos bancos de dados NoSQL estão listados abaixo.

### Flexibilidade

Os bancos de dados NoSQL geralmente oferecem esquemas flexíveis que permitem um desenvolvimento mais rápido e iterativo. O modelo de dados flexível torna os bancos de dados NoSQL ideais para dados semiestruturados e não estruturados.

### Escalabilidade

Os bancos de dados NoSQL são normalmente projetados para escalonar usando clusters distribuídos de hardware, em vez de escalonar adicionando servidores caros e robustos. Alguns provedores de nuvem lidam com essas operações nos bastidores como um serviço totalmente gerenciado.

### Alto desempenho

Os bancos de dados NoSQL são otimizados para modelos de dados e padrões de acesso específicos. Eles permitem um desempenho mais alto do que se você estivesse tentando realizar uma funcionalidade semelhante com bancos de dados relacionais.

### Altamente funcional

Os bancos de dados NoSQL fornecem APIs altamente funcionais e tipos de dados criados especificamente para cada um de seus respectivos modelos de dados.

### Agilidade

Com a capacidade de responder a situações não planejadas, os BDs NoSQL atendem a ciclos de versão de software frequentes e são adequados para um desenvolvimento de aplicativo mais ágil e rápido.


Quais são os casos de uso dos bancos de dados NoSQL?
-----------------------------------------

É possível usar os bancos de dados NoSQL para criar uma ampla variedade de aplicativos móveis, de Internet das Coisas (IoT), de jogos e da Web de alto desempenho que proporcionam excelentes experiências de usuário em escala. A variedade de bancos de dados NoSQL e seus respectivos casos de uso são muito abrangentes. Embora seja um desafio apresentar um conjunto representativo de casos de uso, abaixo fornecemos alguns exemplos ilustrativos como pontos de partida e incentivamos você a saber mais sobre cada banco de dados NoSQL e seus respectivos casos de uso.

### Gerenciamento de dados em tempo real

É possível fornecer recomendações em tempo real, personalização e experiências de usuário aprimoradas com bancos de dados NoSQL. Por exemplo, a [Disney+] (https://www.youtube.com/watch?v=TCnmtSY2dFM) fornece sua extensa biblioteca de conteúdo digital para mais de 150 milhões de assinantes usando a tecnologia de banco de dados NoSQL. Ela pode dimensionar e fornecer recursos populares, como Continue Watching, Watchlist e Personalized Recommendations com o [Amazon DynamoDB](https://aws.amazon.com/dynamodb/).

### Segurança na nuvem

Você pode usar bancos de dados gráficos para descobrir rapidamente relações complexas em seus dados. Por exemplo, a [Wiz](https://aws.amazon.com/blogs/database/the-world-is-a-graph-how-wiz-reimagines-cloud-security-using-a-graph-in-amazon-neptune/) reimaginou a segurança na nuvem como um gráfico usando o [Amazon Neptune](https://aws.amazon.com/neptune/). A Wiz ajuda seus clientes a melhorar sua postura de segurança, identificando e corrigindo rapidamente os riscos mais críticos. Eles usam o modelo gráfico armazenado no Amazon Neptune para descobrir a combinação tóxica de fatores de risco que representam riscos críticos. Os mecanismos de risco da Wiz percorrem o gráfico e, em segundos, reúnem uma série de fatores de risco interconectados em um gráfico de segurança.

### Aplicativos de alta disponibilidade

Os bancos de dados NoSQL distribuídos são excelentes para criar aplicativos de alta disponibilidade e baixa latência para mensagens, mídias sociais, compartilhamento de arquivos e muito mais. Por exemplo, o [Snapchat](https://aws.amazon.com/solutions/case-studies/snap-dynamodb/) tem mais de 290 milhões de usuários que enviam bilhões de fotos e mensagens de vídeo diariamente. Ele usa sistemas de banco de dados NoSQL para reduzir a latência média do envio de mensagens em 20%.

Como funcionam os bancos de dados NoSQL
---------------------------

Os bancos de dados NoSQL usam uma variedade de modelos de dados para acessar e gerenciar dados. Esses tipos de bancos de dados são otimizados especificamente para aplicativos que exigem modelos de dados flexíveis, grande volume de dados e baixa latência, o que é obtido com o relaxamento de algumas das restrições de consistência de dados dos bancos de dados relacionais. Há diferenças na implementação com base no modelo de dados. Entretanto, muitos bancos de dados NoSQL usam [Javascript Object Notation (JSON)](https://aws.amazon.com/documentdb/what-is-json/), um formato aberto de intercâmbio de dados que representa os dados como uma coleção de pares nome-valor.


### Exemplo de banco de dados NoSQL

Considere este exemplo de modelagem do esquema de um banco de dados de livros simples:

* Em um banco de dados relacional, um registro de livro é frequentemente desmontado (ou "normalizado") e armazenado em tabelas separadas, e os relacionamentos são definidos por restrições de chave primária e estrangeira. Neste exemplo, a tabela **Books** tem colunas para **ISBN**, **Título do livro** e **Número da edição**; a tabela **Authors** tem colunas para **AuthorID** e **Nome do autor**; e, finalmente, a tabela **Author-ISBN** tem colunas para **AuthorID** e **ISBN**. O modelo relacional foi projetado para permitir que o banco de dados imponha a integridade referencial entre as tabelas do banco de dados, normalizado para reduzir a redundância e, em geral, otimizado para armazenamento.

![SQL](images/05-01-01.png)

* Em um banco de dados NoSQL, um registro de livro geralmente é armazenado como um documento. Para cada livro, o item, **ISBN**, **Título do livro**, **Número da edição**, **Nome do autor** e **ID do autor** são armazenados como atributos em um único documento. Nesse modelo, os dados são otimizados para desenvolvimento intuitivo e escalabilidade horizontal.

![SQL](images/05-01-02.png)

### Terminologia SQL vs. NoSQL

A tabela a seguir compara a terminologia usada por bancos de dados NoSQL selecionados com a terminologia usada por bancos de dados SQL.  

|**SQL**|**MongoDB**|**DynamoDB**|**Cassandra**|**Couchbase**|
|----|----|----|----|----|
|Table|Collection|Table|Table|Data bucket|
|Row|Document|Item|Row|Document|Column|
|Column|Field|Attribute|Colum|Field|
|Primary key|ObjectId|Partition key|Primary key|Document ID|
|Index|Index|Secondary index|Index|Index|
|View|View|Global secondary index|Materialized view|View|
|Nested table or object|Embedded document|Map|Map|Map|
|Array|Array|List|List|List|

Quais são os tipos de bancos de dados NoSQL?
-------------------------------------

Existem vários sistemas de banco de dados NoSQL diferentes devido a variações na forma como eles gerenciam e armazenam dados sem esquema. Explicamos a seguir alguns dos tipos mais comuns.

### Bancos de dados de chaves-valores

[Os bancos de dados de chave-valor](https://aws.amazon.com/nosql/key-value/) são altamente particionáveis e permitem o escalonamento horizontal em um nível que outros tipos de bancos de dados NoSQL podem não alcançar. Um banco de dados de valor-chave armazena dados como uma coleção de pares de valor-chave em que uma chave serve como um identificador exclusivo. As chaves e os valores podem ser qualquer coisa, desde objetos simples até objetos compostos complexos. Casos de uso como jogos, tecnologia de anúncios e IoT se prestam particularmente bem ao design de dados do armazenamento de valor-chave. O [Amazon DynamoDB] (https://aws.amazon.com/dynamodb/) foi projetado para oferecer desempenho consistente com latência de milissegundos de um dígito para qualquer escala de cargas de trabalho. 

### Bancos de dados de documentos

[Os bancos de dados de documentos](https://aws.amazon.com/documentdb/) têm o mesmo formato de modelo de documento que os desenvolvedores usam em seu código de aplicativo. Eles armazenam dados como objetos [JSON](https://aws.amazon.com/documentdb/what-is-json/) que são flexíveis, semiestruturados e hierárquicos por natureza. A natureza flexível, semiestruturada e hierárquica dos documentos e dos bancos de dados de documentos permite que eles evoluam de acordo com as necessidades dos aplicativos. O [modelo de banco de dados de documentos] (/nosql/document/) funciona bem com catálogos, perfis de usuários e sistemas de gerenciamento de conteúdo, em que cada documento é único e evolui com o tempo. O [Amazon DocumentDB (com compatibilidade com MongoDB)](https://aws.amazon.com/documentdb/) e o MongoDB são bancos de dados de documentos populares que oferecem APIs poderosas e intuitivas para desenvolvimento flexível e iterativo.

### Bancos de dados Graph

[Os bancos de dados de gráficos](https://aws.amazon.com/neptune/) são criados com o objetivo de facilitar a criação e a execução de aplicativos que trabalham com conjuntos de dados altamente conectados. Eles usam nós para armazenar entidades de dados e bordas para armazenar relacionamentos entre entidades. Uma borda sempre tem um nó inicial, um nó final, um tipo e uma direção. Ela pode descrever relacionamentos pai-filho, ações, propriedade e coisas do gênero. Não há limite para o número e o tipo de relacionamentos que um nó pode ter. Você pode [usar um banco de dados de gráficos] (/nosql/graph/) para criar e executar aplicativos que funcionem com conjuntos de dados altamente conectados. Os casos de uso típicos de um banco de dados de gráficos incluem redes sociais, mecanismos de recomendação, detecção de fraudes e gráficos de conhecimento. O [Amazon Neptune](https://aws.amazon.com/neptune/) é um serviço de banco de dados de gráficos totalmente gerenciado que oferece suporte ao modelo Property Graph e ao Resource Description Framework (RDF) com a opção de duas APIs de gráficos (TinkerPop e RDF/SPARQL).

### Bancos de dados na memória

Enquanto outros bancos de dados não relacionais armazenam dados em disco ou SSDs, os [armazenamentos de dados na memória](https://aws.amazon.com/nosql/in-memory/) são projetados para eliminar a necessidade de acessar discos. Eles são ideais para aplicativos que exigem tempos de resposta de microssegundos ou têm grandes picos de tráfego. Você pode usá-los em aplicativos de jogos e de tecnologia de publicidade para recursos como placares de líderes, armazenamentos de sessões e análises em tempo real. [Amazon MemoryDB for Redis](https://aws.amazon.com/memorydb/) é um serviço de banco de dados na memória durável e compatível com Redis que oferece latência de leitura de microssegundos, latência de gravação de milissegundos de um dígito e durabilidade Multi-AZ. [O Amazon ElastiCache](https://aws.amazon.com/elasticache/) é um serviço de cache na memória totalmente gerenciado, compatível com o Redis e o Memcached, para atender a cargas de trabalho de baixa latência e alta taxa de transferência. [O Amazon DynamoDB Accelerator (DAX)](https://aws.amazon.com/dynamodbaccelerator/) é outro exemplo de um armazenamento de dados criado para fins específicos que torna as leituras do DynamoDB uma ordem de magnitude mais rápidas.

### Bancos de dados de pesquisa

Um [banco de dados de mecanismo de pesquisa](https://aws.amazon.com/nosql/search/) é um tipo de banco de dados não relacional dedicado à pesquisa de conteúdo de dados, como registros de saída de aplicativos usados por desenvolvedores para solucionar problemas. Eles usam índices para categorizar características semelhantes entre os dados e facilitar a capacidade de pesquisa. Os bancos de dados de mecanismos de pesquisa são otimizados para classificar dados não estruturados, como imagens e vídeos. O [Amazon OpenSearch Service] (https://aws.amazon.com/opensearch-service/) foi criado para fornecer visualizações e análises quase em tempo real de dados gerados por máquinas, indexando, agregando e pesquisando registros e métricas semiestruturados.


Quais são as diferenças entre os bancos de dados NoSQL e SQL?
--------------------------------------------------------

Durante décadas, o modelo de dados predominante no desenvolvimento de aplicativos foi o modelo de dados relacionais, que armazenava dados em tabelas compostas de linhas e colunas. A Structured Query Language (SQL) era usada para criar e editar essas tabelas relacionais. [Os bancos de dados SQL](https://aws.amazon.com/what-is/sql/) modelam as relações de dados como tabelas. As linhas da tabela representam uma coleção de valores relacionados de um objeto ou entidade. Cada coluna da tabela representa um atributo de dados, e um campo (ou célula da tabela) armazena o valor real do atributo. É possível usar um sistema de gerenciamento de banco de dados relacional (RDBMS) para acessar os dados de várias maneiras diferentes sem reorganizar as próprias tabelas do banco de dados.

Foi somente em meados e no final dos anos 2000 que outros modelos de dados flexíveis começaram a ser adotados e utilizados de forma significativa. Para diferenciar e categorizar essas novas classes de bancos de dados e modelos de dados, foi criado o termo NoSQL. NoSQL significa não apenas SQL ou não-SQL. Muitas vezes, o termo NoSQL é usado de forma intercambiável com o termo não relacional. As principais diferenças entre os bancos de dados relacionais e não relacionais são apresentadas na tabela abaixo.

| |Bancos de dados relacionais|Bancos de dados NoSQL|
|----|----|----|
|Cargas de trabalho ideais|[Bancos de dados relacionais](https://aws.amazon.com/relational-database/) são projetados para aplicativos de processamento de transações on-line (OLTP) transacionais e fortemente consistentes. Eles também são bons para o processamento analítico on-line (OLAP).| Os bancos de dados NoSQL são projetados para vários padrões de acesso a dados que incluem aplicativos de baixa latência. Os bancos de dados de pesquisa NoSQL são projetados para análise de dados semiestruturados.|
|Modelo de dados| O modelo relacional normaliza os dados em tabelas compostas de linhas e colunas. Um esquema define estritamente as tabelas, as linhas, as colunas, os índices, as relações entre as tabelas e outros elementos do banco de dados.| Os bancos de dados NoSQL fornecem uma variedade de modelos de dados, como valor-chave, documento, gráfico e coluna, que são otimizados para desempenho e escala.|
|Propriedades ACID| Os bancos de dados relacionais oferecem propriedades de atomicidade, consistência, isolamento e durabilidade (ACID): `Atomicidade` exige que uma transação seja executada completamente ou não seja executada. `Consistência` exige que os dados estejam em conformidade com o esquema do banco de dados quando uma transação tiver sido confirmada. `Isolamento` exige que as transações simultâneas sejam executadas separadamente umas das outras. A `durabilidade` requer a capacidade de se recuperar de uma falha inesperada do sistema ou de uma queda de energia até o último estado conhecido.| A maioria dos bancos de dados NoSQL oferece compensações ao relaxar algumas das propriedades ACID dos bancos de dados relacionais em favor de um modelo de dados mais flexível que pode ser dimensionado horizontalmente. Isso torna os bancos de dados NoSQL uma excelente opção para casos de uso de alto rendimento e baixa latência que precisam ser escalonados horizontalmente além das limitações de uma única instância.|
|Desempenho| O desempenho geralmente depende do subsistema de disco. A otimização de consultas, índices e estrutura de tabelas geralmente é necessária para atingir o desempenho máximo.| O desempenho geralmente é uma função do tamanho do cluster de hardware subjacente, da latência da rede e do aplicativo de chamada.|
|Escala| os bancos de dados relacionais normalmente são escalonados com o aumento dos recursos de computação do hardware ou escalonados com a adição de réplicas para cargas de trabalho somente de leitura.|Os bancos de dados NoSQL geralmente são particionáveis. Isso ocorre porque os padrões de acesso podem ser ampliados com o uso da arquitetura distribuída para aumentar o rendimento, o que proporciona um desempenho consistente em escala quase ilimitada.|
|APIs| As solicitações para armazenar e recuperar dados são comunicadas por meio de consultas que estão em conformidade com uma linguagem de consulta estruturada (SQL). Essas consultas são analisadas e executadas pelo banco de dados relacional.|A APIs baseadas em objetos permitem que os desenvolvedores de aplicativos armazenem e recuperem estruturas de dados com facilidade. As chaves de partição permitem que os aplicativos procurem pares de valores-chave, conjuntos de colunas ou documentos semiestruturados que contenham objetos e atributos de aplicativos serializados.|

Quando você deve escolher bancos de dados NoSQL em vez de bancos de dados SQL
---------------------------------------------------------

Um banco de dados NoSQL é melhor para lidar com dados indeterminados, não relacionados ou que mudam rapidamente. Seu uso é intuitivo para os desenvolvedores quando o aplicativo determina o esquema do banco de dados. Você pode usá-lo para aplicativos que:

* Precisam de esquemas flexíveis que permitam um desenvolvimento mais rápido e iterativo.  
    
* Priorizam o desempenho em detrimento da consistência dos dados e da manutenção das relações entre as tabelas de dados (integridade referencial).
* Exigem escalonamento horizontal por meio de sharding entre servidores.
* Suporte para dados semiestruturados e não estruturados.

Você nem sempre precisa escolher entre um esquema de banco de dados não relacional e relacional. É possível empregar uma combinação de bancos de dados SQL e NoSQL em seus aplicativos. Essa abordagem híbrida é bastante comum e garante que cada carga de trabalho seja mapeada para o banco de dados correto para obter o melhor desempenho de preço.

