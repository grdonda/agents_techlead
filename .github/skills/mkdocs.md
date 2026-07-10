# MkDocs

Responsável apenas pela documentação.

## Entrada

Recebe um documento markdown da pasta templates/github-analise-repositorio.md

## Saída

Salvar em docs/analises/<repositorio>.md
Sem acentos
Lowercase

## Navegação

Abrir:
mkdocs.yml
Verificar se existe o nome do projeto no nav de analise

Analises:
Caso não exista
Criar usando mesmo nome do projeto na url do repositorio

Caso exista
Verificar se o projeto já está listado.

Se estiver
Não duplicar.

Se não estiver
Adicionar.

Exemplo

nav:

- Home: index.md

- Analises:
    - Projeto A: analises/projeto-a.md
    - Projeto B: analises/projeto-b.md

## Atualização

Se o arquivo existir
Sobrescrever.

Nunca criar versões duplicadas.