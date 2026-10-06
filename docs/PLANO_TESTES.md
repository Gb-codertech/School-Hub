# Plano de Testes e Aceitação

Um teste só deve ser marcado como concluído depois de executado e observado na aplicação.

## T01 — Autenticação
Validar login, rejeição de credenciais inválidas e carregamento do perfil correto.

## T02 — Criação de reserva
Validar datas/horas, disponibilidade, quantidade e limites de duração.

## T03 — Gestão de reserva pela secretaria
Validar pesquisa, filtros e ações permitidas sobre uma reserva.

## T04 — Levantamento
Validar seleção apenas de computadores disponíveis, quantidade correta, criação do empréstimo e mudança dos equipamentos para `emprestado`.

## T05 — Devolução normal
Validar inspeção e regresso dos equipamentos normais a `disponivel`.

## T06 — Devolução com dano/problema
Validar criação de manutenção, mudança para `manutencao` e preservação do histórico.

## T07 — Devolução incompleta
Validar equipamento não devolvido como `indisponivel` e empréstimo sem conclusão total incorreta.

## T08 — Atrasos
Validar identificação de empréstimos fora do prazo no dashboard e listas.

## T09 — Reserva não levantada
Validar transição para `nao_levantada` após a tolerância e libertação da capacidade.

## T10 — Permissões
Validar que aluno, secretaria e admin só conseguem executar operações autorizadas.

## T11 — Concorrência
Validar que duas operações concorrentes não conseguem atribuir o mesmo computador.

## T12 — Integridade
Validar ausência de referências órfãs e de múltiplos empréstimos ativos incompatíveis para o mesmo computador.

## T13 — Responsividade e acessibilidade
Validar desktop/mobile, navegação por teclado, foco, labels/ARIA, contraste e legibilidade.

## T14 — Auditoria
Validar que operações relevantes registam ação, entidade e utilizador.

## T15 — Demonstração ponta a ponta
Executar: Reserva → Levantamento → Empréstimo → Devolução → Inspeção → Disponível/Manutenção → Histórico.

## Regra de evidência

Não marcar um teste como concluído apenas porque o código parece correto. Registar o resultado depois da execução manual ou de evidência equivalente.
