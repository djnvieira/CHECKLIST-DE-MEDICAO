# Changelog

Todas as mudanças relevantes deste projeto são documentadas aqui. Formato baseado em [Keep a Changelog](https://keepachangelog.com/pt-BR/1.0.0/).

Cada versão corresponde a um arquivo `checklist-vX.html` publicado lado a lado com os anteriores (ver [CLAUDE.md](CLAUDE.md) sobre a convenção de versionamento).

## [0.5.0] — checklist-v5.html — 2026-07-01

- Grid de Identificação reorganizado em linhas simétricas de 3 colunas (antes misturava campos de largura simples com `span2`, quebrando o alinhamento).
- Telefone do responsável: placeholder trocado para um número genérico (`(00) 0 0000-0000`) no lugar de um número pessoal.
- Eletrodoméstico "Geladeira" renomeado para "Refrigerador".
- Novo item "Ar condicionado" no Quadro 2 (Eletrodomésticos), com campo opcional de observação para especificar painel.
- Quadro 1 (Obra Civil): adicionados "Ponto de aspiração central" e "Ponto de ar condicionado".
- Novo **Quadro 6 — Observações Gerais**: campo de texto livre opcional, incluído no resumo final.

## [0.4.1] — checklist-v4.1.html — 2026-06-30

- Eletrodomésticos com necessidade de alimentação (Cooktop/Fogão, Forno, Micro-ondas, Geladeira, Freezer) ganharam campo "Alimentação" (Elétrico/Gás).
- Forno, Micro-ondas, Geladeira e Freezer ganharam campo "Necessidade de respiro" (Sim/Não) com especificação obrigatória quando "Sim".
- Quadro 1 (Obra Civil): adicionados "Base de alvenaria (cozinha)" e "Base de alvenaria (lavanderia)".

## [0.4.0] — checklist-v4.html — 2026-06-30

10 correções de revisão aplicadas sobre a v3:

- Removido o rótulo redundante "SOLICITAÇÃO DE MEDIÇÃO · INTERNO" do cabeçalho.
- Removido bloco "FABRILIS · MARCENARIA AUTORAL" duplicado no resumo.
- Endereço da obra desmembrado em logradouro, número, complemento e ponto de referência.
- Telefone do responsável com máscara automática `(DD) D DDDD-DDDD`.
- Datas do resumo exibidas no formato brasileiro (DD/MM/AAAA).
- Eletrodomésticos ganharam campo "Referência/Código" e dimensões passaram a ser em mm.
- Resumo do Quadro 3 (Bancadas/Cubas/Metais) reescrito em linhas separadas por item, em vez de uma linha corrida.
- Assinatura trocada de "Data do envio" para "Gerente".
- Removido rodapé duplicado no resumo.

## [0.3.0] — checklist-v3.html — 2026-06-30

Reconstrução a partir da v1 (a v2 havia ficado burocrática demais). Trocas principais:

- Campo "Arquiteto(a)" adicionado à Identificação.
- Quadro de metais/cubas reformulado duas vezes na mesma versão:
  - primeira tentativa: unificação de cuba + pedra + metal em "pontos de água", com Louças Sanitárias separadas;
  - versão final: arquitetura por **Bancada/Ambiente**, com tipo de cuba (Inox / Louça-vidro-acrílico / Esculpida / Não se aplica) determinando dinamicamente quais campos aparecem (modelo da cuba, especificação, metal vinculado). Quadro de Louças Sanitárias removido a pedido.

## [0.2.0] — checklist-v2.html — 2026-06-29

Versão expandida com 15 melhorias solicitadas (persistência em localStorage, avaliação prévia da obra, lista dinâmica de ambientes, validação visual reforçada, etc.) — posteriormente considerada burocrática demais e substituída pela reconstrução da v3.

## [0.1.0] — index.html — 2026-06-29

Versão inicial do checklist: identificação do projeto, obra civil, eletrodomésticos, cubas/louças, metais e acabamentos, mobiliário de terceiros e demais itens, com barra de progresso e geração de resumo para impressão/PDF.
