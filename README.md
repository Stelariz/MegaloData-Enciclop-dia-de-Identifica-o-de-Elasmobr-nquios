# 🦈 MegaloData: Enciclopédia de Identificação de Elasmobrânquios

O **MegaloData** é um projeto de sistema de catálogo e identificação biológica especializado em tubarões e raias. O objetivo principal é fornecer uma estrutura de dados robusta para que pesquisadores possam identificar espécies através de características morfológicas, genéticas e de habitat.

Este repositório documenta a **fase de planejamento e arquitetura** do software, simulando o estágio pré-desenvolvimento.

---

## 🌍 Por que o MegaloData é Vital?

A criação de uma enciclopédia digital estruturada para elasmobranquios vai além de um simples catálogo. Ela é fundamental por três pilares principais:

### 1. Conservação e Monitoramento de Espécies
Muitas espécies de tubarões estão em risco de extinção. Ter um sistema que permite cruzar dados de **Habitat** e **Taxonomia** ajuda ONGs e Governos a identificar áreas de proteção prioritárias. Sem dados estruturados, a ciência é lenta; com o MegaloData, a informação é acionável.

### 2. Integridade Científica vs. Caos de Dados
Dados biológicos costumam estar dispersos em planilhas não normalizadas. O MegaloData resolve isso aplicando **Normalização de Banco de Dados (3NF)**, garantindo que uma alteração em uma Família Biológica se propague corretamente para todas as Espécies vinculadas, evitando redundâncias e erros de catálogo.

### 3. Identificação em Tempo Real
Ao estruturar chaves de busca baseadas em **Morfologia** (dentes, nadadeiras, fendas branquiais), o sistema funciona como uma ferramenta de apoio para pesquisadores em campo, permitindo a identificação rápida através de parâmetros técnicos pré-definidos.

---

## 🏗️ Estrutura do Sistema

O sistema foi desenhado seguindo uma arquitetura multicamadas, focando na integridade referencial dos dados taxonômicos.

### 📊 Modelagem de Dados (MER)
A base do projeto reside em um banco de dados relacional (SQL) para garantir que a hierarquia biológica seja respeitada:
* **Reinos/Ordens/Famílias:** Tabelas com relacionamentos `1:N`.
* **Espécies:** Entidade central com chaves estrangeiras para tabelas de morfologia.
* **Habitats:** Relacionamento `N:N` com espécies (uma espécie pode habitar vários oceanos).

### 🛠️ Tech Stack Planejada
* **Documentação:** Markdown / Mermaid.js (Diagramas).
* **Banco de Dados:** MySQL ou PostgreSQL.
* **Gestão de Projeto:** Kanban via GitHub Projects.
* **Qualidade (QA):** Cypress para testes de API e validação de schema.

---

## 📋 Requisitos do Projeto

### Funcionais (RF)
- [ ] **RF01:** O sistema deve permitir a busca de espécies por filtros morfológicos (ex: número de fendas branquiais).
- [ ] **RF02:** O sistema deve validar a unicidade do Nome Científico.
- [ ] **RF03:** O sistema deve permitir o upload de coordenadas geográficas de avistamento.

### Não-Funcionais (RNF)
- [ ] **RNF01:** A integridade referencial deve ser mantida via Foreign Keys (FK).
- [ ] **RNF02:** O sistema deve responder a consultas complexas de cruzamento de dados em menos de 200ms.

---

## 🧪 Estratégia de Qualidade (QA)

Como o MegaloData lida com dados científicos, a precisão é crítica. O plano de testes foca em:
1.  **Data Integrity Testing:** Scripts SQL para garantir que não existam "espécies órfãs" sem família definida.
2.  **API Validation:** Garantir que os inputs de dados (JSON) sigam estritamente o modelo de dados definido.
3.  **Boundary Testing:** Validar se os limites de habitat (profundidade, temperatura) aceitam apenas valores realistas.

---

## 🚀 Próximos Passos (Backlog)

Estes itens serão transformados em **Cards de Desenvolvimento** no GitHub Projects:
1.  Definição do DDL (Data Definition Language) para criação das tabelas iniciais.
2.  Mapeamento de Constraints (Check Constraints para tipos de dentes e nadadeiras).
3.  Criação de massa de dados (Seed) para as 5 principais ordens de tubarões.
4.  Desenho dos Mockups de interface para o módulo de busca avançada.

---
*Projeto acadêmico para a disciplina de Estrutura de Software da 2ª turma do curso de Big Data para Indústria - FATEC São Carlos.*
