# Dashboard Geral Multiáreas — Universo Seg Pub

Este patch transforma o dashboard de qualidade em uma central geral para todas as áreas automatizadas do site.

## Áreas configuradas agora

- Concursos
- Remuneração

## Arquivos principais

```text
dashboard-qualidade.html
dashboard-qualidade/index.html
dashboard-geral.html
dashboard-concursos.html
dashboard-remuneracao.html
data/areas.json
data/concursos/_relatorio-qualidade.json
data/remuneracao/_relatorio-qualidade.json
```

## Como funciona

O dashboard carrega `data/areas.json` e, para cada área, lê o relatório de qualidade informado no campo `relatorio`.

Ele normaliza relatórios com formatos diferentes e classifica tudo em:

```text
pendentes
fracas
fortes
```

## Como adicionar uma nova área no futuro

1. Crie o relatório da nova área em algo como:

```text
data/nova-area/_relatorio-qualidade.json
```

2. Adicione uma entrada em:

```text
data/areas.json
```

Exemplo:

```json
{
  "id": "direitos",
  "nome": "Direitos",
  "descricao": "Qualidade das informações sobre direitos e benefícios.",
  "relatorio": "data/direitos/_relatorio-qualidade.json",
  "workflow": "Atualizar Direitos - Simples"
}
```

3. O dashboard geral passa a exibir a nova área automaticamente.

## Links úteis no GitHub Pages

```text
/dashboard-qualidade.html
/dashboard-qualidade/?area=concursos
/dashboard-qualidade/?area=remuneracao
/dashboard-concursos.html
/dashboard-remuneracao.html
```
