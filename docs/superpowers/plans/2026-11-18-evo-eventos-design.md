# EVO Eventos — plano de implementação visual

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox syntax for tracking.

**Goal:** Entregar apenas o design navegável das telas EVO Eventos, conforme o novo pedido do usuário.
**Architecture:** Protótipo estático em HTML/CSS/JavaScript, com dados fictícios, sem backend ou ações de negócio. Navegação entre telas serve para revisão visual.
**Tech Stack:** HTML semântico, CSS responsivo, JavaScript mínimo, Phosphor Icons.
**Spec:** docs/superpowers/specs/2026-11-18-evo-eventos-design.md, subordinado ao pedido de 18/11: somente design.

## Global Constraints

- Não implementar autenticação, inscrições reais, pagamentos, persistência ou controle real de vagas nesta etapa.
- Conta existente EVO e integração Asaas permanecem documentadas como futuras.
- Usar as cores verificadas do Financeiro, Phosphor Icons, sombras sutis e bordas limpas.
- Criar tudo em evo-eventos/, preservando sources/ e sistemas existentes.
- Demonstrar catálogo, detalhe, inscrição, espera, inscrições do aluno, painel e edição de evento.
- Confirmar visual em largura de iPhone e desktop; não alegar teste em iOS real.

## Review Focus

- Em 320–390px, a página não pode rolar horizontalmente nem esconder ações importantes.
- Teclado e navegação precisam de foco visível, rótulos, contraste e áreas de toque adequados.
- Elementos de inscrição e pagamento são exemplos visuais claramente sinalizados.
- Estados de lista de espera e pagamento não podem parecer confirmações reais.
- Arquivos locais, fontes e imagens devem carregar e ter alternativas adequadas.

## Task 1: Direção visual e telas

**Files:** evo-eventos/dist/index.html, styles.css, app.js, assets/*.
**Interfaces:** view=<catalogo|evento|inscricao|espera|minhas|admin|editor> seleciona uma tela de demonstração. Sem APIs de negócio.

- [x] Criar capa editorial esportiva, tipografia, cores e elementos Phosphor.
- [x] Montar catálogo e detalhe com hierarquia clara e conteúdo fictício coerente.
- [x] Montar inscrição e espera, sem envio ou cobrança real.
- [x] Montar painel, listas e editor de evento apenas visuais.
- [x] Inspecionar arquivos e carregar todas as telas em servidor local.

## Task 2: Revisão responsiva e entrega

**Files:** evo-eventos/README.md, INTEGRACAO-EVO-ASAAS.md, documento de desenho atualizado, capturas de revisão.

- [x] Conferir desktop, 390px e 320px; revisar contraste, rolagem, imagens e foco.
- [x] Executar revisão independente do conjunto e corrigir problemas materiais.
- [x] Atualizar o desenho com telas efetivamente entregues e limitações verificadas.
- [x] Entregar prévia privada pelo fluxo Sites quando disponível e registrar o endereço real.

## Decisões de execução

- Implementação direta nesta sessão; o usuário já autorizou executar somente o design.
- A pasta não é um repositório Git; o novo subdiretório isola os arquivos. Git de publicação será gerido pelo fluxo Sites.
- Protótipo visual reversível: verificar por inspeção e navegador, sem testes que apenas repitam marcação e estilo.
- Não há dependência de banco, Supabase, chaves Asaas ou acesso ao Administrativo.

## Progresso

- Planejamento e conferência do escopo: concluídos.

- Etapa visual concluída. Prévia privada publicada; integrações futuras documentadas. Capturas e medições registradas em evo-eventos/review/.
