# Test Quipux - Backend

Este é o repositório do backend para o projeto *Test Quipux*, desenvolvido utilizando **Spring Boot**.

## Tecnologias Utilizadas

- **Java**: Linguagem principal do projeto.
- **Spring Boot**: Framework para construção da aplicação.
- **H2 Database**: Banco de dados em memória para testes.
- **Spring Security**: Configuração de formulário de login e HTTP Basic; JWT não está configurado em `SecurityConfig.java`.

## Ambiente e limites

`build.gradle` declara Spring Boot 3.4.1 e toolchain Java 23. O projeto usa Gradle Wrapper. A interface correspondente está em `test-quipux-front`; integração, CORS, credenciais de execução e disponibilidade precisam de validação em ambiente próprio.

## Como Executar
1. Clone este repositório:
   ```bash
   git clone https://github.com/GuilhermeSerafim/test-quipux-back.git
   ```

2. Navegue até o diretório do projeto:
   ```bash
   cd test-quipux-back
   ```

3. Compile e execute a aplicação:
   ```bash
   ./gradlew bootRun
   ```

   No Windows, use `gradlew.bat bootRun`.

4. Endereço local padrão:
   ```
   http://localhost:8080
   ```

## Endpoints Disponíveis

- **GET** `/lists` - Retorna todas as listas de reprodução.
- **GET** `/lists/{listName}` - Busca uma lista pelo nome; retorna 404 quando não encontrada.
- **POST** `/lists` - Adiciona uma nova lista de reprodução.
- **DELETE** `/lists/{listName}` - Remove uma lista de reprodução pelo nome.

## Autenticação

`SecurityConfig.java` permite `/h2-console/**` e exige autenticação nas demais requisições, habilitando form login e HTTP Basic. Não há configuração JWT nesse arquivo. Credenciais devem ser definidas em ambiente próprio, sem incorporá-las ao frontend ou versioná-las. CSRF e frame options estão desabilitados nessa configuração de demonstração.

## Contribuição

Sinta-se à vontade para abrir issues ou enviar pull requests.
