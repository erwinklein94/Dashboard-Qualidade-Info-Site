# Revisão do Dashboard de Qualidade

Esta versão corrige a leitura operacional do relatório de concursos.

## Problema encontrado

O dashboard anterior usava diretamente os campos `resumo` e `acao` do relatório bruto. Isso podia distorcer a decisão operacional.

Exemplo: uma instituição com score alto e conteúdo bom podia aparecer como `rodar_qualificado` apenas porque a fonte direta falhou ou porque foi publicada no modo qualificado.

## Nova interpretação do dashboard

O painel agora calcula um diagnóstico próprio por instituição:

- `OK editorial`: conteúdo suficiente para o usuário final.
- `Qualificar conteúdo`: score baixo, qualidade baixa ou campo crítico ruim/genérico.
- `Pesquisa inicial`: instituições recém-incluídas/sem primeira pesquisa útil.
- `Revisar resultado pago`: OpenAI já foi usada ou há rascunho; revisar antes de gastar de novo.
- `Ajustar fonte/monitor`: conteúdo está aceitável, mas a fonte direta falhou.

## Regra central

Nem toda linha `rodar_qualificado` no relatório bruto significa que a instituição precisa gastar OpenAI de novo.

O dashboard agora separa:

```text
problema editorial real
vs.
problema de fonte/monitoramento
vs.
primeira pesquisa pendente
vs.
resultado pago que precisa revisão visual
```

Isso deixa a fila de ações mais útil para decidir onde gastar crédito da OpenAI.
