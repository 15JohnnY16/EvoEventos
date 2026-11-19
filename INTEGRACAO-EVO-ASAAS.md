# EVO Eventos — integração futura

Atualizado após o design em 18/11/2026.

## Estado da entrega

**Esta etapa entrega somente o design.** Navegação e preenchimento de campos servem à avaliação visual. Nada é enviado, salvo, publicado, cobrado ou inscrito. Pessoas, eventos e estados são exemplos.

O usuário definiu um site próprio ligado ao sistema EVO e autorizou deixar as integrações em aberto neste documento. Não é necessário obter senhas ou chaves para avaliar o design.

## Conta existente EVO

**Tratar o aluno como alguém que já tem conta no sistema EVO. Não criar outra base de contas nem outro cadastro para o aluno.**

A etapa funcional deverá ser conectada ao serviço de identidade e às permissões do sistema existente, com contrato definido pelo responsável pelo Administrativo. O login próprio do Financeiro não foi identificado como login dos alunos.

O integrador deverá definir e verificar:

- Como iniciar o login existente e retornar ao evento escolhido com segurança.
- Como o servidor verifica a identidade e recebe um identificador estável da pessoa.
- Nome de exibição e contato permitido para a inscrição, vindos de fonte validada.
- Quais alunos/dependentes essa conta pode inscrever. Não presumir uma pessoa por conta.
- Como obter permissões de gestão, unidades e capacidades existentes da equipe.
- Como expirar/revogar a sessão e negar acesso a inscrições de outra pessoa.

Não confiar em nome, identificador de aluno ou perfil admin enviado pelo navegador. Não usar metadados editáveis pelo usuário como autorização. Não copiar chaves privilegiadas para o frontend. O método concreto de autenticação permanece pendente; não foi simulado como integração concluída.

## Asaas

O design prevê um link de pagamento e uma tela de acompanhamento. Nenhum link real, credencial, checkout, webhook ou chamada à API Asaas foi configurado.

Antes de ativar pagamento real, o responsável deverá verificar o limite `limit` do link e definir o vínculo entre inscrição e cobrança. Um link compartilhado pode ser reutilizado fora do site; o limite local não prova que todas as cobranças externas respeitam a lotação.

O retorno do Asaas é navegação, não prova de pagamento. A confirmação deve partir de evento financeiro autenticado e reconciliado ou de procedimento manual autorizado, rastreável e com identificador único da cobrança. Tratar valor divergente, pagamento duplicado, evento repetido, pagamento tardio, cancelamento e reembolso explicitamente.

Referências oficiais consultadas:

- [Criar link de pagamentos e parâmetro limit](https://docs.asaas.com/reference/criar-um-link-de-pagamentos).
- [Visão geral dos links e confirmação por eventos](https://docs.asaas.com/docs/payment-links-overview).
- [Eventos de pagamento](https://docs.asaas.com/docs/payment-events).

## Vagas, reservas e espera

Estas regras são requisitos futuros, **não funcionalidades implementadas**:

1. O servidor mantém `confirmados + reservas válidas <= capacidade` em operação atômica.
2. Uma inscrição ativa por evento e aluno, com idempotência para reenvios.
3. Sem vaga, a pessoa entra em espera FIFO atribuída pelo servidor, sem cobrança.
4. Promoção da fila reserva/oferece vaga; não confirma pagamento.
5. Não liberar uma reserva já encaminhada para pagamento enquanto a cobrança anterior ainda puder ser quitada, sem reconciliação/cancelamento externo seguro.
6. Impedir que um mesmo pagamento confirme duas inscrições e que a capacidade seja reduzida abaixo da ocupação comprometida.
7. Separar os estados editorial, inscrição e pagamento; preservar histórico e validar autorização em toda alteração.

As quantidades de exemplo seguem esta intenção: Open 40 confirmados + 6 em pagamento de 48 vagas = 2 disponíveis; clínica 12 + 6 de 24 = 6 disponíveis; Sunset 32 de 32, com 7 em espera.

## Administração futura

Implementar persistência, autorização existente por unidade, criação/edição, validação de datas e capacidade, publicação agendada por relógio do servidor, upload seguro de capa e exportação CSV protegida contra fórmulas. Armazenar instantes em UTC e editar/exibir em `America/Sao_Paulo`.

Antes do lançamento, validar concorrência na última vaga, idempotência, promoção FIFO, acesso entre alunos/unidades e todos os estados de pagamento em ambiente de testes. Confirmar também a experiência em Safari/iPhone real. A inspeção do design em viewport reduzido não substitui essas verificações.
