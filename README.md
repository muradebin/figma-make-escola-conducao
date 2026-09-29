# Acervo para Figma Make

Este diretório contém uma cópia organizada do acervo de perguntas e imagens do projeto Exame de Condução MZ. Ele foi preparado para ser enviado ao Figma Make ou publicado separadamente no GitHub.

## Estrutura

- `catalogo.json`: informações gerais e regras de leitura.
- `categorias.json`: mapa entre categorias, códigos originais e caminhos dos ficheiros.
- `free/`: sete pacotes gratuitos.
- `premium/`: 84 pacotes pagos, incluindo os bundles `lp` e `pro`.
- `source-index.json`: índice original exportado.
- `source-by-category.json`: agrupamento original exportado.

Cada categoria possui:

```text
{nivel}/{categoria}/{bundle}/questions/{unit}.json
{nivel}/{categoria}/{bundle}/images/{unit}/
```

O `{bundle}` identifica a origem do pacote: `demo`, `lp` ou `pro`. Ele é mantido no caminho para evitar colisões entre unidades com o mesmo nome. No JSON de cada pacote, o campo `imageRelativePath` identifica a imagem da pergunta. A imagem correspondente está dentro da pasta `images/{unit}` do mesmo bundle, categoria e nível.

## Categorias

- `cde`, `codigo-da-estrada`: Código da Estrada
- `sdt`, `sinais-de-transito`: Sinais de Trânsito
- `exame`, `exames-predefinidos`: Exames Predefinidos
- `revisao`, `cg`, `mec`, `revisao-geral`: Revisão Geral

## Instrução para o Figma Make

Leia primeiro `catalogo.json` e `categorias.json`. Depois leia os ficheiros JSON dentro das pastas `free` e `premium`. Organize cada pergunta pela categoria e pelo bundle indicado no caminho. Associe as imagens pelo `imageRelativePath` dentro da pasta de imagens do mesmo pacote.

Não invente conteúdo. Use o campo `correct` somente para validar a resposta depois da submissão. Mostre primeiro os pacotes gratuitos e identifique os pacotes premium como conteúdo bloqueado ou opcional.

## Nota de publicação

O diretório `premium` contém as respostas correctas. Não use esses ficheiros diretamente no navegador numa versão pública com conteúdo pago. Para produção, mova o conteúdo premium para uma API ou base de dados com autenticação.