# Dashboard de Qualidade — Associações e sindicatos

Este patch adiciona a área **Associações e sindicatos** ao site de controle de qualidade.

## O que foi integrado

- Nova área em `data/areas.json`.
- Novo relatório local em `data/associacoes/_relatorio-qualidade.json`.
- Novo atalho em `dashboard-qualidade.html`.
- Nova rota direta em `dashboard-associacoes-sindicatos.html` e `dashboard-associacoes-sindicatos/index.html`.
- Sincronização automática do relatório vindo do site principal pelo workflow `.github/workflows/sincronizar-relatorios.yml`.

## Origem dos dados

O dashboard de qualidade agora tenta copiar do site principal:

```text
site-principal/data/associacoes/_relatorio-qualidade.json
```

para:

```text
dashboard/data/associacoes/_relatorio-qualidade.json
```

## Entrada no dashboard geral

A área entra automaticamente no dashboard geral porque foi cadastrada em `data/areas.json`. O carregador também reconhece relatórios com lista em `itens`, que é o formato usado pelo relatório inicial de associações.

## Links úteis

```text
/dashboard-qualidade.html?area=associacoes-sindicatos
/dashboard-associacoes-sindicatos.html
/dashboard-associacoes-sindicatos/
```
