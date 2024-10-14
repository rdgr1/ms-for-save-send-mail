# Projeto MS-Login-Email

Este repositório contém dois microserviços que fazem parte de uma solução maior para gerenciamento de usuários e envio de emails. Cada serviço é desenvolvido em **Spring Boot**, com integração a banco de dados PostgreSQL e outras tecnologias do ecossistema Java. O foco é fornecer uma arquitetura modular, onde cada microserviço pode ser gerenciado de forma independente.

## Descrição

- **Microserviço de Email**: Responsável por gerenciar o envio de emails. Ele é projetado para ser eficiente, usando bibliotecas do Spring que facilitam o envio de emails através de servidores SMTP, além de suportar a integração com filas de mensagens (AMQP) para envio assíncrono.
  
- **Microserviço de Usuário**: Gerencia a criação, consulta, atualização e exclusão de usuários. Utiliza Spring Data JPA para persistência dos dados no banco de dados PostgreSQL e também oferece endpoints RESTful para gerenciamento via API.

### Principais funcionalidades:
- Cadastro de usuários
- Envio de emails de confirmação ou notificações
- Integração com banco de dados relacional (PostgreSQL)
- Uso de filas de mensagens para processamento assíncrono de emails

## Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3.3.4**
- **Spring Data JPA**
- **Spring Boot Starter AMQP**
- **Spring Boot Starter Mail**
- **PostgreSQL**
- **Maven**

## Estrutura do Projeto

O projeto é dividido em dois diretórios principais, cada um contendo um microserviço:

- `email/`: Microserviço de gerenciamento de emails.
- `user/`: Microserviço de gerenciamento de usuários.

Cada microserviço contém sua própria estrutura de código e dependências Maven no arquivo `pom.xml`.

## Instalação

### Pré-requisitos

- **Java 17** ou superior
- **Maven**
- **PostgreSQL** configurado

### Passos para rodar o projeto

1. Clone o repositório:
    ```bash
    git clone <URL_DO_REPOSITORIO>
    ```

2. Navegue até a pasta do microserviço desejado (email ou user):
    ```bash
    cd ms-login-email/email
    # ou
    cd ms-login-email/user
    ```

3. Instale as dependências do projeto:
    ```bash
    mvn clean install
    ```

4. Configure as propriedades do banco de dados e do serviço de email (veja a seção de **Configuração** abaixo).

5. Execute o projeto:
    ```bash
    mvn spring-boot:run
    ```

## Configuração

Você deve configurar as seguintes propriedades em um arquivo `application.properties` ou usar variáveis de ambiente:

### Exemplo de `application.properties`:

```properties
# Configurações do banco de dados
spring.datasource.url=jdbc:postgresql://localhost:5432/nome-do-banco
spring.datasource.username=seu-usuario
spring.datasource.password=sua-senha

# Configurações do email
spring.mail.host=smtp.exemplo.com
spring.mail.port=587
spring.mail.username=seu-usuario
spring.mail.password=sua-senha
```
##Testes
Você pode rodar os testes automatizados para ambos os microserviços usando Maven:

```bash
mvn test
```
Isso vai executar a suíte de testes configurada para garantir que as funcionalidades estão funcionando conforme esperado.

##Contribuição
Se você deseja contribuir para o projeto, siga os passos abaixo:

- 1.Faça um fork do repositório.
- 2.Crie uma nova branch com sua feature:
```bash
git checkout -b minha-feature
```
- 3.Faça as alterações desejadas e faça commit:
```bash
git commit -m "Adiciona nova funcionalidade"
```
- 4.Envie para o seu fork:
```bash
git push origin minha-feature
```
- 5.Abra um Pull Request para o repositório original.
##Licença
Este projeto está licenciado sob a [MIT License].
