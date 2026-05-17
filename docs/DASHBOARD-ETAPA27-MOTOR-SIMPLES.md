# Dashboard de Qualidade — lógica do motor simples

Esta versão do dashboard acompanha a reformulação do motor de concursos.

## Classificações exibidas

O painel agora trabalha com apenas três classificações reais:

```text
pendentes
fracas
fortes
```

E com dois modos operacionais extras do workflow:

```text
todas
instituicao
```

## Significado

### Pendentes

Instituições que ainda precisam da primeira pesquisa útil.

Workflow sugerido:

```text
grupo_atualizacao: pendentes
quantidade: 5
modelo_openai: gpt-5.4-mini, gpt-5.4 ou gpt-5.5
```

### Fracas

Instituições que já têm conteúdo, mas ainda estão genéricas, incompletas ou abaixo do padrão editorial.

Workflow sugerido:

```text
grupo_atualizacao: fracas
quantidade: 5
modelo_openai: gpt-5.4 ou gpt-5.5
```

### Fortes

Instituições com conteúdo considerado bom, usadas apenas para manutenção.

Workflow sugerido:

```text
grupo_atualizacao: fortes
quantidade: 5
modelo_openai: gpt-5.4-mini
```

### Todas

Não é uma classificação editorial. É um modo para rodar qualquer instituição respeitando a quantidade escolhida.

### Instituição

Não é uma classificação editorial. É um modo manual para atualizar um ID específico.

Exemplo:

```text
grupo_atualizacao: instituicao
instituicao: pmesp
quantidade: 1
modelo_openai: gpt-5.5
```

## Compatibilidade

O dashboard aceita o novo relatório simples com:

```json
{
  "modelo_operacional": "simples",
  "resumo": {
    "total": 110,
    "pendentes": 63,
    "fracas": 7,
    "fortes": 40
  },
  "grupos": {
    "pendentes": [],
    "fracas": [],
    "fortes": []
  },
  "fila_acoes": []
}
```

Também tenta interpretar relatórios antigos quando possível.
