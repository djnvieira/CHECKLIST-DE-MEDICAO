# CLAUDE.md

Instruções para trabalhar neste repositório em sessões futuras.

## O que é este projeto

Um checklist HTML de página única (self-contained: HTML + CSS + JS inline, sem build, sem dependências) usado pela Fabrilis para padronizar o envio de projetos ao setor técnico antes da medição. Publicado via GitHub Pages.

**Não é** um projeto de aplicação com frontend framework, backend ou persistência de servidor. É deliberadamente simples: qualquer pessoa abre o arquivo com duplo clique ou pelo link do GitHub Pages, sem precisar instalar nada.

## Convenção de versionamento

Cada evolução relevante vira um **novo arquivo**, nunca uma edição in-place da versão anterior:

```
checklist-v3.html
checklist-v4.html
checklist-v4.1.html
checklist-v5.html   ← versão corrente
```

Regras:
- Sempre copie a versão anterior mais recente como ponto de partida (`cp checklist-vX.html checklist-vY.html`), depois edite a cópia.
- **Nunca edite uma versão já publicada** — quem tem o link antigo salvo não pode ter o comportamento trocado debaixo dos pés.
- Depois de editar, valide a estrutura antes de publicar (balanceamento de chaves/parênteses, funções referenciadas existem, nenhum resíduo de código morto da versão anterior):
  ```bash
  python3 -c "
  html=open('checklist-vY.html').read()
  for o,c in [('{','}'),('(',')'),('[',']')]:
      a,b=html.count(o),html.count(c)
      print(o,'OK' if a==b else 'MISMATCH')
  "
  ```
- Teste no navegador antes de publicar (preencher os campos obrigatórios via JS/DOM, clicar em "Gerar solicitação de medição", conferir que o resumo sai correto). Use o preview server se disponível.
- Registre a mudança no `CHANGELOG.md` com a lista objetiva do que mudou.
- `index.html` é a v1 original — mantido por compatibilidade, não editar.

## Estilo de código

- CSS via variáveis (`:root { --ink, --red, --green, ... }`), sem framework.
- JS vanilla, um único `<script>` IIFE por arquivo, sem módulos.
- Estado do formulário vive em um objeto `state{}` (chave = id do campo) mantido inteiramente em memória — não há `localStorage` nem backend. Fechar a aba perde o progresso; isso é aceito porque o formulário é preenchido de uma vez, na hora do envio.
- Padrão de nomes: `sec1items`, `sec2items` etc. para listas de itens fixos; `dynRows`, `dynEletros`, `bancadas` para coleções de itens adicionados dinamicamente pelo usuário.
- Toda validação de "resolvido" passa por `rowResolved(id)` — ao adicionar um novo tipo de campo obrigatório, atualizar essa função.
- O resumo final é montado como string HTML em `sum*()` functions (`sumEletros`, `sumBancadas`, `sumDyn`) — ao adicionar um quadro novo, criar a função de resumo correspondente e chamá-la na ordem certa dentro do listener do botão "finish".

## O que evitar

- Não introduzir build step (Vite/webpack/etc.) ou dependências de pacote sem alinhar antes — quebra a promessa de "abrir e usar" que é o ponto central da ferramenta.
- Não mover para múltiplos arquivos/módulos — a natureza de arquivo único é intencional para portabilidade (e-mail, pen-drive, GitHub Pages sem CDN).
- Não remover uma versão antiga do repositório sem confirmar que ninguém depende do link.
