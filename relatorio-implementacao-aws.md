# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

**Data:** 24 de Maio de 2026  
**Empresa:** Abstergo Industries  
**Responsável:** Lucas Vieira Felisberto  

---

## Introdução

Este relatório apresenta o processo de implementação de ferramentas na empresa **Abstergo Industries**, realizado por **Lucas Vieira Felisberto**. O objetivo do projeto foi elencar 3 serviços AWS com a finalidade de realizar **redução de custos imediatos**, otimizar a infraestrutura de TI e aumentar a eficiência operacional da rede de farmácias.

A Abstergo Industries é uma rede farmacêutica fictícia de médio porte que anteriormente operava com infraestrutura on-premises, enfrentando altos custos com manutenção de servidores físicos, licenças de software e equipes de TI dedicadas. A migração para a nuvem AWS foi identificada como a principal estratégia para reversão deste cenário.

---

## Descrição do Projeto

O projeto de implementação foi dividido em **3 etapas**, cada uma com objetivos específicos de redução de custo e modernização tecnológica. A seguir, são descritas as etapas do projeto:

---

### Etapa 1 — Amazon S3 (Simple Storage Service)

- **Nome da ferramenta:** Amazon S3
- **Foco da ferramenta:** Armazenamento escalável e de baixo custo na nuvem
- **Descrição do caso de uso:**

  A Abstergo Industries mantinha um servidor de arquivos físico local para armazenar receitas médicas digitalizadas, notas fiscais, relatórios de estoque, laudos e histórico de compras dos clientes. Esse servidor demandava custos elevados com hardware, energia elétrica, manutenção preventiva e um profissional dedicado para backup diário.

  Com a adoção do **Amazon S3**, todo o armazenamento foi migrado para a nuvem, utilizando a classe **S3 Standard** para arquivos de acesso frequente e **S3 Glacier Instant Retrieval** para documentos históricos com acesso esporádico. Políticas de ciclo de vida (*Lifecycle Policies*) foram configuradas para mover automaticamente os arquivos mais antigos para camadas de armazenamento mais baratas.

  **Resultados esperados:**
  - Redução de ~70% nos custos de armazenamento em comparação ao servidor local
  - Eliminação de custos com hardware, energia e manutenção física
  - Alta disponibilidade (99,999999999% de durabilidade — 11 noves)
  - Backup automático e replicação entre regiões AWS

---

### Etapa 2 — Amazon RDS (Relational Database Service)

- **Nome da ferramenta:** Amazon RDS com instâncias MySQL
- **Foco da ferramenta:** Banco de dados gerenciado como serviço (DBaaS) para redução de custos operacionais
- **Descrição do caso de uso:**

  O sistema de gestão farmacêutica da Abstergo (controle de estoque, cadastro de clientes, vendas e prescrições) rodava sobre um banco de dados MySQL instalado em um servidor físico on-premises. Essa estrutura exigia um DBA dedicado, licenças de sistema operacional e manutenção periódica de hardware, além de janelas de manutenção que causavam indisponibilidade do sistema.

  Com a migração para o **Amazon RDS for MySQL**, a gestão de patches, backups automáticos, failover e escalabilidade passaram a ser responsabilidade da AWS. Foi adotado o modelo de instâncias **Reserved Instances** com pagamento antecipado de 1 ano, o que gerou desconto de até **40%** em relação ao modelo on-demand.

  Adicionalmente, o uso do recurso **Amazon RDS Proxy** otimizou o pool de conexões do banco, reduzindo o consumo de memória das aplicações e viabilizando o uso de instâncias menores.

  **Resultados esperados:**
  - Eliminação dos custos com servidor de banco de dados físico
  - Redução de ~40% no custo de banco de dados com Reserved Instances
  - Backups automatizados e recuperação pontual (PITR) sem custo adicional
  - Alta disponibilidade com Multi-AZ e failover automático em menos de 60 segundos

---

### Etapa 3 — AWS Lambda + Amazon API Gateway

- **Nome da ferramenta:** AWS Lambda + Amazon API Gateway
- **Foco da ferramenta:** Computação serverless para processamento de eventos e integração de sistemas
- **Descrição do caso de uso:**

  A Abstergo operava um servidor de aplicação dedicado (sempre ligado, 24x7) para executar rotinas de integração entre o sistema de ponto de venda (PDV), o sistema de estoque, o SNGPC (Sistema Nacional de Gerenciamento de Produtos Controlados) e a plataforma de e-commerce da farmácia. Esse servidor apresentava ociosidade de aproximadamente 80% do tempo, gerando desperdício de recursos computacionais e custos desnecessários.

  A arquitetura foi redesenhada utilizando **AWS Lambda** para executar as funções de integração de forma *event-driven* (orientada a eventos), disparadas via **Amazon API Gateway** quando necessário — por exemplo, ao registrar uma venda, atualizar o estoque ou enviar dados ao SNGPC.

  No modelo serverless, a empresa paga apenas pelo tempo de execução das funções (medido em milissegundos), eliminando completamente o custo de um servidor sempre disponível.

  **Resultados esperados:**
  - Eliminação do custo com servidor de aplicação dedicado 24x7
  - Pagamento proporcional ao uso real (pay-per-use)
  - Escalonamento automático em períodos de alta demanda (Black Friday, campanhas sazonais)
  - Redução estimada de ~85% nos custos de computação para essas rotinas

---

## Conclusão

A implementação dos serviços AWS na empresa **Abstergo Industries** tem como resultado esperado a **significativa redução de custos operacionais de TI**, estimada em até **60% no total** ao longo do primeiro ano, quando comparada à infraestrutura on-premises anterior. Os três serviços implementados — Amazon S3, Amazon RDS e AWS Lambda + API Gateway — atuam de forma complementar, eliminando desperdícios, automatizando tarefas operacionais e garantindo alta disponibilidade dos sistemas críticos da farmácia.

Além da redução de custos imediata, a migração para a AWS posiciona a Abstergo Industries para uma evolução contínua, com acesso facilitado a serviços de **Machine Learning** (como o Amazon Rekognition para validação de receitas e o Amazon Forecast para previsão de demanda de medicamentos), **análise de dados** e **segurança avançada**, que poderão ser explorados em etapas futuras do projeto.

Recomenda-se:
1. **Monitoramento contínuo** dos custos via **AWS Cost Explorer** e configuração de alertas com **AWS Budgets**
2. **Revisão trimestral** das instâncias Reserved e ajuste de capacidade conforme o crescimento da empresa
3. **Exploração progressiva** de outros serviços AWS para automação de processos farmacêuticos, como análise de dados de vendas e personalização de ofertas para clientes

---

## Anexos

| # | Documento | Descrição |
|---|-----------|-----------|
| 1 | `arquitetura-aws-abstergo.png` | Diagrama da arquitetura AWS implementada |
| 2 | `planilha-comparativo-custos.xlsx` | Comparativo de custos on-premises vs AWS (12 meses) |
| 3 | `politica-lifecycle-s3.json` | Configuração das políticas de ciclo de vida do Amazon S3 |
| 4 | `script-migracao-rds.sql` | Scripts de migração do banco de dados para o Amazon RDS |
| 5 | `lambdas-integracao.zip` | Código-fonte das funções AWS Lambda de integração |

---

**Assinatura do Responsável pelo Projeto:**

---

**Lucas Vieira Felisberto**  
Analista de dados/ETL - Pleno  
Abstergo Industries  
Data: 24/05/2026
