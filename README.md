# README: Estudo de caso da COVID-19

---

# Sumário

1. **Introdução**
2. **Descrição dos Dados**
3. **Objetivos do Projeto**
4. **Tecnologias Utilizadas**
5. **Execução do Projeto**
6. **Recursos Compartilhados**
7. **Possíveis Melhorias Futuras**
8. **Contato**

---

# 1. Introdução
Este projeto é um estudo de caso sobre os dados da COVID-19 no Brasil, com foco em casos confirmados e óbitos por município e estado. O objetivo é utilizar ferramentas do Google Cloud Platform (GCP) para ingestão, processamento e análise de dados, além de criar um dashboard interativo no Looker Studio para visualização dos resultados.

---

# 2. Descrição dos Dados
- **Fonte:** Dados obtidos do Brasil.IO, baseados em boletins das Secretarias Estaduais de Saúde.
- **Tabelas Utilizadas:**
  - `caso`: Contém casos confirmados e óbitos por município/estado.
  - **Observação:** Inicialmente, a tabela "obito_cartorio", que registra óbitos totais e por causas específicas, foi considerada. No entanto, ao final do projeto, como a base não foi utilizada, o código foi readaptado para não importar esta tabela, visando economizar recursos.
- **Origem dos Arquivos:** Disponíveis em https://brasil.io/dataset/covid19/files/

---

# 3. Objetivos do Projeto
- **Ingestão de Dados**: Carregar a base de dados no Cloud Storage.
- **Automação**: Automatizar a ingestão e ETL.
- **Consultas SQL**: Responder as perguntas com consultas SQL no BigQuery.
- **Dashboard**: Criar um dashboard interativo no Looker Studio.

---

# 4. Tecnologias Utilizadas
- **Cloud Storage**: Armazenamento de dados.
- **Google Colab/Python**: Automação para o processamento, transformação e ingestão dos dados para o BigQuery.
- **BigQuery**: Consultas para análise dos dados.
- **Looker Studio**: Visualização de dados e geração de insights.

---

# 5. Execução do Projeto
  ### 5.1. Etapa 1: Ingestão de Dados
    - Foi realizado o download do arquivo compactado (caso.csv.gz) do site Brasil.IO.
    - Arquivo salvo no Google Drive para armazenamento e acesso.
    - Utilizado o Google Colab com Python para estruturar e transformar os dados, preparando-os para ingestão.
    - Carregamento (loading) dos dados transformados para o BigQuery, garantindo a integração com o dataset covid.
  ### 5.2. Etapa 2: Análise no BigQuery:
    - Consultas SQL desenvolvidas para responder às perguntas do cliente:
      1. Total de casos confirmados.
      2. Quantidade de casos confirmados por Estado (top 5).
      3. Letalidade (%) por Estado (top 5).
      4. Taxa de óbitos por mil habitantes por Estado (top 5).
      5. Porcentagem de municípios com óbitos em relação ao total.
      6. População total por estado, município mais populoso e representatividade populacional.
  ### 5.3. Etapa 3: Dashboard no Looker Studio:
    - Importada a base de dados do BigQuery para o Looker Studio.
    - Filtros aplicados: Data (dd/mm/yyyy), Cidade, Estado.
    - Totalizadores estáticos: Total de casos confirmados, óbitos confirmados, municípios atingidos, população total, municípios com óbitos.
    - Tabela: Data, município, estado, casos confirmados, casos por 100k habitantes, óbitos, taxa de letalidade, óbitos por 100k habitantes.
    - Gráfico: Linha representando óbitos e confirmados acumulados por dia no Brasil.
    - Análise adicional: Mapa geográfico para melhor compreensão visual do impacto social da COVID-19.
    
---

# 6. Recursos Compartilhados
  - **[Dashboard - Looker Studio](https://lookerstudio.google.com/reporting/aa3a82ee-6d6a-4a20-a876-bc40f596db8d)**
  - **[Repositório - Google Drive](https://drive.google.com/drive/folders/1xb_j0d21MzVk0JrsP64os8hvfDyqdqCZ?usp=sharing)**
  - **[Script Python - Google Colab](https://colab.research.google.com/drive/1qz9BJX1J6JzG4iQb73uf7jPnj-PFoiTr?usp=sharing)**
  - **[Resolução SQL/BigQuery - Google Documentos](https://docs.google.com/document/d/1-7zCOye4ZQGnowvWWe4Kh7ZxkDDvHrsVotKsCV17Sks/edit?usp=sharing)**

---

# 7. Possíveis Melhorias Futuras
  - **API para Dados em Streaming:** Implementar uma API para capturar e processar dados da COVID-19 em tempo real.
  - **Google Functions:** Utilizar o Cloud Functions para automatizar a extração e ingestão.
  - **Modularização no Script:** Reorganizar o script Python em módulos reutilizáveis.
  - **Otimizar o desempenho das consultas SQL:** Profissionalizar as consultas SQL, refinando a linguagem.

---

# 8. Contato
Para dúvidas ou melhorias, entre em contato pelo GitHub ou via e-mail: [enzopolisel@gmail.com](enzopolisel@gmail.com).

