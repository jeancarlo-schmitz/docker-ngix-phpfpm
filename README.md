# Projeto PHP + Nginx + PHP-FPM com Docker

Este projeto utiliza **Docker** para rodar um ambiente PHP com **Nginx** e **PHP-FPM**, pronto para desenvolvimento e testes, podendo se conectar a um banco PostgreSQL externo.

---

## Estrutura do projeto
/docker/
│
├── nginx/
│ ├── Dockerfile
│ └── nginx.conf
│
├── php/
│ ├── Dockerfile
│
└── docker-compose.yml


- **nginx/**: contém a imagem customizada do Nginx e o arquivo de configuração (`nginx.conf`).
- **php/**: contém a imagem PHP-FPM customizada com extensões necessárias (como `pdo_pgsql` para PostgreSQL).
- **docker-compose.yml**: define os serviços e volumes.

---