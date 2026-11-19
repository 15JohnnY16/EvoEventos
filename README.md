# EVO Eventos — prévia de design

Protótipo visual criado em 18/11/2026. Escopo atual: **somente design**, conforme pedido do usuário. Todos os eventos, nomes, quantidades, datas e valores são fictícios.

Repositório: [15JohnnY16/EvoEventos](https://github.com/15JohnnY16/EvoEventos).
Prévia: [EVO Eventos na Vercel](https://evo-eventos-design.vercel.app). A proteção padrão da Vercel pode solicitar login; links temporários de acesso direto expiram.

## Navegar

Abra a prévia e use **Telas da prévia**, no topo, para alternar entre nove telas. O caminho navegável de evento detalhado é o EVO Open; os demais cartões demonstram variações visuais. Controles de negócio mostram aviso de demonstração.

| Tela | Endereço relativo |
|---|---|
| Catálogo | `?view=catalogo` |
| Detalhe do EVO Open | `?view=evento` |
| Inscrição, dados | `?view=inscricao` |
| Pagamento, apenas visual | `?view=pagamento` |
| Lista de espera | `?view=espera` |
| Minhas inscrições | `?view=minhas` |
| Administração de eventos | `?view=admin` |
| Amostra de participantes | `?view=participantes` |
| Formulário de novo evento | `?view=editor` |

O formulário pode ser editado para avaliar campos e foco. Não salva, não publica e não atualiza o cartão de exemplo.

## Executar localmente

Com Node.js instalado, neste diretório:

```text
node preview.mjs
```

Abra `http://127.0.0.1:4173`. Não há instalação de dependências nem build: `dist/` é o resultado estático. Para conferir a sintaxe: `node --check dist/app.js` e `node --check preview.mjs`.

## Arquivos

- `dist/index.html`: entrada, metadados e carregamento local de recursos.
- `dist/styles.css`: identidade visual e adaptação a celular/desktop.
- `dist/app.js`: telas ilustrativas, navegação e avisos; sem APIs ou armazenamento.
- `dist/assets/`: imagem ilustrativa gerada, Inter variável, Phosphor Icons e licenças.
- `INTEGRACAO-EVO-ASAAS.md`: requisitos pendentes para a futura etapa funcional.
- `docs/superpowers/specs/2026-11-18-evo-eventos-design.md`: desenho atualizado após a entrega visual.
- `docs/superpowers/plans/2026-11-18-evo-eventos-design.md`: plano e registro da etapa de design.
- `review/`: capturas e medições da revisão local, excluídas da publicação.

## Hospedagem na Vercel

A prévia atual foi enviada diretamente à Vercel. A conexão automática deste repositório com a Vercel não foi configurada nesta etapa.

Para uma futura importação do repositório, usar o preset **Other**, sem comando de instalação ou build, e o diretório de saída **dist**. O site continua estático, sem variáveis de ambiente ou serviços externos necessários ao design.

## Verificação

As nove telas foram carregadas em larguras de 320 e 390 px: imagens carregadas e componentes principais dentro da largura de conteúdo. O painel usa rolagem interna na tabela e bloqueia deslocamento horizontal da página. Menu da prévia revisado também em 844 × 390 px, com rolagem interna.

Foram feitas inspeção visual de catálogo, detalhe, inscrição, painel e formulário; revisão independente de arquivos; correções de navegação entre exemplos, estado de pagamento, filtro da amostra e altura do menu. A validação usa navegador desktop com viewport reduzido, **não um iPhone ou Safari real**.

Não existe backend, sessão EVO, banco, inscrição, controle real de vagas, exportação, upload, agendamento ou integração Asaas nesta entrega.

## Recursos visuais

Cores de referência verificadas em `15JohnnY16/EvoC/src/app/globals.css`: verde `hsl(142 76% 46%)`, fundo `hsl(222 47% 6%)`, superfícies escuras e detalhes roxos. O nome EVO foi composto tipograficamente para o protótipo; não foi entregue um arquivo de logotipo oficial.

Ícones: [Phosphor Web 2.1.2](https://github.com/phosphor-icons/web), peso regular, MIT. Fonte: [Inter variável, Google Fonts](https://github.com/google/fonts/tree/main/ofl/inter), OFL. Licenças incluídas nos assets. Sem Lucide.

`dist/assets/quadra-evo.png` foi criado pelo gerador de imagens integrado para este protótipo. Não representa uma unidade real nem uma foto oficial da EVO. Prompt resumido: fotografia editorial realista de quadra verde de tênis em Brasília ao pôr do sol, sem pessoas, com rede, raquete e bolas no primeiro plano, árvores tropicais, sem texto, marcas ou logotipos. A imagem foi usada com recortes e tratamentos CSS nos cartões, sem alterar o arquivo original.
