# Open Projects 📋

**Gerenciador de projetos open source e local-first: tempo, custos, pessoas, fotos e tudo sobre cada projeto, em um só lugar.**

> [!IMPORTANT]
> **Status: planejamento.** Ainda não há código neste repositório. Tudo o que está descrito abaixo é **planejado** — nada disso existe ainda. O caminho até a primeira versão está em **[PLANO.md](PLANO.md)**.

---

## Por que existe

Informação sobre um projeto costuma ficar espalhada: horas numa planilha, gastos no extrato, fotos no celular, contatos no WhatsApp, decisões na cabeça de alguém. O **Open Projects** quer juntar tudo isso numa **ficha única por projeto**, rodando no seu computador, com seus dados em um arquivo seu.

Pensado para quem toca vários projetos ao mesmo tempo — freelancers, pequenas equipes, obras e reformas, projetos pessoais ou de pesquisa.

## O que vai fazer

| Recurso | O que é | Situação |
|---|---|---|
| 🗂️ **Ficha do projeto** | Descrição, características, status, fotos e arquivos anexos | planejado (Fase 1) |
| ⏱️ **Controle de tempo** | Timer de iniciar/parar, lançamentos manuais e total acumulado por projeto | planejado (Fase 1) |
| 💰 **Custos e orçamento** | Lançamento de gastos, orçamento previsto e gráfico gasto × previsto | planejado (Fase 2) |
| 👥 **Pessoas e papéis** | Quem participa de cada projeto e com qual função | planejado (Fase 2) |
| ✅ **Tarefas em kanban** | Quadro simples de tarefas por projeto | planejado (Fase 2) |
| 📄 **Relatórios** | Exportar resumo do projeto (tempo, custos, pessoas) em PDF | planejado (Fase 3) |
| 🔄 **Sincronização opcional** | Sincronizar entre dispositivos, sem ser obrigatório | planejado (Fase 3) |

## Princípios

- **Local-first:** funciona offline; os dados ficam na sua máquina (banco SQLite planejado).
- **Open source:** código aberto, sem dependência de serviço pago.
- **Simples primeiro:** cada fase entrega algo utilizável antes de crescer.
- **Seus dados são seus:** fácil de exportar e fazer backup.

## Stack prevista

Ainda **não decidida em definitivo**. Sugestão atual: **Tauri + React + SQLite** (mesma base do projeto Company-Manager, do mesmo autor). A decisão é a primeira tarefa da Fase 1 do [PLANO.md](PLANO.md).

## Como instalar / rodar

Ainda não há o que instalar. Assim que existir uma versão executável, as instruções entram aqui.

## Como contribuir

O projeto está no começo, então ideias valem tanto quanto código:

1. Leia o [PLANO.md](PLANO.md) e veja em que fase estamos.
2. Abra uma *issue* com sugestão, dúvida ou caso de uso real seu.
3. Para código: faça um fork, crie uma branch a partir de `main` e abra um *pull request* ligado a um item do plano.

## Licença

Ainda não definida (sem arquivo `LICENSE` no repositório). Escolher a licença está no plano, Fase 0.

---

<sub>README e PLANO revisados em 21/10/2026 a partir da visão do André. Itens marcados como **planejado** ainda não existem no código.</sub>
