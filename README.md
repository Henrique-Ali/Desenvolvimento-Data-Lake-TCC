# Desenvolvimento-Data-Lake-TCC

## **Visão Geral do Projeto**
Neste projeto, desenvolvemos uma arquitetura de Data Lake para demonstrar os desafios e soluções no gerenciamento e análise de dados em larga escala. Utilizando uma abordagem flexível e escalável, nosso Data Lake integra dados de diversas fontes, permitindo o armazenamento e processamento eficiente de informações estruturadas e não estruturadas.

O projeto abrange desde os fundamentos teóricos até a implementação prática, detalhando técnicas de armazenamento, limpeza e processamento de dados. Esperamos que este trabalho contribua para a compreensão dos benefícios e desafios do uso de Data Lakes na tomada de decisões estratégicas, proporcionando maior flexibilidade e capacidade de análise de dados.

## Detalhes Técnicos
A abordagem de um Data Lake permite que os dados sejam segregados em camadas, nas quais é possível aplicar técnicas distintas de transformação dos dados, com intuito de tornar escalável as cargas de processamento e dispor de dados em diferentes estágios de manipulação para possibilitar diferentes usos dessas informações simultaneamente.

## Arquitetura do Data Lake
A arquitetura do Data Lake desenvolvida neste projeto é ilustrada no diagrama abaixo:

![Arquitetura](https://github.com/Henrique-Ali/Desenvolvimento-Data-Lake-TCC/blob/main/imagens/DiagramaArquitetura.png)

1. ### Fonte de Dados (Origem):
   * API: API externa que fornece dados climáticos de várias regiões do Brasil.
   * Banco de Dados On-Premises: Banco de dados relacional que armazena informações ambientais e sociais.

1. ### Ingestão:

   * AWS Lambda: Periodicamente consulta a API externa, coletando informações referentes ao clima em pontos dispersos pelo Brasil.
   * AWS Database Migration Service (DMS): Serviço que facilita a migração de dados de bancos de dados on-premises para a nuvem AWS.
     
1. ### Armazenamento:
   * Amazon S3:
      * Crus: Armazena dados no formato original, preservando sua integridade.
      * Tratados: Os dados são limpos, transformados e estruturados para análises específicas.
      * Analítico: Consolida os resultados analíticos para visualizações e insights.

      Cada camada impõe restrições de acesso para garantir a segurança e integridade dos dados.

1. ### Processamento

   O processamento envolve várias operações sequenciais, respeitando a estrutura e tipo de arquivo. Inclui:

   * Aplicação de regras de negócio para garantir a precisão e consistência dos dados.
   * Limpeza de dados para remover inconsistências e erros.
   * Conversão de formatos para garantir compatibilidade.
   * Agregação de dados para criar conjuntos mais abrangentes e úteis para análises.

   Serviços:

      * Amazon DynamoDB: Armazena as regras de limpeza, desde a formatação de tipos de dados até a remoção de valores específicos e substituição de pontuações, em tabelas dedicadas.
      * AWS Glue: Serviço de ETL (Extração, Transformação e Carregamento) que organiza e prepara os dados para análise.

1. ### Visualização

   A visualização transforma dados complexos em representações gráficas intuitivas, como gráficos, dashboards e mapas. Ferramentas de visualização permitem consultas SQL diretas e compartilhamento de dados via API, facilitando a análise e interpretação de dados por diferentes públicos dentro da organização.

   Para uma visualização dinâmica dos dados, criamos uma API que extrai informações do fluxo de dados no Data Lake. Esta API foi integrada a um site existente em outro projeto. Nele, os dados gerados pelo processo semântico alimentam um mapa interativo, exibindo todas as localidades consultadas durante o fluxo de processamento. Os usuários podem interagir com o mapa para visualizar informações climáticas detalhadas de cada localidade.
<div align="center">
  
![mapa](https://github.com/Henrique-Ali/Desenvolvimento-Data-Lake-TCC/blob/main/imagens/MapaDados.png)

</div>

## Conclusão

Este projeto contribui para a compreensão dos benefícios e desafios associados à utilização de um Data Lake, destacando a importância da manipulação de dados na tomada de decisões estratégicas. Proporciona uma visão abrangente e integrada dos dados, com maior flexibilidade e capacidade de análise, alinhada às necessidades atuais do mercado computacional.

Explore o arquivo do TCC para mais detalhes sobre a metodologia, implementação e resultados obtidos.

## Desenvolvedores

* [Caio Pereira](https://github.com/Caio-Pereira)
* Gabriel Camacho
* [Henrique Ali](https://github.com/Henrique-Ali?tab=repositories)
* Rebecca Amaral
