<h1>Pipeline de Dados com Prefect, DBT e PostgreSQL</h1>
<h2>Visão Geral do Projeto</h2>
<br>
<p>Este projeto demonstra a criação de uma pipeline de dados completa e automatizada, usando Prefect para orquestração, DBT para transformação e PostgreSQL para armazenamento. O objetivo é coletar e analisar dados do site da ANS (Agência Nacional de Saúde Suplementar), com foco na criação de uma tabela derivada que apresenta o total de planos de saúde por categoria no mês de dezembro de 2019.</p>

<h2>Objetivo do Projeto</h2>
<br>

<ul>
<li>Automatizar o fluxo de dados: desde a extração até a transformação e armazenamento.</li>
<li>Fornecer insights relevantes: criar uma tabela derivada com informações categorizadas sobre planos de saúde.</li>
<li>Demonstrar habilidades técnicas: implementação prática de ferramentas essenciais para engenharia de dados.</li>
</ul>
<br>

<h2>Tecnologias Utilizadas</h2>

<ul>
<li>Prefect: Ferramenta de orquestração de workflows para gerenciar o fluxo de dados de forma confiável e escalável.</li>
<li>DBT (Data Build Tool): Utilizado para transformar os dados brutos em tabelas estruturadas e análises significativas.</li>
<li>PostgreSQL: Banco de dados relacional usado para armazenamento e consulta de dados.</li>
<li>Docker: Para configurar e gerenciar ambientes consistentes.</li>
</ul>

<h2>Arquitetura do Projeto</h2>

    <p>Extração de Dados</p>

<li>Coleta dos dados disponíveis no site da ANS por meio de scripts automatizados, configurados e monitorados no Prefect.</li>

    <p>Carga no Banco de Dados.</p>

<li>Os dados extraídos são inseridos em uma tabela bruta no PostgreSQL, utilizando Prefect para orquestrar o processo.</li>

    <p>Transformação com DBT</p>

<li>DBT é usado para mapear e transformar os dados, criando uma tabela derivada que apresenta o total de planos categorizados por tipo no mês de dezembro de 2019.</li>

    <p>Validação e Monitoramento</p>

<li>Validamos os resultados finais com consultas SQL e integramos logs detalhados para monitoramento no Prefect.</li>


<h2>Como Executar o Projeto</h2>

<h3>Pré-requisitos</h3>
<ul>
<li>Docker e Docker Compose instalados.</li>
<li>PostgreSQL configurado.</li>
<li>Prefect e DBT instalados no ambiente.</li>
</ul>

<h3>Passos para Rodar o Projeto</h3>

<p>1.Clonar o Repositório</p>
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
