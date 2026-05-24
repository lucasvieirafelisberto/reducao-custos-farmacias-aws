# 💊 Redução dos Custos em Farmácias com AWS

<p align="center">
  <img src="https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white"/>
  <img src="https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white"/>
  <img src="https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white"/>
  <img src="https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge"/>
</p>

---

## 📋 Sobre o Projeto

Projeto desenvolvido como parte do bootcamp **DIO + Totvs — Fundamentos de Engenharia de Dados e Machine Learning**.

O desafio consiste em conceber e projetar uma solução de infraestrutura em nuvem para uma farmácia fictícia (**Abstergo Industries**), utilizando serviços da **AWS** com foco em **redução de custos operacionais imediatos**, substituindo uma infraestrutura on-premises custosa e pouco escalável.

---

## 🏢 Contexto da Empresa

| Campo | Detalhe |
|-------|---------|
| **Empresa** | Abstergo Industries |
| **Segmento** | Rede Farmacêutica |
| **Problema** | Alta infraestrutura on-premises com servidores físicos, alto custo de manutenção e baixa escalabilidade |
| **Solução** | Migração para serviços gerenciados AWS com modelo pay-as-you-go |

---

## ☁️ Serviços AWS Implementados

### 🗂️ Etapa 1 — Amazon S3
> Armazenamento escalável e de baixo custo na nuvem

Substituiu o servidor de arquivos físico local utilizado para armazenar receitas digitalizadas, notas fiscais, relatórios e histórico de clientes.

- ✅ Classe **S3 Standard** para arquivos de acesso frequente
- ✅ Classe **S3 Glacier Instant Retrieval** para documentos históricos
- ✅ **Lifecycle Policies** para movimentação automática entre camadas
- 💰 Redução estimada de **~70%** nos custos de armazenamento

---

### 🗄️ Etapa 2 — Amazon RDS (MySQL)
> Banco de dados gerenciado como serviço (DBaaS)

Substituiu o servidor de banco de dados físico que controlava estoque, vendas, clientes e prescrições da farmácia.

- ✅ **Reserved Instances** com desconto de até 40%
- ✅ **Multi-AZ** para alta disponibilidade e failover automático
- ✅ **Amazon RDS Proxy** para otimização de conexões
- ✅ Backups automáticos com recuperação pontual (PITR)
- 💰 Redução estimada de **~40%** nos custos de banco de dados

---

### ⚡ Etapa 3 — AWS Lambda + Amazon API Gateway
> Computação serverless para integração de sistemas

Substituiu um servidor de aplicação dedicado 24x7 (com ~80% de ociosidade) que fazia integrações entre PDV, estoque, SNGPC e e-commerce.

- ✅ Arquitetura **event-driven** (orientada a eventos)
- ✅ Pagamento apenas pelo tempo de execução real
- ✅ Escalonamento automático em picos de demanda
- 💰 Redução estimada de **~85%** nos custos de computação

---

## 📊 Resumo de Resultados

| Serviço | Substituiu | Redução de Custo |
|---------|-----------|-----------------|
| Amazon S3 | Servidor de arquivos físico | ~70% |
| Amazon RDS | Servidor de banco de dados on-premises | ~40% |
| AWS Lambda + API Gateway | Servidor de aplicação 24x7 | ~85% |
| **Total geral** | **Infraestrutura on-premises** | **~60% no primeiro ano** |

---

## 🚀 Próximos Passos Recomendados

- [ ] Monitoramento de custos com **AWS Cost Explorer** e **AWS Budgets**
- [ ] Exploração de **Amazon Rekognition** para validação de receitas médicas
- [ ] Uso de **Amazon Forecast** para previsão de demanda de medicamentos
- [ ] Análise de dados de vendas com **Amazon QuickSight**

---

## 📁 Estrutura do Repositório

```
reducao-custos-farmacias-aws/
│
├── README.md                          # Este arquivo
└── relatorio-implementacao-aws.md     # Relatório técnico completo do projeto
```

---

## 🛠️ Tecnologias Utilizadas

![Amazon S3](https://img.shields.io/badge/Amazon%20S3-569A31?style=flat&logo=amazons3&logoColor=white)
![Amazon RDS](https://img.shields.io/badge/Amazon%20RDS-527FFF?style=flat&logo=amazonrds&logoColor=white)
![AWS Lambda](https://img.shields.io/badge/AWS%20Lambda-FF9900?style=flat&logo=awslambda&logoColor=white)
![Amazon API Gateway](https://img.shields.io/badge/Amazon%20API%20Gateway-FF4F8B?style=flat&logo=amazonapigateway&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)

---

## 👨‍💻 Autor

<table>
  <tr>
    <td align="center">
      <b>Lucas Vieira Felisberto</b><br/>
      Analista de dados/ETL - Pleno <br/>
    </td>
  </tr>
</table>

---

## 📚 Referências

- [Documentação Amazon S3](https://docs.aws.amazon.com/s3/)
- [Documentação Amazon RDS](https://docs.aws.amazon.com/rds/)
- [Documentação AWS Lambda](https://docs.aws.amazon.com/lambda/)
- [AWS Pricing Calculator](https://calculator.aws/)
- [DIO — Digital Innovation One](https://www.dio.me)

---

<p align="center">
  Feito como desafio para o bootcamp TOTVS - Fundamentos de Engenharia de Dados e Machine Learning <strong>DIO + Totvs</strong>
</p>
