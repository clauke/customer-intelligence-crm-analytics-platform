# Requisitos Não Funcionais
## Customer Intelligence & CRM Analytics Platform

**Versão:** 0.1  
**Status:** Em elaboração  
**Projeto:** Customer Intelligence & CRM Analytics Platform

---

## 1. Objetivo

Este documento estabelece os requisitos não funcionais da plataforma Customer Intelligence & CRM Analytics Platform, definindo critérios de qualidade, desempenho, segurança, confiabilidade, manutenção e disponibilidade que deverão ser observados durante o desenvolvimento da solução.

Os requisitos não funcionais complementam os requisitos funcionais, estabelecendo como a plataforma deverá operar e quais padrões deverá atender.

## 2. Escopo

Os requisitos abrangem os seguintes aspectos:

- Desempenho e eficiência.
- Segurança e proteção de dados.
- Qualidade e integridade dos dados.
- Confiabilidade e disponibilidade.
- Manutenibilidade e organização do código.
- Escalabilidade.
- Interoperabilidade e integração.
- Usabilidade e documentação.
- Reprodutibilidade e versionamento.
- Custos e utilização de ferramentas gratuitas.

## 3. Requisitos Não Funcionais

### 3.1. Desempenho e Eficiência

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF001 | Os processos de ingestão e transformação deverão executar de forma eficiente, considerando o volume de dados sintéticos definido para o projeto. | Os processos deverão concluir sem consumo excessivo de recursos e sem falhas por limitações evitáveis de memória. |
| RNF002 | As consultas SQL deverão ser estruturadas para oferecer desempenho adequado às análises. | Consultas críticas deverão utilizar filtros, junções e índices de forma apropriada. |
| RNF003 | As consultas disponibilizadas pela API própria deverão apresentar tempos de resposta adequados ao ambiente local. | Os endpoints deverão ser testados e seus tempos de resposta registrados. |
| RNF004 | Os processos de carga deverão evitar reprocessamentos desnecessários. | A estratégia de carga deverá considerar controle de lotes, identificadores e histórico de execução. |

### 3.2. Segurança e Proteção de Dados

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF005 | As integrações deverão utilizar mecanismos de autenticação compatíveis com os cenários simulados. | Implementar autenticação por API Key ou Bearer Token, conforme o cenário. |
| RNF006 | Credenciais, tokens e demais informações sensíveis não deverão ser armazenados diretamente no código-fonte. | Utilizar variáveis de ambiente e arquivos locais protegidos pelo `.gitignore`. |
| RNF007 | O acesso ao banco de dados deverá utilizar credenciais e permissões apropriadas. | As conexões deverão utilizar configurações externas ao código e permissões compatíveis com cada operação. |
| RNF008 | A API própria deverá validar os parâmetros recebidos nas requisições. | Entradas inválidas deverão ser rejeitadas com respostas HTTP apropriadas. |
| RNF009 | As consultas ao banco de dados deverão utilizar mecanismos que reduzam riscos de SQL Injection. | Utilizar consultas parametrizadas e validação das entradas. |
| RNF010 | Os dados utilizados no projeto deverão ser sintéticos, sem exposição intencional de informações pessoais reais. | Os dados gerados deverão representar clientes fictícios e não deverão conter dados pessoais reais. |
| RNF011 | Os arquivos de configuração local e credenciais não deverão ser publicados no GitHub. | Revisar o `.gitignore` e verificar os arquivos antes dos commits. |

### 3.3. Qualidade e Integridade dos Dados

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF012 | Os dados deverão manter consistência entre as diferentes camadas da arquitetura. | As transformações deverão preservar as regras de negócio e os relacionamentos definidos. |
| RNF013 | As cargas deverão possuir mecanismos de identificação e rastreabilidade. | Registrar informações como data de carga, origem, lote e status de processamento, conforme aplicável. |
| RNF014 | Os processos deverão identificar registros duplicados e inconsistências. | Implementar verificações de duplicidade, campos obrigatórios e integridade referencial. |
| RNF015 | Os dados utilizados nas análises deverão passar por verificações de qualidade. | Validar completude, consistência, unicidade e validade dos dados relevantes. |
| RNF016 | As regras de tratamento de dados ausentes deverão ser documentadas. | Registrar os critérios de preenchimento, exclusão ou manutenção de valores ausentes. |
| RNF017 | As métricas analíticas deverão seguir definições de negócio padronizadas. | Documentar fórmulas, critérios e períodos utilizados no cálculo dos indicadores. |

### 3.4. Confiabilidade e Disponibilidade

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF018 | Os processos de integração deverão possuir tratamento de erros. | Falhas de conexão, respostas inválidas e erros de processamento deverão ser identificados e registrados. |
| RNF019 | As chamadas às APIs deverão possuir limites de tempo de espera. | Implementar timeout configurável nas requisições. |
| RNF020 | As integrações deverão prever tentativas controladas de reexecução em caso de falhas temporárias. | Implementar mecanismo de retry com intervalo progressivo, quando aplicável. |
| RNF021 | Os processos deverão gerar registros de execução. | Registrar início, término, status, quantidade de registros processados e mensagens de erro. |
| RNF022 | As cargas deverão permitir identificar execuções incompletas ou malsucedidas. | Utilizar status de processamento e identificadores de lote. |
| RNF023 | A solução deverá permitir a execução e validação dos processos em ambiente local. | Os componentes deverão funcionar no ambiente de desenvolvimento documentado, sem depender de serviços comerciais externos. |

### 3.5. Manutenibilidade e Organização

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF024 | O código Python deverá seguir uma estrutura organizada e modular. | Separar responsabilidades em módulos e diretórios específicos. |
| RNF025 | Os scripts deverão possuir nomes claros e padronizados. | Adotar convenção de nomenclatura consistente em todo o projeto. |
| RNF026 | O código deverá apresentar comentários e documentação quando necessário. | Documentar funções, regras de negócio e trechos de maior complexidade. |
| RNF027 | As regras de transformação e os cálculos analíticos deverão ser documentados. | Manter documentação atualizada dos principais processos e indicadores. |
| RNF028 | A solução deverá permitir a manutenção e evolução de seus componentes sem alterações desnecessárias em outras partes. | Adotar separação de responsabilidades entre ingestão, transformação, armazenamento, analytics e API. |
| RNF029 | Os scripts deverão utilizar configurações externas sempre que apropriado. | Evitar caminhos absolutos e parâmetros de ambiente fixos diretamente no código. |

### 3.6. Escalabilidade

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF030 | A arquitetura deverá permitir a inclusão de novas fontes de dados. | Novas fontes deverão poder ser incorporadas sem necessidade de reconstrução completa da solução. |
| RNF031 | A estrutura de dados deverá permitir a inclusão de novas entidades e indicadores. | A modelagem deverá permitir evolução controlada das estruturas analíticas. |
| RNF032 | Os processos de integração deverão suportar crescimento do volume de registros. | Utilizar estratégias de processamento e carga adequadas ao volume de dados. |
| RNF033 | A API própria deverá permitir a inclusão de novos endpoints. | A estrutura da aplicação deverá permitir expansão organizada dos recursos disponibilizados. |

### 3.7. Interoperabilidade e Integração

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF034 | As integrações deverão utilizar padrões amplamente adotados no mercado. | Utilizar HTTP/HTTPS, APIs REST e formatos JSON quando aplicáveis. |
| RNF035 | Os dados recebidos pelas APIs deverão ser compatíveis com os processos de ingestão. | Implementar validação e tratamento das estruturas JSON recebidas. |
| RNF036 | As integrações deverão considerar paginação e limites de requisição. | Implementar mecanismos de paginação e tratamento de respostas HTTP 429 quando aplicável. |
| RNF037 | A API própria deverá disponibilizar documentação dos endpoints. | Utilizar OpenAPI e interface Swagger para consulta e testes. |
| RNF038 | Os componentes deverão permitir comunicação entre Python, SQL Server, SSIS e Power BI. | Validar a integração entre as tecnologias previstas na arquitetura. |
| RNF039 | As integrações externas deverão utilizar serviços simulados sob controle do projeto. | Disponibilizar APIs locais que representem sistemas de CRM, vendas, marketing e atendimento, sem dependência de provedores comerciais. |

### 3.8. Usabilidade e Documentação

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF040 | Os dashboards deverão apresentar informações de maneira clara e intuitiva. | Utilizar títulos, indicadores, filtros e elementos visuais consistentes. |
| RNF041 | Os indicadores deverão possuir definições acessíveis aos usuários. | Documentar significado, fórmula e finalidade dos KPIs. |
| RNF042 | A documentação técnica deverá ser organizada e atualizada. | Manter documentação em arquivos Markdown no repositório. |
| RNF043 | A execução dos processos deverá possuir instruções claras. | Documentar dependências, configurações e comandos necessários. |
| RNF044 | A documentação da API deverá facilitar a compreensão e utilização dos recursos. | Apresentar endpoints, parâmetros, autenticação, exemplos de requisição e respostas. |

### 3.9. Reprodutibilidade e Versionamento

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF045 | O ambiente de desenvolvimento deverá possuir dependências documentadas. | Manter o arquivo `requirements.txt` atualizado. |
| RNF046 | Os processos de geração e transformação deverão produzir resultados reproduzíveis, considerando os mesmos parâmetros e sementes aleatórias quando aplicáveis. | Documentar e controlar sementes e parâmetros utilizados na geração de dados e experimentos. |
| RNF047 | O código-fonte deverá ser versionado utilizando Git e GitHub. | Manter histórico de commits organizado e repositório atualizado. |
| RNF048 | Alterações relevantes deverão ser registradas na documentação. | Atualizar documentos e informações de versão conforme a evolução do projeto. |
| RNF049 | Os experimentos de Machine Learning deverão possuir parâmetros e métricas registrados. | Documentar os dados utilizados, configurações, métricas e resultados dos modelos. |

### 3.10. Custos e Ferramentas

| ID | Requisito | Critério de aceitação |
|---|---|---|
| RNF050 | O desenvolvimento deverá utilizar ferramentas gratuitas ou recursos já disponíveis no ambiente da desenvolvedora. | Não exigir contratação de licenças, planos pagos ou serviços comerciais adicionais. |
| RNF051 | As integrações deverão funcionar sem exigir contas corporativas ou estudantis. | Utilizar APIs locais simuladas e recursos que não dependam desse tipo de conta. |
| RNF052 | O projeto deverá evitar dependência obrigatória de infraestrutura em nuvem paga. | Permitir execução e demonstração da solução em ambiente local. |
| RNF053 | As ferramentas e bibliotecas utilizadas deverão possuir condições de uso compatíveis com o projeto. | Registrar as principais tecnologias e suas respectivas licenças quando aplicável. |

## 4. Diretrizes Gerais

Além dos requisitos individuais, deverão ser observadas as seguintes diretrizes:

1. Priorizar soluções gratuitas, de código aberto ou já disponíveis no ambiente de desenvolvimento.
2. Utilizar dados sintéticos para representar cenários empresariais realistas.
3. Evitar dependência de plataformas externas que exijam contratação de serviços.
4. Priorizar processamento local e integração entre os componentes da arquitetura.
5. Manter separação entre código-fonte, dados, configurações e documentação.
6. Adotar práticas de segurança e qualidade desde as primeiras etapas de desenvolvimento.
7. Registrar decisões técnicas e alterações relevantes ao longo do projeto.

## 5. Critérios Gerais de Aceitação

A plataforma será considerada aderente aos requisitos não funcionais quando:

- Os processos de ingestão, transformação e carga forem executados com rastreabilidade e tratamento de erros.
- Os dados apresentarem consistência e integridade entre as camadas.
- As integrações REST contemplarem autenticação, validação, paginação e tratamento de falhas, conforme aplicável.
- A API própria disponibilizar endpoints documentados e testáveis.
- Os componentes apresentarem organização, documentação e possibilidade de manutenção.
- Os dashboards apresentarem indicadores consistentes e compreensíveis.
- O ambiente permitir a reprodução dos principais processos e experimentos.
- A solução puder ser desenvolvida e demonstrada sem contratação de ferramentas ou serviços adicionais.

## 6. Considerações Finais

Os requisitos não funcionais estabelecidos neste documento orientam as decisões técnicas e a implementação da plataforma Customer Intelligence & CRM Analytics Platform.

Eles deverão ser considerados durante todas as etapas do projeto, podendo ser revisados e complementados conforme novas necessidades forem identificadas.

---

**Projeto:** Customer Intelligence & CRM Analytics Platform
**Documento:** Requisitos Não Funcionais  
**Versão:** 0.1