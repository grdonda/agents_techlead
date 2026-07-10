# java-especialista-springrest-algafood

Data: 09/07/2026 14:00

Repositório: grdonda/java-especialista-springrest-algafood

Branch Principal: main

---

# Resumo Executivo

Aplicação Spring Boot de backend REST para domínio de restaurante. Evidência pública confirma foco em `Cozinha`, `Estado` e `Restaurante`.

---

# Objetivo do Projeto

Expor operações REST simples com persistência JPA via `EntityManager` e retorno em JSON/XML.

---

# Stack

- Java 25
- Spring Boot 4.0.6
- Spring WebMVC
- Spring Data JPA
- Jackson XML

---

# Arquitetura

- Camadas `api`, `domain` e `infraestructure`.
- Controllers dependem de interfaces de repositório.
- Repositórios usam `EntityManager` manual.
- Não foi identificada camada de service.

---

# Estrutura de Pastas

- `src/main/java/.../api/controller` - controllers HTTP.
- `src/main/java/.../api/model` - wrapper XML.
- `src/main/java/.../domain/model` - entidades JPA.
- `src/main/java/.../domain/model/repository` - contratos de repositório.
- `src/main/java/.../infraestructure` - persistência com `EntityManager`.

---

# Dependências

- `spring-boot-starter-parent:4.0.6`
- `spring-boot-starter-actuator`
- `spring-boot-starter-data-jpa`
- `spring-boot-starter-webmvc`
- `jackson-dataformat-xml`

---

# Banco de Dados

- MySQL sugerido pelo driver runtime.
- H2 usado em testes.
- Persistência visível por `EntityManager`.
- Migrações: Não encontrado.

---

# Configurações

- `spring.application.name=java-especialista-springrest-algafood`
- `spring.profiles.active=dev`
- `application.yml`: Não encontrado.
- Datasource: Não encontrado.

---

# APIs

- `GET /ping`
- `GET /cozinhas/listar`
- `GET /cozinhas/{id}`
- `GET /estados/listar`

---

# Segurança

- Autenticação/autorização: Não encontrado.
- DTOs e validação: Não encontrado.
- Handler global de exceções: Não encontrado.
- Swagger/OpenAPI: Não encontrado.

---

# Observabilidade

- `spring-boot-starter-actuator` presente.
- Métricas customizadas: Não encontrado.
- Logs configurados: Não encontrado.
- Health check básico via `/ping`.

---

# Testes

- `contextLoads()` presente.
- Testes de controller com `MockMvc` presentes.
- Cenários negativos: Não encontrado.
- Validação de entrada: Não encontrado.

---

# Patterns Encontrados

|Pattern|Status|Observação|
|---|---|---|
|Repository|Encontrado|Interfaces em `domain` e implementação em `infraestructure`|
|Controller|Encontrado|Endpoints REST em `api/controller`|
|Wrapper XML|Encontrado|`CozinhasXmlWrapper` para XML|
|Service|Não encontrado|Sem camada intermediária|

---

# Anti-patterns

|Tipo|Arquivo|Descrição|Arquivo|Como resolver|
|---|---|---|---|---|
|Injeção por campo|`CozinhaController.java`|Uso de `@Autowired` em campo|`CozinhaController.java`|Trocar por injeção via construtor|
|Acoplamento alto|`CozinhaController.java`|Controller acessa repositório diretamente|`CozinhaController.java`|Adicionar service layer|
|Persistência manual|`CozinhaRepositoryImpl.java`|Uso direto de `EntityManager`|`CozinhaRepositoryImpl.java`|Avaliar Spring Data JPA|
|Exposição de entidade|`CozinhaController.java`|Entidade JPA retornada na API|`CozinhaController.java`|Usar DTOs|

---

# Pontos Fortes

- Contratos de repositório separados da implementação.
- Estrutura pequena e navegável.
- XML e JSON suportados.
- `MockMvc` presente nos testes.

---

# Pontos Fracos

- Falta service layer.
- Falta DTO.
- Falta validação.
- Falta tratamento centralizado de exceções.

---

# Dívida Técnica

- Falta de service layer.
- Falta de DTOs.
- Falta de validação de entrada.
- Falta de handler global de exceções.

---

# TODO

|Prioridade|Tipo|Descrição|Arquivo|
|---|---|---|---|
|Alta|Refatoração|Criar service layer|`CozinhaController.java`|
|Alta|Refatoração|Trocar injeção por campo por construtor|`CozinhaController.java`|
|Alta|Refatoração|Introduzir DTOs|`CozinhaController.java`|
|Alta|Correção|Adicionar Bean Validation|`CozinhaController.java`|
|Alta|Correção|Criar handler global de exceções|`CozinhaController.java`|
|Média|Teste|Cobrir cenários negativos|`CozinhaControllerTest.java`|
|Média|Teste|Cobrir JSON e XML|`CozinhaControllerTest.java`|
|Média|Upgrade|Avaliar Spring Data JPA|`CozinhaRepositoryImpl.java`|
|Média|Documentação|Adicionar README|`README.md`|

---

# Riscos

|Risco|Impacto|Arquivo|
|---|---|---|
|Controller sem service|Regra de negócio espalhada|`CozinhaController.java`|
|Entidade exposta na API|Acoplamento forte com JPA|`CozinhaController.java`|
|Sem validação|Entradas inválidas passam adiante|`CozinhaController.java`|
|Sem handler global|Erros inconsistentes|`CozinhaController.java`|
|`EntityManager` manual|Manutenção cresce com a complexidade|`CozinhaRepositoryImpl.java`|

---

# Melhorias

## Alta

|Problema|Impacto|Ação|
|---|---|---|
|Sem service layer|Baixa manutenibilidade|Criar service|`CozinhaController.java`|
|Sem DTO|API acoplada ao domínio|Adicionar DTOs|`CozinhaController.java`|
|Sem validação|Erros de entrada|Adicionar Bean Validation|`CozinhaController.java`|
|Sem handler global|Erros inconsistentes|Centralizar exceções|`CozinhaController.java`|

## Média

|Problema|Impacto|Ação|
|---|---|---|
|Testes limitados|Baixa confiança|Cobrir cenários negativos|`CozinhaControllerTest.java`|
|Sem contrato formal|Dificulta consumo|Documentar API|`README.md`|
|XML e JSON sem testes dedicados|Risco de regressão|Cobrir serialização|`CozinhaControllerTest.java`|

## Baixa

|Problema|Impacto|Ação|
|---|---|---|
|Sem Swagger|API menos autoexplicativa|Adicionar OpenAPI|`README.md`|
|Sem métricas extras|Baixa visibilidade|Evoluir Actuator|`application.properties`|
|Sem README público|Baixa descoberta|Adicionar documentação|`README.md`|

---

# Score Técnico

|Item|Nota|
|----|----|
|Arquitetura|5|
|Código|6|
|Logs|4|
|Segurança|4|
|Performance|6|
|Testes|5|
|Documentação|1|
|Manutenibilidade|4|

## Nota Final

4/10

---

# Conclusão

Estado geral: base funcional e simples.
Principal risco: controller e repositório concentram regra e acoplamento.
Primeira ação recomendada: criar service layer e DTOs.