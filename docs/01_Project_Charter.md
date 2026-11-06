# Project Charter
## Customer Intelligence & CRM Analytics Platform

**Versão:** 0.1  
**Status:** Em elaboração  
**Categoria:** Data Engineering, Business Intelligence e Customer Analytics

---

## 1. Visão geral

O Customer Intelligence & CRM Analytics Platform é um projeto de desenvolvimento de uma plataforma analítica voltada à gestão do relacionamento com clientes.

A solução utilizará dados sintéticos, criados para representar uma empresa fictícia de varejo omnichannel, contemplando operações de vendas, marketing, atendimento e relacionamento com clientes.

A plataforma permitirá integrar, processar, armazenar e analisar dados provenientes de diferentes fontes, incluindo arquivos estruturados e APIs REST.

O objetivo é transformar dados operacionais em informações estratégicas que apoiem a tomada de decisões e a melhoria dos resultados comerciais.

## 2. Objetivo geral

Desenvolver uma plataforma de dados que permita analisar o comportamento dos clientes, avaliar o desempenho comercial, monitorar indicadores de relacionamento e identificar oportunidades de melhoria na aquisição, conversão, retenção e fidelização de clientes.

## 3. Objetivos específicos

- Construir uma base de dados sintéticos com características realistas.
- Desenvolver processos de integração de dados utilizando Python, SQL Server e SSIS.
- Consumir e integrar dados por meio de APIs REST.
- Implementar processos de ETL e validação da qualidade dos dados.
- Desenvolver um Data Warehouse com modelagem dimensional.
- Construir indicadores de CRM, vendas, marketing e atendimento.
- Analisar o funil de vendas e as taxas de conversão.
- Avaliar a satisfação dos clientes por meio de NPS e outros indicadores.
- Desenvolver análises de retenção, churn, LTV, CAC e segmentação RFM.
- Construir dashboards interativos utilizando Power BI.
- Aplicar técnicas de Machine Learning para segmentação e previsão de comportamento dos clientes.
- Disponibilizar informações analíticas por meio de uma API própria.

## 4. Contexto do negócio

A empresa fictícia atua no varejo omnichannel, comercializando produtos por diferentes canais:

- Lojas físicas.
- E-commerce.
- Aplicativo próprio.

A empresa também possui operações de marketing, vendas, atendimento ao cliente e programa de fidelidade.

Apesar de possuir dados distribuídos em diferentes sistemas, a organização enfrenta dificuldades para obter uma visão integrada dos clientes e avaliar o desempenho das suas operações.

A plataforma proposta busca solucionar esse problema por meio da integração e análise centralizada das informações.

## 5. Problemas de negócio

O projeto deverá permitir investigar questões como:

1. Qual é o perfil dos clientes e como eles se comportam?
2. Quais canais de aquisição apresentam melhores resultados?
3. Como está o desempenho do funil de vendas?
4. Quais clientes apresentam maior risco de abandono?
5. Qual é o nível de satisfação e recomendação dos clientes?
6. Quais campanhas apresentam melhor retorno?
7. Qual é o valor do ciclo de vida dos clientes?
8. Quais segmentos apresentam maior potencial de crescimento?
9. Como melhorar a retenção e a fidelização?
10. Quais oportunidades existem para aumentar a receita por cliente?

## 6. Escopo do projeto

### Incluído

- Criação de empresa e cenário de negócio fictícios.
- Geração de dados sintéticos utilizando Python.
- Integração de arquivos CSV e JSON.
- Consumo de APIs REST.
- Desenvolvimento de uma API REST própria.
- Processos de ETL e integração com SSIS.
- Banco de dados SQL Server 2022.
- Camadas RAW, STG, ODS e Data Warehouse.
- Modelagem dimensional.
- Indicadores de CRM, vendas, marketing e atendimento.
- Análise de funil de vendas.
- NPS, CSAT e CES.
- Análise RFM, LTV, CAC, churn e retenção.
- Cohort Analysis.
- Dashboards Power BI.
- Análises estatísticas e Machine Learning.
- Documentação técnica e de negócio.
- Versionamento e publicação no GitHub.

### Fora do escopo

- Implantação de um CRM comercial completo.
- Utilização de dados pessoais reais.
- Contratação de plataformas comerciais pagas como dependência obrigatória.
- Operações reais de venda ou atendimento.
- Integração com contas empresariais reais.

## 7. Arquitetura preliminar

A solução seguirá a arquitetura:

**Fontes de dados → RAW → STG → ODS → Data Warehouse → Analytics e BI**

As integrações serão realizadas por Python e SSIS, incluindo o consumo de APIs REST.

A camada analítica contemplará:

- Power BI para visualização e acompanhamento de indicadores.
- Python e Scikit-learn para análises avançadas e Machine Learning.
- FastAPI para disponibilização de informações por meio de serviços REST.

## 8. Tecnologias previstas

| Tecnologia | Aplicação |
|---|---|
| Python 3.11 | Geração, integração e processamento |
| Pandas e NumPy | Manipulação de dados |
| SQL Server 2022 | Armazenamento |
| SQL | Consultas e modelagem |
| SSIS | Integração e orquestração |
| Power BI | Visualização e indicadores |
| DAX | Medidas analíticas |
| Scikit-learn | Machine Learning |
| FastAPI | Desenvolvimento de APIs |
| Git e GitHub | Versionamento e publicação |

## 9. Resultados esperados

Ao final do projeto, espera-se obter:

- Uma base de dados sintéticos consistente e relacionada.
- Uma arquitetura de integração e processamento funcional.
- Um Data Warehouse estruturado.
- Indicadores confiáveis de desempenho comercial e relacionamento.
- Dashboards interativos.
- Modelos analíticos e preditivos.
- APIs funcionais para integração e disponibilização de dados.
- Documentação completa e repositório público no GitHub.

## 10. Critérios de sucesso

O projeto será considerado concluído quando:

- Os dados sintéticos forem gerados e validados.
- Os processos de integração e ETL forem executados corretamente.
- As APIs de integração e disponibilização estiverem funcionais.
- O Data Warehouse estiver carregado e validado.
- Os indicadores estiverem implementados e documentados.
- Os dashboards apresentarem informações consistentes.
- As análises de negócio produzirem conclusões e recomendações.
- A documentação permitir compreender e reproduzir a solução.

## 11. Diretrizes do projeto

- Priorizar dados sintéticos com comportamento realista.
- Preservar a rastreabilidade das informações.
- Aplicar boas práticas de engenharia de dados.
- Separar claramente as responsabilidades de cada camada.
- Documentar as decisões técnicas e de negócio.
- Priorizar soluções gratuitas e acessíveis.
- Manter o projeto versionado no GitHub.
- Desenvolver uma solução que represente desafios reais encontrados em ambientes corporativos.

---

**Documento:** Project Charter  
**Projeto:** Customer Intelligence & CRM Analytics Platform  
**Versão:** 0.1