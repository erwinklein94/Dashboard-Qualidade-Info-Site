# Correção — dashboard carregando zerado

O dashboard estava com os cards zerados porque o JavaScript não chamava automaticamente a função `loadDefaultReport()` ao abrir a página.

## O que foi corrigido

- O painel agora carrega `data/concursos/_relatorio-qualidade.json` automaticamente ao abrir.
- Se existir um relatório antigo ou inválido salvo no navegador, ele é ignorado.
- O dashboard tenta ler dados em `fila_acoes` e, se necessário, também em `grupos`.
- A tela agora informa erro real quando o JSON não é encontrado.

## Arquivos alterados

- `dashboard-qualidade.html`
- `dashboard-qualidade/index.html`
- `docs/CORRECAO-DASHBOARD-ZERADO.md`

## Depois de subir

Abra o dashboard e pressione `Ctrl + F5`.

Se ainda aparecer zerado, clique em:

```text
Limpar relatório salvo
```

Depois clique em:

```text
Recarregar relatório do site
```
