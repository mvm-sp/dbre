Migração de Dados 
====================

Introdução
-----------------------------

Os `esquemas` de banco de dados definem a estrutura e as inter-relações dos dados gerenciados por bancos de dados relacionais. Embora seja importante desenvolver um esquema bem pensado no início de seus projetos, a evolução dos requisitos torna difícil ou impossível evitar alterações no esquema inicial. E como o esquema gerencia a forma e os limites dos dados, as alterações devem ser aplicadas com cuidado para corresponder às expectativas dos aplicativos que o utilizam e evitar a perda de dados atualmente mantidos pelo sistema de banco de dados.

Neste módulo, veremos o que são migrações de esquema de banco de dados, quais problemas elas resolvem e as diferentes estratégias de implementação. Daremos uma olhada nos vários pontos problemáticos que elas abordam, bem como em algumas possíveis armadilhas que elas apresentam.

O que são migrações de banco de dados?
--------------------------------------------------------------

As migrações de banco de dados, também conhecidas como [migrações de esquema](https://www.prisma.io/dataguide/intro/database-glossary#migration), migrações de esquema de banco de dados ou simplesmente migrações, são conjuntos controlados de alterações desenvolvidas para modificar a estrutura dos objetos em um [banco de dados relacional](https://www.prisma.io/dataguide/intro/database-glossary#relational-database). As migrações ajudam a fazer a transição dos esquemas de banco de dados de seu estado atual para um novo estado desejado, seja adicionando tabelas e [colunas](https://www.prisma.io/dataguide/intro/database-glossary#column), removendo elementos, dividindo campos ou alterando tipos e [restrições](https://www.prisma.io/dataguide/intro/database-glossary#constraint).

As migrações gerenciam alterações incrementais, muitas vezes reversíveis, nas estruturas de dados de forma programática. Os objetivos do software de migração de banco de dados são tornar as alterações no banco de dados repetíveis, compartilháveis e testáveis sem perda de dados. Em geral, o software de migração produz artefatos que descrevem o conjunto exato de operações necessárias para transformar um banco de dados de um estado conhecido para o novo estado. Esses artefatos podem ser verificados e gerenciados pelo software de controle de versão normal para acompanhar as alterações e compartilhá-las entre os membros da equipe.

Embora evitar a perda de dados seja geralmente um dos objetivos do software de migração, as alterações que eliminam ou modificam destrutivamente as estruturas que atualmente abrigam dados podem resultar em exclusão. Para lidar com isso, a migração geralmente é um processo supervisionado que envolve a inspeção dos scripts de alteração resultantes e a realização de quaisquer modificações necessárias para preservar informações importantes.

Quais são as vantagens das ferramentas de migração?
------------------------------------------------------------------------------------------

As migrações são úteis porque permitem que os esquemas de banco de dados evoluam à medida que os requisitos mudam. Elas ajudam os desenvolvedores a planejar, validar e aplicar com segurança as alterações de esquema em seus ambientes. Essas alterações compartimentadas são definidas em um nível granular e descrevem as transformações que devem ocorrer para a movimentação entre várias “versões” do banco de dados.

Em geral, os sistemas de migração criam artefatos ou arquivos que podem ser compartilhados, aplicados a vários sistemas de banco de dados e armazenados no controle de versão. Isso ajuda a construir um histórico de modificações no banco de dados que pode estar intimamente ligado às alterações de código que o acompanham nos aplicativos clientes. O esquema do banco de dados e as suposições do aplicativo sobre essa estrutura podem evoluir em conjunto.

Alguns outros benefícios incluem a possibilidade (e, às vezes, a necessidade) de ajustar manualmente o processo, separando a geração da lista de operações da execução das mesmas. Cada alteração pode ser auditada, testada e modificada para garantir que os resultados corretos sejam obtidos, ao mesmo tempo em que se conta com a automação para a maior parte do processo.

Quais são algumas das desvantagens das ferramentas de migração?
--------------------------------------------------------------------------------------------------

Os sistemas de migração têm suas falhas, mas, felizmente, a maioria delas pode ser atenuada por meio de processos e supervisão.

Como as migrações modificam as estruturas de banco de dados existentes, é preciso tomar cuidado para evitar a perda de dados. Isso pode ser causado por suposições incorretas feitas pelas ferramentas ou por transformações que exigem uma compreensão do significado por trás das estruturas de dados. Embora possa ser tentador presumir que os arquivos de migração gerados estejam corretos, como os arquivos de migração se referem principalmente às estruturas de dados, é sua responsabilidade garantir que os dados também sejam preservados ou transformados corretamente.

As migrações também podem não dar certo se forem aplicadas a um banco de dados que esteja em um estado diferente do presumido. Por exemplo, isso pode acontecer quando são feitas alterações na estrutura do banco de dados fora dos limites do sistema de migração ou quando as migrações são aplicadas na ordem errada. Todos os sistemas de migração dependem da compreensão do estado atual do banco de dados para modificar corretamente as estruturas existentes. Se o estado real divergir do estado presumido, as migrações podem falhar ou podem alterar o banco de dados de maneiras indesejáveis.

Outro possível problema com as migrações é que elas costumam ser muito específicas da ferramenta. Os sistemas de migração geram artefatos que representam o estado dos bancos de dados ou as alterações necessárias. Embora algumas ferramentas produzam resultados em SQL simples, às vezes elas codificam detalhes adicionais para a ferramenta analisar nos comentários ou podem usar formatos especiais de nome de arquivo para indicar a ordem. Pode ser difícil alternar entre as ferramentas de migração sem que haja uma ruptura clara entre a geração anterior e a atual de arquivos de migração.

Migrações baseadas em estado vs. mudança
---------------------------------------------------------------------

Há dois tipos principais de estratégias de transformação de esquema empregadas pelo software de migração: migrações baseadas em estado e migrações baseadas em alterações. Qualquer uma delas pode ser usada com eficiência para gerenciar o processo e, às vezes, é útil empregar uma combinação de ambas. Os pontos fortes de cada abordagem, no entanto, geralmente determinam qual é a mais adequada para um projeto, com base na adequação ao estilo de desenvolvimento da equipe envolvida.

### Migrações baseadas em estado

O software de migração baseado em estado cria artefatos que descrevem como recriar o estado desejado do banco de dados a partir do zero. Os arquivos que ele produz podem ser aplicados a um sistema de banco de dados relacional vazio para atualizá-lo completamente.

Depois que os artefatos que descrevem o estado desejado são criados, a migração real envolve a comparação dos arquivos gerados com o estado atual do banco de dados. Esse processo permite que o software analise a diferença entre os dois estados e gere um ou mais arquivos novos para alinhar o esquema atual do banco de dados com o esquema descrito pelos arquivos. Essas operações de alteração são então aplicadas ao banco de dados para atingir o estado de meta.

#### O que ter em mente com as migrações baseadas em estado

Como quase todas as migrações, os arquivos de migração baseados em estado devem ser cuidadosamente examinados por desenvolvedores experientes para supervisionar o processo. Tanto os arquivos que descrevem o estado final desejado quanto os arquivos que descrevem as operações para colocar o banco de dados atual em conformidade devem ser revisados para garantir que as transformações não levarão à perda de dados. Por exemplo, se as operações geradas tentarem renomear uma tabela excluindo a tabela atual e recriando-a com o novo nome, uma pessoa experiente deverá reconhecer esse fato e intervir para evitar a perda de dados.

As migrações baseadas em estado podem parecer um tanto desajeitadas se houver grandes alterações frequentes no esquema do banco de dados que exijam esse tipo de intervenção manual. Devido a essa sobrecarga, essa técnica costuma ser mais adequada para cenários em que o esquema é bem pensado com antecedência, com mudanças fundamentais que ocorrem com pouca frequência.

No entanto, as migrações baseadas em estado têm a vantagem de produzir arquivos que descrevem totalmente o estado do banco de dados em um único contexto. Isso pode ajudar os novos desenvolvedores a se integrarem mais rapidamente e funciona bem com fluxos de trabalho em sistemas de controle de versão, pois as alterações conflitantes introduzidas por ramificações de código podem ser resolvidas facilmente.

### Migrações baseadas em alterações

A principal alternativa às migrações baseadas em estado é um sistema de migração baseado em alterações. As migrações baseadas em alterações também produzem arquivos que alteram as estruturas existentes em um banco de dados para chegar ao estado desejado. Em vez de descobrir as diferenças entre o estado desejado do banco de dados e o atual, essa abordagem se baseia em um estado conhecido do banco de dados para definir as operações que o levarão ao novo estado. Arquivos de migração sucessivos são produzidos para modificar ainda mais o banco de dados, criando uma série de arquivos de alteração que podem reproduzir o estado final do banco de dados quando aplicados consecutivamente.

Como as migrações baseadas em alterações funcionam delineando as operações necessárias de um estado de banco de dados conhecido para o desejado, é necessária uma cadeia ininterrupta de arquivos de migração a partir do ponto de partida inicial. Esse sistema requer um estado inicial, que pode ser um sistema de banco de dados vazio ou um arquivo que descreva a estrutura inicial, os arquivos que descrevem as operações que levam o esquema a cada transformação e uma ordem definida na qual os arquivos de migração devem ser aplicados.

#### O que ter em mente com as migrações baseadas em mudanças

As migrações baseadas em alterações rastreiam a proveniência do design do esquema do banco de dados até a estrutura original por meio da série de scripts de transformação que ele cria. Isso pode ajudar a ilustrar a evolução da estrutura do banco de dados, mas é menos útil para entender o estado completo do banco de dados em um determinado momento, pois as alterações descritas em cada arquivo modificam a estrutura produzida pelo último arquivo de migração.

Como o estado anterior é muito importante para os sistemas baseados em alterações, o sistema geralmente usa um banco de dados dentro do próprio sistema de banco de dados para rastrear quais arquivos de migração foram aplicados. Isso ajuda o software a entender em que estado o sistema está no momento, sem precisar analisar a estrutura atual e compará-la com o estado desejado, conhecido apenas pela compilação de toda a série de arquivos de migração.

A desvantagem dessa abordagem é que o estado atual do banco de dados não é descrito na base de código após o ponto inicial. Cada arquivo de migração se baseia no anterior, portanto, embora as alterações sejam bem compartimentadas, é muito mais difícil raciocinar sobre o estado completo do banco de dados em um determinado ponto. Além disso, como a ordem das operações é muito importante, pode ser mais difícil resolver conflitos produzidos por desenvolvedores que fazem alterações conflitantes.

Os sistemas baseados em alterações, no entanto, têm a vantagem de permitir alterações rápidas e iterativas na estrutura do banco de dados. Em vez do processo demorado de analisar o estado atual do banco de dados, compará-lo com o estado desejado, criar arquivos para executar as operações necessárias e aplicá-las ao banco de dados, os sistemas baseados em alterações assumem o estado atual do banco de dados com base nas alterações anteriores. Isso geralmente torna as alterações mais leves, mas torna as alterações fora da banda no banco de dados especialmente perigosas, pois as migrações podem deixar os sistemas de destino em um estado indefinido.

Como você usa as migrações de banco de dados?
--------------------------------------------------------------------------

Agora que já apresentamos as duas principais classes de sistemas de migração, vamos dar uma olhada em como você realmente usa essas ferramentas durante o desenvolvimento, a implementação e a colaboração de aplicativos.

### Durante o desenvolvimento

As migrações de banco de dados tornam-se potencialmente relevantes a partir do momento em que você faz a primeira modificação no esquema de dados inicial. Na verdade, a maioria das ferramentas de migração gera arquivos de migração para trazer um banco de dados relacional de um estado completamente vazio para o esquema inicial.

À medida que você desenvolve o aplicativo, a forma dos dados que deseja armazenar, os requisitos do sistema de banco de dados e os detalhes específicos que deseja preservar mudam com frequência. Isso pode acontecer à medida que você compreende melhor o espaço do problema ou quando recursos adicionais exigem dados adicionais ou um layout diferente das informações atuais. É importante definir essas alterações de esquema à medida que elas ocorrem durante o desenvolvimento para garantir que os artefatos sejam sincronizados e implantados com o código associado.

O armazenamento e o gerenciamento de arquivos de migração com a base de código associada permitem que as alterações no esquema do banco de dados passem pelo mesmo processo de revisão que as alterações de código recebem. Conforme mencionado anteriormente, as migrações baseadas em estado podem facilitar esse processo, pois os conflitos entre o estado desejado ficam aparentes com a comparação dos arquivos. Os sistemas baseados em alterações requerem mais cuidado e resolução prática quando ocorrem conflitos, pois a ordenação é importante e toda a estrutura de dados não é visível em nenhum dos arquivos de migração iterativa.

Em geral, a prática recomendada é ser conservador na maneira como você define as alterações no banco de dados em desenvolvimento e lembrar que suas alterações poderão ser executadas em dados de produção. Isso é especialmente importante para alterações destrutivas. Deve-se considerar opções mais seguras para a exclusão, como renomear colunas em vez de excluí-las, realizar exclusões “suaves” ao cancelar a publicação dos dados em vez de removê-los ou copiar estruturas de dados ao transformá-los em vez de sobrescrevê-los.

Em outras palavras, as migrações de esquema de banco de dados são uma das alterações que você manterá com as alterações de código. As migrações de esquema geralmente devem ser consideradas em conjunto com as alterações de código para garantir que todas as alterações sejam documentadas e aplicáveis ao design atual do banco de dados.

### Durante o teste e a implantação

Depois que as migrações forem criadas, você geralmente as implantará em ambientes cada vez mais importantes para garantir que funcionem conforme o esperado e que todos os requisitos do seu código sejam atendidos. Embora você provavelmente tenha desenvolvido e aplicado as migrações em um ambiente de desenvolvimento, provavelmente precisará testá-las em ambientes adicionais com dados, integrações e cargas mais realistas, assim como faria com as alterações de código.

Nesse ponto, você precisa garantir que os arquivos de migração sejam aplicados de forma limpa ao banco de dados de destino, que o estado de destino inicial compartilhe a estrutura e as suposições que você tinha ao desenvolver os arquivos de migração e que os dados mantidos pelo banco de dados não sejam afetados negativamente pelas alterações que você está fazendo. Uma combinação de verificações manuais e automatizadas pode ser realizada para confirmar que esses requisitos foram atendidos.

Depois que as alterações tiverem sido validadas como seguras e funcionais nos ambientes de preparação, elas poderão estar prontas para serem aplicadas aos sistemas de banco de dados de produção. Antes de aplicar as migrações aos sistemas de produção, é importante considerar a realização de um backup completo dos dados atuais, caso uma cópia recente não esteja disponível no momento. Os backups são vitais para o caso de a migração ter consequências imprevistas ou se as diferenças entre os ambientes de preparação e de produção causarem perda de dados.

Como escolher as melhores ferramentas de migração
---------------------------------------------------------------------------------

Considerando todas as informações que abordamos até agora, como você realmente decide sobre as soluções de migração mais adequadas para seus projetos? Há várias considerações diferentes que você pode usar para restringir suas melhores escolhas.

Às vezes, a linguagem da base de código, a estrutura de desenvolvimento ou o backend do banco de dados que você está usando sugerem fortemente as ferramentas que você deve usar para gerenciar as migrações. Por exemplo, embora muitas vezes não sejam requisitos rígidos, muitas estruturas da Web incluem seus próprios sistemas de migração para gerenciar o esquema de seus bancos de dados de apoio. Esses sistemas geralmente têm boa integração com o restante das ferramentas da estrutura e podem ajudar a reduzir o atrito do gerenciamento das alterações no banco de dados como um processo separado.

Outra consideração que pode afetar sua seleção é o nível de maturidade e a quantidade de suporte fornecido para uma determinada ferramenta. Como mencionamos acima, os arquivos de migração produzidos por várias ferramentas tendem a não ser diretamente compatíveis entre si, embora possam ser aplicados diretamente como SQL puro. A escolha de uma opção estável pode ajudá-lo a evitar cenários em que uma ferramenta caia em desuso e não seja mais mantida, forçando-o a alterar o processo de migração no meio do desenvolvimento.

Outro ponto que você talvez queira considerar é o formato dos artefatos de migração reais. Se eles forem arquivos SQL bem formatados e bem organizados, você provavelmente poderá confiar na capacidade de entender as alterações que os arquivos produzem. Da mesma forma, se as migrações forem escritas na linguagem de programação que o restante do seu projeto estiver usando, o significado poderá ser fácil de analisar e exigir menos mudança de contexto de outras tarefas de desenvolvimento. Evite ferramentas que produzam arquivos de migração difíceis de entender ou modificar manualmente.

Outro fator em sua decisão pode envolver recursos adicionais fornecidos pelos sistemas de migração. Algumas ferramentas oferecem excelente integração com outras ferramentas ou oferecem opções flexíveis, como a capacidade de esmagar arquivos de migração baseados em alterações anteriores em um arquivo de estado de “ponto de verificação”. As ferramentas têm suporte variável para inspecionar falhas de migração ou reverter alterações quando ocorrem problemas. Seus requisitos e sua filosofia de desenvolvimento podem afetar quais desses recursos são necessários.

_fonte : https://www.prisma.io/_