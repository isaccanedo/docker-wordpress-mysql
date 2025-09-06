# WordPress + MySQL com Docker Compose

Este projeto fornece um ambiente completo para rodar o WordPress com MySQL usando Docker Compose. Ideal para desenvolvimento local, testes ou para iniciar rapidamente um novo site WordPress sem precisar instalar nada manualmente.

## Pré-requisitos

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/)

## Como usar

1. **Clone este repositório:**

   ```bash
   git clone https://github.com/isaccanedo/docker-wordpress-mysql.git
   cd docker-wordpress-mysql
   ```

2. **Suba os serviços com o Docker Compose:**

   ```bash
   docker-compose up -d
   ```

3. **Acesse o WordPress:**

   Abra o navegador e acesse [http://localhost:8080](http://localhost:8080)

## Estrutura dos Serviços

- **db**: MySQL 8.0  
  Banco de dados utilizado pelo WordPress.  
  Os dados são persistidos no volume `db_data`.

- **wordpress**: WordPress (latest)  
  Aplicação WordPress pronta para configuração.  
  O diretório `wp-content` é montado como volume para facilitar o desenvolvimento de temas e plugins.

## Configurações Padrão

- **MySQL**
  - Usuário root: `root`
  - Senha root: `senhadoadmin`
  - Banco de dados: `wordpress`
  - Usuário: `wordpressuser`
  - Senha: `senhadousuario`

- **WordPress**
  - Porta local: `8080`
  - Dados persistentes em: `./wp-content`

> **Importante:** Para ambientes de produção, altere as senhas padrão no arquivo `docker-compose.yml`!

## Volumes

- `db_data`: Armazena os dados do MySQL.
- `./wp-content`: Sincroniza o conteúdo do WordPress (temas, plugins, uploads) com o host.

## Parar e remover os containers

```bash
docker-compose down
```

Se quiser remover também os volumes (dados do banco serão perdidos):

```bash
docker-compose down -v
```

## Personalização

- Para instalar plugins ou temas, basta adicionar arquivos em `./wp-content`.
- Altere variáveis de ambiente no `docker-compose.yml` para customizar as credenciais ou nomes dos serviços.

## Referências

- [Documentação oficial do WordPress Docker](https://hub.docker.com/_/wordpress)
- [Documentação oficial do MySQL Docker](https://hub.docker.com/_/mysql)
- [Documentação do Docker Compose](https://docs.docker.com/compose/)

---

Feito com ❤️ usando Docker Compose.
