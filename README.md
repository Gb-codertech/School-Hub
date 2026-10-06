# School Hub

Plataforma web para gestão de recursos e empréstimos de computadores escolares.

## Objetivo

O School Hub centraliza o ciclo de vida dos empréstimos de computadores portáteis numa escola:

**Reserva → Levantamento → Empréstimo → Devolução → Inspeção → Disponível/Manutenção → Reparação → Disponível**

O projeto foi desenvolvido no contexto de uma disciplina/UFCD escolar e privilegia uma solução funcional, segura, responsiva e adequada a uma demonstração académica.

## Funcionalidades principais

- Autenticação e controlo de acesso por perfil.
- Gestão de reservas.
- Levantamento de computadores com atribuição física dos equipamentos.
- Gestão de devoluções e inspeção individual.
- Gestão de computadores e manutenção.
- Gestão de alunos, cursos e turmas.
- Histórico e auditoria.
- Relatórios e indicadores.
- Definições administrativas.
- Regras de disponibilidade, atrasos e reservas não levantadas.
- Proteção de dados através de RLS e operações atómicas na base de dados.

## Perfis

- **Aluno:** consulta e gere as suas próprias reservas e empréstimos.
- **Secretaria:** gere reservas, levantamentos, devoluções, inventário e dados de alunos.
- **Admin:** inclui operações administrativas, manutenção/reparações, auditoria, turmas/cursos e definições.

## Stack

- React + TypeScript + Vite
- Tailwind CSS + shadcn/ui
- Supabase / PostgreSQL
- Supabase Auth
- TanStack Query
- Zod + React Hook Form

## Organização

- `docs/` — documentação técnica, testes e gestão do projeto.
- Código da aplicação — a sincronizar/exportar da plataforma de desenvolvimento para este repositório.

## Gestão do trabalho

A gestão do projeto utiliza GitHub para versionamento e Issues e Notion para o Kanban e acompanhamento visual das tarefas.

## Estado atual

O núcleo funcional da aplicação encontra-se em fase final de validação, documentação e preparação da entrega/demonstração.

> O repositório foi criado nesta fase para organizar o versionamento e a entrega. O histórico deve representar apenas alterações reais; não serão inventados commits retroativos.
