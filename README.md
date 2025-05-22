🚀 Trabalho: Conteinerização com Docker Compose
🎓 Nomes dos integrantes
Pedro Bartz (1135935)
Rafael Pedra (1136090)
João Vitor (1134020)

📝 Resumo
Este projeto tem como objetivo demonstrar o uso da conteinerização com Docker Compose, integrando dois serviços: uma API desenvolvida com FastAPI e um banco de dados PostgreSQL.
A aplicação expõe uma API RESTful capaz de realizar operações CRUD (Create, Read, Update, Delete) sobre uma entidade de usuários.
A composição de contêineres permite isolar cada serviço, facilitando o desenvolvimento, o deploy, e garantindo portabilidade entre ambientes. 
A API é acessível pelo host através de uma porta específica, mesmo estando executando dentro de uma máquina virtual.

🎯 Objetivo do Trabalho
Explorar as possibilidades abertas pela conteinerização por meio do uso do Docker Compose, utilizando no mínimo dois contêineres que se comunicam:
Contêiner 1: API Python com FastAPI e SQLAlchemy.
Contêiner 2: Banco de Dados relacional PostgreSQL.
O sistema implementa uma estrutura completa de CRUD e expõe os serviços de forma que podem ser acessados a partir do host da máquina virtual.

🛠️ Serviços utilizados
📌 FastAPI
📌 PostgreSQL

| Serviço    | Porta     | Volume                            | Rede          | Imagem                |
| ---------- | --------- | --------------------------------- | ------------- | --------------------- |
| FastAPI    | 8000:8000 | Não necessário                    | `app-network` | Python + dependências |
| PostgreSQL | 5432:5432 | `pgdata:/var/lib/postgresql/data` | `app-network` | postgres\:latest      |


🐳 Docker
🔹 Imagens utilizadas
Python oficial: para criar a imagem da API com FastAPI.
PostgreSQL oficial: para o banco de dados.

🔹 Configuração de cada serviço
Serviço	Porta	Volume	Rede	Imagem
FastAPI	8000:8000	Não necessário	app-network	Python + dependências
PostgreSQL	5432:5432	pgdata:/var/lib/postgresql/data	app-network	postgres:latest
Dependência: A API depende do banco de dados PostgreSQL para realizar as operações CRUD.
Volumes: Persistência de dados do banco.
Redes: Comunicação isolada via rede app-network.
