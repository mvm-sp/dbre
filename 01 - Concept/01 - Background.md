
Como nasceu o DBRE
=====================

Em uma análise prévia da recente evolução da Implementação, manutenção e gestão de plataformas nos ambientes corporativos, percebemos que as necessidades se tornaram complexas, a demanda por soluções robustas, confiáveis, com alto grau de resiliência, com maior nível de disponibilidade e o menor custo possível tornou-se o tema principal nas discussões sobre engenharia de software moderna. Neste cenário, novas disciplinas e frameworks estão surgindo para aperfeiçoar os processos de construção, publicação e gerenciamento de aplicações, tais como [DevOps](https://www.atlassian.com/br/devops), [SRE](https://www.redhat.com/pt-br/topics/devops/what-is-sre) e [FinOps](https://learn.microsoft.com/pt-br/azure/cost-management-billing/finops/overview-finops) entre tantas. 

Origem é o SRE
----------------

Uma das disciplinas básicas para entendermos a abrangência das técnicas de **DBRE** (_Database Reliability Engineer_) é a **SRE**(_Site Reliability Engineer_), portanto vamos ter uma breve aproximação dos conceitos envolvidos;

#### O que é SRE:

Site Reliability Engineering (SRE) ou engenharia de confiabilidade de sites é uma abordagem da engenharia de software para gerenciar sistemas e automatizar tarefas operacionais de TI. Em resumo, a disciplina de `SRE` tem como objetivo aplicar técnicas que proporcionem um produto final (aplicação que o cliente vai consumir) com garantias de um grau mínimo de falhas. A aplicação, então, recebe a qualificação de `confiável`

Os engenheiros de confiabilidade, originalmente, a partir do ambiente de inovação do [Google®](https://sre.google/sre-book/table-of-contents/) iniciaram os estudos de confiabilidade de plataformas e definiram que e disciplina possue alguns pilares

#### [Pilares do SRE](#pilares-do-sre):
*   [Embracing Risk](https://sre.google/sre-book/embracing-risk/)
*   [Service Level Objectives](https://sre.google/sre-book/service-level-objectives/)
*   [Eliminating Toil](https://sre.google/sre-book/eliminating-toil/) 
*   [Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/)
*   [Release Engineering](https://sre.google/sre-book/release-engineering/)
*   [Simplicity](https://sre.google/sre-book/simplicity/)
  
```
Recentemente outros engenheiros adicionáram um capítulo de Observability aos pilares de SRE, 
o link a seguir trás mais detalhes a respeito.
```

[Observability](https://www.redhat.com/pt-br/topics/devops/what-is-observability) é hoje um dos capitulos relacionados a disciplina `SRE`.