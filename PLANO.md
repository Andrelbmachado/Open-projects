# PLANO — Open Projects

Plano por fases, do zero até a primeira versão útil. Cada fase termina com algo **que roda e pode ser usado**. Marque `[x]` ao concluir e registre o PR ao lado do item.

**Estado atual (21/10/2026):** Fase 0 não iniciada — o repositório tem só documentação.

---

## Fase 0 — Fundação

**Objetivo:** repositório pronto para receber código.

- [ ] Decidir a stack e registrar a decisão em `docs/decisoes/0001-stack.md` (contexto, opções, escolha).
  - Sugestão: **Tauri 2 + React + TypeScript + SQLite**, mesma base do Company-Manager.
  - Critérios: roda offline, instalador leve para Windows/macOS/Linux, acesso a arquivos locais (fotos).
- [ ] Escolher licença (ex.: MIT ou AGPL-3.0) e adicionar `LICENSE`.
- [ ] Gerar o esqueleto do app (`npm create tauri-app`) com React + TS.
- [ ] Configurar lint/format (ESLint + Prettier) e testes (Vitest).
- [ ] CI no GitHub Actions: lint + testes + build em cada PR.
- [ ] Adicionar `.gitignore` adequado à stack.

**Pronto quando:** `npm run tauri dev` abre uma janela vazia e o CI passa verde num PR.

---

## Fase 1 — MVP: projetos e tempo

**Objetivo:** cadastrar projetos e saber quanto tempo foi gasto em cada um.

### Modelo de dados (SQLite)
- [ ] `projeto` — id, nome, descrição, status (`ideia` · `ativo` · `pausado` · `concluído`), data de início, criado/atualizado em.
- [ ] `caracteristica` — id, projeto_id, chave, valor (campos livres por projeto).
- [ ] `anexo` — id, projeto_id, tipo (`foto` · `arquivo`), caminho local, legenda.
- [ ] `registro_tempo` — id, projeto_id, início, fim (nulo = timer rodando), nota.
- [ ] Migrações versionadas desde a primeira tabela.

### Funcionalidades
- [ ] Lista de projetos com busca e filtro por status.
- [ ] Criar / editar / arquivar projeto.
- [ ] Ficha do projeto: descrição, características, galeria de fotos, arquivos.
- [ ] Anexar foto/arquivo copiando para a pasta de dados do app (não depender do caminho original).
- [ ] Timer iniciar/parar por projeto; só um timer ativo por vez.
- [ ] Lançamento manual e edição de registros de tempo.
- [ ] Total de horas por projeto (geral e no mês corrente).
- [ ] Backup: exportar/importar o banco + pasta de anexos em um `.zip`.

### Testes
- [ ] Testes de unidade para cálculo de horas (incluindo timer atravessando meia-noite).
- [ ] Teste de migração em banco vazio e em banco da versão anterior.

**Pronto quando:** dá para criar um projeto com 3 fotos, rodar o timer, fechar e reabrir o app, e ver as horas somadas corretamente. Publicar como release `v0.1.0`.

---

## Fase 2 — Custos, pessoas e tarefas

**Objetivo:** visão financeira e de equipe de cada projeto.

- [ ] Tabela `custo` — id, projeto_id, descrição, valor (em centavos, inteiro), data, categoria.
- [ ] Campo `orcamento_previsto` no projeto.
- [ ] Tela de custos com total gasto, saldo e gráfico **gasto × previsto** ao longo do tempo.
- [ ] Alerta visual quando o gasto passar de 80% e 100% do orçamento.
- [ ] Tabelas `pessoa` (nome, contato) e `participacao` (pessoa_id, projeto_id, papel).
- [ ] Opcional: registro de tempo associado a uma pessoa.
- [ ] Kanban por projeto: colunas `a fazer` · `fazendo` · `feito`, arrastar e soltar.

**Pronto quando:** um projeto mostra orçamento, gasto, quem participa e um quadro de tarefas. Release `v0.2.0`.

---

## Fase 3 — Relatórios e integrações

**Objetivo:** levar os dados para fora do app.

- [ ] Relatório PDF por projeto: resumo, horas, custos, pessoas e fotos selecionadas.
- [ ] Exportar CSV de registros de tempo e custos.
- [ ] Sincronização **opcional** entre dispositivos (avaliar Open Base); o app continua 100% funcional sem ela.
- [ ] Integração com o Company-Manager (definir antes: o que é compartilhado e em qual direção).

**Pronto quando:** é possível gerar um PDF de um projeto e sincronizar dois computadores de teste. Release `v0.3.0`.

---

## Fora do escopo (por enquanto)

- Versão web hospedada / multiusuário em servidor.
- App mobile.
- Integrações com ferramentas pagas (Jira, Trello etc.).

## Riscos e dúvidas em aberto

- **Fotos pesadas:** gerar miniaturas para a galeria não ficar lenta.
- **Moeda:** começar só com BRL ou já suportar várias?
- **Sincronização:** resolver conflitos sem servidor central é difícil — por isso fica na Fase 3 e é opcional.
