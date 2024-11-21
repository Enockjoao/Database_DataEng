<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pipeline de Dados com Prefect, DBT e PostgreSQL</title>
</head>
<body>
  <h1>Pipeline de Dados com Prefect, DBT e PostgreSQL</h1>

  <h2>Visão Geral do Projeto</h2>
  <p>
    Este projeto demonstra a criação de uma pipeline de dados completa e automatizada, usando Prefect para orquestração,
    DBT para transformação e PostgreSQL para armazenamento. O objetivo é coletar e analisar dados do site da ANS
    (Agência Nacional de Saúde Suplementar), com foco na criação de uma tabela derivada que apresenta o total de planos
    de saúde por categoria no mês de dezembro de 2019.
  </p>

  <h2>Objetivo do Projeto</h2>
  <ul>
    <li><p>Automatizar o fluxo de dados: desde a extração até a transformação e armazenamento.</p></li>
    <li><p>Fornecer insights relevantes: criar uma tabela derivada com informações categorizadas sobre planos de saúde.</p></li>
    <li><p>Demonstrar habilidades técnicas: implementação prática de ferramentas essenciais para engenharia de dados.</p></li>
  </ul>

  <h2>Tecnologias Utilizadas</h2>
  <ul>
    <li><p><strong>Prefect:</strong> Ferramenta de orquestração de workflows para gerenciar o fluxo de dados de forma confiável e escalável.</p></li>
    <li><p><strong>DBT (Data Build Tool):</strong> Utilizado para transformar os dados brutos em tabelas estruturadas e análises significativas.</p></li>
    <li><p><strong>PostgreSQL:</strong> Banco de dados relacional usado para armazenamento e consulta de dados.</p></li>
    <li><p><strong>Docker:</strong> Para configurar e gerenciar ambientes consistentes.</p></li>
  </ul>

  <h2>Arquitetura do Projeto</h2>
  <ol>
    <li>
      <p><strong>Extração de Dados:</strong> Coleta dos dados disponíveis no site da ANS por meio de scripts automatizados, configurados e monitorados no Prefect.</p>
    </li>
    <li>
      <p><strong>Carga no Banco de Dados:</strong> Os dados extraídos são inseridos em uma tabela bruta no PostgreSQL, utilizando Prefect para orquestrar o processo.</p>
    </li>
    <li>
      <p><strong>Transformação com DBT:</strong> DBT é usado para mapear e transformar os dados, criando uma tabela derivada que apresenta o total de planos categorizados por tipo no mês de dezembro de 2019.</p>
    </li>
    <li>
      <p><strong>Validação e Monitoramento:</strong> Validamos os resultados finais com consultas SQL e integramos logs detalhados para monitoramento no Prefect.</p>
    </li>
  </ol>

  <h2>Como Executar o Projeto</h2>

  <h3>Pré-requisitos</h3>
  <ul>
    <li><p>Docker e Docker Compose instalados.</p></li>
    <li><p>PostgreSQL configurado.</p></li>
    <li><p>Prefect e DBT instalados no ambiente.</p></li>
  </ul>

  <h3>Passos para Rodar o Projeto</h3>
  <ol>
    <li>
      <p><strong>Clonar o Repositório:</strong></p>
      <pre><code>git clone https://github.com/seu-usuario/pipeline-prefect-dbt.git
cd pipeline-prefect-dbt
      </code></pre>
    </li>
    <li>
      <p><strong>Subir o Ambiente Docker:</strong></p>
      <pre><code>docker-compose up -d</code></pre>
    </li>
    <li>
      <p><strong>Executar o Flow do Prefect:</strong></p>
      <pre><code>prefect deployment run flow_name</code></pre>
    </li>
    <li>
      <p><strong>Transformação com DBT:</strong> Dentro do container DBT, execute os comandos para gerar as tabelas derivadas:</p>
      <pre><code>dbt run
dbt test</code></pre>
    </li>
    <li>
      <p><strong>Verificar os Resultados:</strong> Realize consultas no PostgreSQL para verificar a tabela derivada:</p>
      <pre><code>SELECT * FROM tabela_derivada;</code></pre>
    </li>
  </ol>

  <h2>Resultados e Aprendizados</h2>
  <ul>
    <li>
      <p><strong>Resultados:</strong></p>
      <ul>
        <li><p>Tabela derivada criada com sucesso, apresentando o total de planos por categoria em dezembro de 2019.</p></li>
        <li><p>Pipeline modular e escalável, facilitando ajustes futuros.</p></li>
      </ul>
    </li>
    <li>
      <p><strong>Aprendizados:</strong></p>
      <ul>
        <li><p>Orquestração eficiente de workflows com Prefect.</p></li>
        <li><p>Transformações avançadas de dados com DBT.</p></li>
        <li><p>Integração e manipulação de dados com PostgreSQL.</p></li>
      </ul>
    </li>
  </ul>

  <h2>Possíveis Extensões do Projeto</h2>
  <ul>
    <li><p>Adicionar visualização dos dados utilizando Apache Superset ou Metabase.</p></li>
    <li><p>Implementar monitoramento em tempo real para alterações nos dados da ANS.</p></li>
    <li><p>Otimizar a pipeline para suportar múltiplos períodos de tempo e categorias adicionais.</p></li>
  </ul>
</body>
</html>
