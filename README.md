<h1>Pipeline de Dados com Prefect, DBT e PostgreSQL</h1>
Visão Geral do Projeto
Este projeto demonstra a criação de uma pipeline de dados completa e automatizada, usando Prefect para orquestração, DBT para transformação e PostgreSQL para armazenamento. O objetivo é coletar e analisar dados do site da ANS (Agência Nacional de Saúde Suplementar), com foco na criação de uma tabela derivada que apresenta o total de planos de saúde por categoria no mês de dezembro de 2019.

Objetivo do Projeto
Automatizar o fluxo de dados: desde a extração até a transformação e armazenamento.
Fornecer insights relevantes: criar uma tabela derivada com informações categorizadas sobre planos de saúde.
Demonstrar habilidades técnicas: implementação prática de ferramentas essenciais para engenharia de dados.
Tecnologias Utilizadas
Prefect: Ferramenta de orquestração de workflows para gerenciar o fluxo de dados de forma confiável e escalável.
DBT (Data Build Tool): Utilizado para transformar os dados brutos em tabelas estruturadas e análises significativas.
PostgreSQL: Banco de dados relacional usado para armazenamento e consulta de dados.
Docker: Para configurar e gerenciar ambientes consistentes.
Arquitetura do Projeto
Extração de Dados

Coleta dos dados disponíveis no site da ANS por meio de scripts automatizados, configurados e monitorados no Prefect.
Carga no Banco de Dados

Os dados extraídos são inseridos em uma tabela bruta no PostgreSQL, utilizando Prefect para orquestrar o processo.
Transformação com DBT

DBT é usado para mapear e transformar os dados, criando uma tabela derivada que apresenta o total de planos categorizados por tipo no mês de dezembro de 2019.
Validação e Monitoramento

Validamos os resultados finais com consultas SQL e integramos logs detalhados para monitoramento no Prefect.
Como Executar o Projeto
Pré-requisitos
Docker e Docker Compose instalados.
PostgreSQL configurado.
Prefect e DBT instalados no ambiente.
Passos para Rodar o Projeto
Clonar o Repositório

bash
Copiar código
git clone https://github.com/seu-usuario/pipeline-prefect-dbt.git  
cd pipeline-prefect-dbt  
Subir o Ambiente Docker

bash
Copiar código
docker-compose up -d  
Executar o Flow do Prefect
Configure o fluxo no Prefect e execute:

bash
Copiar código
prefect deployment run flow_name  
Transformação com DBT
Dentro do container DBT, execute os comandos para gerar as tabelas derivadas:

bash
Copiar código
dbt run  
dbt test  
Verificar os Resultados
Realize consultas no PostgreSQL para verificar a tabela derivada:

sql
Copiar código
SELECT * FROM tabela_derivada;  
Resultados e Aprendizados
Resultados:

Tabela derivada criada com sucesso, apresentando o total de planos por categoria em dezembro de 2019.
Pipeline modular e escalável, facilitando ajustes futuros.
Aprendizados:

Orquestração eficiente de workflows com Prefect.
Transformações avançadas de dados com DBT.
Integração e manipulação de dados com PostgreSQL.
Possíveis Extensões do Projeto
Adicionar visualização dos dados utilizando Apache Superset ou Metabase.
Implementar monitoramento em tempo real para alterações nos dados da ANS.
Otimizar a pipeline para suportar múltiplos períodos de tempo e categorias adicionais.
