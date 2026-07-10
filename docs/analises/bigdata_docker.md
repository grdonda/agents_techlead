# BIG DATA ECOSYSTEM COM DOCKER

## Resumo do negocio
Ambiente de estudo e demonstração de um ecossistema Big Data em Docker. O repositório documenta como subir uma stack local com serviços como HDFS, HBase, Hive, Presto, Spark, Jupyter, Hue, MongoDB, Metabase, Nifi, Kafka, MySQL e Zookeeper.

## Data e hora da analise
09/07/2026 00:28

## Objetivo do projeto
Provisionar um laboratório local para experimentação com ferramentas Big Data, incluindo instruções de setup para Windows e Linux, criação de VM, compartilhamento de disco, mapeamento de portas e comandos para operar os containers.

## Branches do projeto
- `master` - branch principal visível no repositório.
- O repositório é um fork de `fabiogjardim/bigdata_docker`.
- A branch pública exibida no GitHub aparece 12 commits atrás do upstream.

## Features do projeto
- Ambiente Docker com múltiplos serviços Big Data.
- Arquivos de composição para subir o ecossistema em container.
- Script `virtualbox_config.bat` para preparar a VM `default` no fluxo Windows.
- Documentação de acesso web para HDFS, Presto, HBase, Mongo Express, Kafka Manager, Metabase, Nifi, Jupyter Spark, Hue e Spark UI.
- Instruções de acesso por shell e por JDBC.
- Notebooks PySpark com exemplos de leitura e gravação em Presto e MySQL.

## Desenvolvedores envolvidos
- Nenhum contributor aparece listado publicamente na página consultada.
- Os commits visíveis e a origem do fork apontam para `fabiogjardim` como referência do upstream.

## Ultimas PRs mergeadas na branch principal
- Nao foi possivel confirmar PRs mergeadas.
- A pagina publica de pull requests do fork mostra `0 Open` e `0 Closed`.

## Ultimas releases e features identificadas
- Nao há releases publicadas visíveis na página do repositório.
- As principais features publicamente identificáveis estão concentradas na orquestração da stack Big Data, nos notebooks de validação e na documentação de uso.

## Dependencias do projeto
- Docker.
- Git.
- Docker Toolbox / Docker Machine e VirtualBox para o fluxo Windows descrito no README.
- Componentes da stack: HDFS, HBase, Hive, Presto, Spark, Jupyter, Hue, MongoDB, Metabase, Nifi, Kafka, MySQL e Zookeeper.

## Analise do `pom.xml`
- Nao foi encontrado `pom.xml`.
- O repositório nao aparenta ser uma aplicacao Java/Maven; a estrutura é orientada a Docker, notebooks e arquivos de configuração de ambiente.

## Analise dos arquivos de configuracao
- Nao foram encontrados `application.properties` nem `application.yml`.
- O principal arquivo de configuracao identificado foi `virtualbox_config.bat`, usado para recriar a VM `default`, ajustar memoria, configurar compartilhamento e mapear portas.
- O README detalha o uso de `docker-compose.yml`, os comandos para subir/parar containers e os endpoints expostos.

## Observacoes tecnicas relevantes
- O projeto é um fork público de `fabiogjardim/bigdata_docker`.
- A documentação sugere um setup mais antigo, dependente de Docker Toolbox e VirtualBox no Windows.
- Os notebooks mostram validações práticas com PySpark e também erros de execução anteriores, o que reforça o uso como laboratório de estudo.
- Como o acesso público é suficiente para ler o README, a proposta geral foi confirmada; já dados como commits recentes, PRs mergeadas e contributors adicionais nao ficaram publicamente evidentes.