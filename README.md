# Coleta de Métricas do Wildfly18+

Este projeto contém um "compose-file" e todos os arquivos necessários para realizar o deploy de 1 container do Prometheus e 1 container do Grafana com seu respectivo dashboard, afim de coletar e visualizar as métricas de um servidor de aplicação java Wildfly versão 18 ou superior.

> Foram realizados testes com as versões 18.x.x,19.x.x,20.x.x,21.x.x,22.x.x

> A versão 23.x.x possui uma versão superior do framework MicroProfile, sendo assim algumas métricas foram alteradas, porém o projeto deve atender à versão salvo algumas métricas que precisarão de revisão.
{.is-warning}

---

## Implantação

* Este projeto foi elaborado para um ambiente **Docker** e o **Docker-Compose** deverá estar instalado caso não esteja utilizando **Swarm**;


1. Realize o clone deste projeto;

2. Acesse o diretório criado com o clone;

3. Acesse o arquivo de configuração do Prometheus;
```
vim configs/prometheus.yml
```

4. Altere a última linha inserindo o IP:PORTA da instância do Wildfly a ser monitorada, caso seja mais de uma adicionar uma linha para cada;
> O Wildfly utiliza a porta de gerência para expor as métricas, a default é 9990.

5. Após salvar o arquivo, execute o comando do Docker-Compose para inciar os containers;
```
docker-compose up -d
```

6. O acesso aos serviços do container é realizado pela porta default de cada um que consta no arquivo "docker-compose.yml";

