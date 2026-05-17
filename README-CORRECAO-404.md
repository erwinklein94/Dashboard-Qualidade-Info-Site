# Correção 404 — Dashboard de Qualidade

O erro 404 acontece porque a raiz do GitHub Pages procura um arquivo `index.html`.

Este patch adiciona:

```text
index.html
404.html
.nojekyll
```

Depois de subir esses arquivos, acesse:

```text
https://erwinklein94.github.io/Dashboard-Qualidade-Info-Site/
```

Também continuam funcionando os caminhos:

```text
https://erwinklein94.github.io/Dashboard-Qualidade-Info-Site/dashboard-qualidade.html
https://erwinklein94.github.io/Dashboard-Qualidade-Info-Site/dashboard-qualidade/
```
