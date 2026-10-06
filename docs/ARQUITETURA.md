# Arquitetura e Estado do Sistema

## Visão geral

O School Hub é uma aplicação web para gestão do ciclo de vida de computadores portáteis escolares.

### Fluxo principal

1. O aluno cria uma reserva.
2. A secretaria valida e realiza o levantamento.
3. São selecionados os computadores físicos disponíveis.
4. É criado o empréstimo.
5. Na devolução, cada equipamento é inspecionado.
6. Equipamentos normais regressam a `disponivel`.
7. Equipamentos com dano/problema passam para `manutencao`.
8. Equipamentos não devolvidos passam para `indisponivel`.
9. Após reparação, um equipamento pode regressar a `disponivel`.

## Perfis

### Aluno
Pode consultar e gerir as próprias reservas e consultar os próprios empréstimos. Não pode gerir computadores, realizar levantamentos/devoluções nem consultar auditoria global.

### Secretaria
Pode gerir reservas, levantamentos, devoluções, inventário e os dados de alunos permitidos pelo sistema. Não gere papéis nem operações administrativas exclusivas do administrador.

### Admin
Inclui operações administrativas, manutenção/reparações, auditoria, turmas/cursos e definições.

## Estados

### Computadores
- `disponivel`
- `emprestado`
- `manutencao`
- `indisponivel`

O estado `reservado` não é utilizado. As reservas representam quantidade; os equipamentos físicos são atribuídos apenas no levantamento.

### Reservas
- `pendente`
- `confirmada`
- `em_curso`
- `concluida`
- `cancelada`
- `nao_levantada`
- `atrasada`

### Empréstimos
- `ativo`
- `devolvido`
- `atrasado`
- `devolução incompleta`

## Regras relevantes

- Timezone: Europe/Lisbon.
- Horário de reservas: 07:00–22:00.
- Duração mínima: 15 minutos.
- Duração máxima: 7 dias.
- Tolerância para levantamento: 30 minutos.
- Reservas não levantadas deixam de ocupar capacidade após a tolerância.
- A disponibilidade é validada de forma atómica no backend.
- Operações críticas são protegidas contra concorrência.
- Alterações administrativas relevantes ficam registadas em auditoria.

## Segurança

O sistema utiliza autenticação e Row Level Security (RLS) para limitar o acesso aos dados conforme o perfil. As regras críticas não devem depender apenas da interface; a validação deve existir também no backend/base de dados.

## Entidades principais

- `profiles`
- `user_roles`
- `courses`
- `classes`
- `laptops`
- `reservations`
- `loans`
- `loan_items`
- `maintenance_records`
- `audit_logs`
- `app_settings`

## Repositório

Este documento descreve o sistema desenvolvido. O código-fonte deverá ser sincronizado para este repositório antes da entrega final, para que o GitHub contenha também a implementação efetiva.
