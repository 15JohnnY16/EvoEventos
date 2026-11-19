# EVO Eventos — design entregue

Atualizado em 18/11/2026, após o pedido de limitar esta etapa ao design.

**Escopo vigente: somente design.** O protótipo visual está implementado e revisado. Nenhuma funcionalidade de negócio foi construída. A prévia privada foi publicada com sucesso: [abrir design EVO Eventos](https://evo-eventos-design.puffus.chatgpt.site).

## Decisões do usuário

- Site próprio para eventos EVO.
- Aluno tratado como alguém que já tem conta no sistema EVO.
- Conexão com identidade/permissões existentes e integração Asaas deixadas em aberto no Markdown final.
- Por ora: telas e apresentação; sem inscrições, pagamentos, persistência ou gestão reais.

O pedido mais recente substitui o escopo funcional do desenho inicial. Os requisitos para a etapa seguinte estão preservados em `evo-eventos/INTEGRACAO-EVO-ASAAS.md`.

## Design implementado

| Tela | O que pode ser avaliado |
|---|---|
| Catálogo | Capa editorial, categorias ilustrativas, filtros visuais, três cartões e estados de disponibilidade |
| Detalhe do EVO Open | Capa, data, local, programação, inclusões, preço e ação de inscrição |
| Inscrição | Nome e contato fictícios da conta EVO, resumo e sequência visual das etapas |
| Pagamento | Preparação para redirecionamento Asaas, métodos ilustrativos e orientação sobre confirmação |
| Lista de espera | Posição fictícia, expectativa de aviso e indicação de que não há cobrança durante a espera |
| Minhas inscrições | Exemplos de ingresso confirmado e participação em espera |
| Painel de eventos | Indicadores fictícios, tabela, estados editoriais e agenda |
| Participantes | Amostra fictícia com estados distintos e aba Todos os estados |
| Novo evento | Capa, título, descrição, unidade, categoria, datas, capacidade, preço, espera, agendamento e campo Asaas |

Use **Telas da prévia**, no topo, para navegar entre as nove telas. O detalhe de evento desenvolvido é o EVO Open; os demais cartões demonstram variações visuais. Botões sem tela correspondente exibem aviso de demonstração, em vez de navegar para outro evento.

## Identidade visual

Cores verificadas em [globals.css do Financeiro](https://github.com/15JohnnY16/EvoC/blob/main/src/app/globals.css): verde `hsl(142 76% 46%)`, fundo `hsl(222 47% 6%)`, superfícies azul-escuras e detalhes roxos. Fonte Inter variável, Phosphor Icons 2.1.2 regular, bordas limpas, raios moderados e sombras sutis. Não foi usado Lucide.

O nome EVO foi composto tipograficamente para o protótipo. Não foi recebido um arquivo de logotipo oficial. A imagem de quadra é gerada e ilustrativa, sem representar uma unidade real da EVO. Recortes e tratamentos de cor distinguem os cartões.

Foram consultados [Sympla](https://www.sympla.com.br/) e [Ingresso.com](https://www.ingresso.com/) como referências de organização do catálogo e de jornada, preservando a identidade EVO.

## Celular e acessibilidade

- Layout adaptado a 320 e 390 px, com cards em coluna e ações principais acessíveis.
- Campos de texto com 16 px e ampliação da tipografia de datas, estados e informações de inscrição.
- Ação de inscrição junto ao rodapé no celular, com consideração para a área segura do dispositivo.
- Tabelas administrativas com rolagem interna e indicação para deslizar.
- Navegação por teclado, foco visível, rótulos associados e respeito a movimento reduzido.
- Menu das telas com altura limitada e rolagem interna, inclusive em paisagem.

## Verificações executadas

As nove telas carregaram em 320 e 390 px, com imagens carregadas e sem corte dos componentes principais nas medições registradas. A página bloqueia deslocamento horizontal; tabelas e faixas de categorias têm rolagem interna intencional.

Catálogo, detalhe, inscrição, painel e formulário passaram por inspeção visual. O menu foi medido em 844 × 390 px: permaneceu dentro da janela, com suas opções acessíveis por rolagem. A sintaxe dos arquivos JavaScript foi conferida. Não foram encontrados erros no console na conferência do painel.

Uma revisão independente dos arquivos apontou e levou à correção de: links que trocavam o evento de exemplo; filtro incompatível com a amostra de participantes; aviso que antecipava um estado de pagamento; menu que poderia esconder opções em janela baixa.

**Limite da validação:** navegador desktop com viewport reduzido. Não foi feito teste em aparelho iPhone ou Safari real. Não foram executados testes de negócio, pois não há funcionalidades de negócio nesta etapa.

Capturas e medições estão em `evo-eventos/review/`, incluindo `catalogo-desktop.jpg`, `catalogo-mobile.jpg`, `admin-desktop.jpg`, `responsive-320.json` e `responsive-390.json`.

## Implementação e entrega

Arquivos em `evo-eventos/`, separados do Financeiro e dos arquivos sincronizados. HTML/CSS/JavaScript estáticos, recursos visuais locais e nenhuma dependência de backend. `README.md` contém as instruções de execução. A pasta `dist/` é a prévia pronta para hospedagem.

Nenhum banco, usuário, permissão ou deploy do Financeiro/Administrativo foi alterado. `sources/` foi preservado.

Acesso da prévia: privado, somente proprietário. A autenticação da hospedagem não representa a conta EVO do aluno.

## Funcionalidades futuras — ainda não implementadas

A conta existente EVO será conectada ao servidor com identidade validada, alunos/dependentes autorizados e permissões por unidade. Não criar cadastro paralelo nem aceitar perfil enviado pelo navegador.

Pagamento real depende da integração Asaas, limite de vendas verificado, vínculo da cobrança à inscrição e confirmação financeira autenticada/reconciliada. O retorno à página não comprova pagamento. Não há link de cobrança ativo no protótipo.

O controle de vagas deverá manter `confirmados + reservas válidas <= capacidade` atomicamente, com idempotência, fila FIFO e promoção sem cobrança antes de oferecer uma vaga. Persistência, upload, exportação, publicação agendada, auditoria e cancelamentos também ficam para a próxima etapa.

Contrato e critérios de aceite: `evo-eventos/INTEGRACAO-EVO-ASAAS.md`.

## Registro do recurso gerado

Arquivo: `evo-eventos/dist/assets/quadra-evo.png`. Gerado com a ferramenta integrada de imagens, sem CLI. O original foi preservado. Prompt utilizado:

> Use case: photorealistic-natural. Asset type: wide editorial photograph for a premium Brazilian tennis academy event website. Create a cinematic, realistic photograph of a pristine outdoor hard tennis court at golden hour in Brasília, no people, deep forest-green court surface with crisp white lines, a real tennis net crossing the middle, one tennis racket and two tennis balls subtly near the right foreground baseline, tropical trees and warm sunset outside the court. Sophisticated sports editorial photography with rich shadows, natural grain, believable perspective and accurate tennis court markings. Landscape 3:2 composition, visual interest concentrated on center and right so it can be cropped into a wide hero. No lettering, no logos, no graphics, no watermarks. Green, dark navy and warm sunlight palette. This is a fictional venue image for a design prototype.

## Registro da publicação

Prévia privada confirmada pela hospedagem em 18/11/2026. Commit publicado: 4a71c9d9f54d2c2516eeeb5459dc6fdf917f679b. O navegador alcançou a proteção de login ChatGPT; a inspeção das telas foi feita na prévia local. O site hospedado não foi inspecionado após login, pois a sessão do navegador não estava autenticada.


## Prévia adicional na Vercel

Publicada em 18/11/2026, a pedido do usuário: [EVO Eventos na Vercel](https://evo-eventos-design.vercel.app). Projeto separado `evo-eventos-design`, na equipe JohnnY's projects. Implantação `dpl_HACK3CuoThvJr3ie22y6eDhZdsh9`, estado READY. A Vercel classificou esta primeira implantação como production no projeto novo; o conteúdo continua sendo somente design estático. Página e arquivos JS/CSS retornaram HTTP 200 na conferência autenticada.

A proteção padrão da Vercel foi preservada. Foi fornecido ao usuário um link direto temporário de visualização; o endereço fixo acima pode solicitar autenticação Vercel após a expiração desse acesso. Nenhuma função de negócio ou integração foi adicionada.
