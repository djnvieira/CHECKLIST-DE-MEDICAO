# Checklist de Medição — Fabrilis

Formulário HTML para padronizar o envio de projetos ao setor técnico antes da medição. Substitui a checagem manual por um checklist interativo que só libera o resumo final quando todos os itens estiverem resolvidos (informados ou marcados como "não se aplica").

**Ver ao vivo:** https://djnvieira.github.io/CHECKLIST-DE-MEDICAO/checklist-v5.html

## Como usar

Não há instalação nem build. Duas formas de abrir:

1. **Online:** acesse o link do GitHub Pages acima direto no navegador.
2. **Local:** baixe o arquivo `.html` e dê duplo clique — abre em qualquer navegador, funciona offline.

Preencha os quadros na ordem (Identificação → Obra Civil → Eletrodomésticos → Bancadas/Cubas/Metais → Mobiliário de Terceiros → Demais Itens → Observações). O botão **"Gerar solicitação de medição"** só habilita quando a barra de progresso chegar a 100%. O resumo gerado pode ser impresso ou salvo como PDF (`Ctrl/Cmd+P`).

## Stack

HTML + CSS + JavaScript puro, em um único arquivo autocontido por versão. Sem framework, sem dependências externas, sem etapa de build. O deploy é o próprio arquivo publicado via GitHub Pages.

Essa simplicidade é intencional: qualquer pessoa do time abre o arquivo sem precisar de Node, npm ou ambiente de desenvolvimento configurado.

## Versões

O projeto evolui por **arquivos versionados lado a lado** (`checklist-v3.html`, `checklist-v4.html`, `checklist-v5.html`...), não por branches/tags — cada versão nova é revisada visualmente antes de publicar, e a versão anterior permanece no ar para não quebrar quem já tem o link salvo. Ver histórico completo em [CHANGELOG.md](CHANGELOG.md).

`index.html` e `checklist-v2.html` são versões antigas mantidas por compatibilidade — a versão corrente é sempre a de número mais alto.

## Estrutura do formulário (v5)

| Quadro | Conteúdo |
|---|---|
| Identificação | Cliente, projeto, consultor, arquiteto, endereço, tipo de medição, fotos (SharePoint) |
| 1 — Obra Civil Finalizada | Checklist de pré-requisitos da obra (revestimento, forro, rodapés, pontos hidráulicos/elétricos, bases de alvenaria, pontos de aspiração/ar-condicionado) |
| 2 — Eletrodomésticos | Lista fixa + itens dinâmicos, com alimentação (elétrico/gás) e necessidade de respiro quando aplicável |
| 3 — Bancadas, Cubas e Metais | Bancada por ambiente com cuba (inox/louça/esculpida) e metal vinculado |
| 4 — Mobiliário de Terceiros | Itens dinâmicos por ambiente |
| 5 — Demais Itens que Interferem | Itens dinâmicos por ambiente |
| 6 — Observações Gerais | Campo livre opcional |

## Contribuindo

Para propor uma alteração: abra a versão mais recente, edite o HTML diretamente (não há build), teste abrindo o arquivo no navegador e valide o fluxo completo (preencher → gerar resumo → imprimir). Depois salve como a próxima versão numerada e registre a mudança no `CHANGELOG.md`.

Ver [CLAUDE.md](CLAUDE.md) para convenções internas do código.
