# ArpoFlow no ChatGPT, Claude, Gemini, Codex, Claude Code e Antigravity

Use o ArpoFlow diretamente em uma conversa no ChatGPT, no Claude ou no Google Gemini. Você também pode instalar os plugins para Codex, Claude Code e Google Antigravity. Com as permissões da sua conta, você pode criar e editar sites e aplicativos, conferir prévias e publicar a versão escolhida.

[Abrir a primeira prévia](#abrir-a-primeira-prévia) · [Resolver falhas e retomar](#resolver-falhas-e-retomar) · [Revisar e publicar pelo painel](#revisar-e-publicar-pelo-painel)

## ChatGPT na web

Se o ArpoFlow já estiver disponível na sua conta, abra uma conversa no ChatGPT, digite `@`, selecione **ArpoFlow** e peça “Liste meus projetos”. Selecione `@ArpoFlow` nos pedidos que precisem consultar ou alterar um projeto.

No ChatGPT na web, a conexão MCP personalizada está disponível em workspaces Business, Enterprise e Edu para quem tem permissão de criação. Abra **Plugins → + → Adicionar servidor MCP personalizado**. Use o nome **ArpoFlow**, informe `https://api.arpoflow.com.br/mcp/openai` e escolha **OAuth**. Selecione **Criar como plugin**, autorize o acesso à sua conta ArpoFlow, revise as ferramentas descobertas e instale o plugin. Em uma conversa, mencione `@ArpoFlow` quando quiser usar uma ferramenta. [Guia da OpenAI](https://help.openai.com/en/articles/12584461-connecting-custom-mcp-servers-in-chatgpt).

## Claude na web

No Claude, abra **Personalizar → Conectores**. Se o ArpoFlow já estiver disponível, selecione **Conectar**. Para cadastrá-lo, adicione um conector web personalizado com o nome **ArpoFlow** e a URL `https://api.arpoflow.com.br/mcp`. Autorize o acesso no ArpoFlow. Em uma conversa, abra **+ → Conectores**, ative **ArpoFlow** e peça “Liste meus projetos”. Em contas de equipe, o administrador pode precisar adicionar o conector primeiro. [Guia da Anthropic](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp).

## Google Gemini

Se a sua conta oferecer apps personalizados, abra os [apps conectados do Gemini](https://gemini.google.com/customize/connectors), escolha **Personalizado** e cadastre o servidor MCP abaixo. Autorize a conexão pelo navegador e selecione o ArpoFlow usando `@` no chat.

```text
https://arpoflow-api.diogovieiradealni.workers.dev/mcp/gemini/v1
```

A disponibilidade depende da conta, do idioma e da região. No modo **Chat**, peça `@ArpoFlow List my ArpoFlow projects`. Se o Gemini responder sem executar a ação, mencione `@ArpoFlow` novamente, indique o projeto e peça a execução da ferramenta. Para uma prévia, indique a versão salva e peça a URL retornada pelo servidor. Confirme a ação se o Gemini solicitar. [Guia de conexão do ArpoFlow](https://app.arpoflow.com.br/integracoes#gemini) · [Disponibilidade no Gemini](https://support.google.com/gemini/answer/17209137).

## Claude Code

Com o Claude Code 2.1.292 ou posterior, execute no terminal:

```sh
claude plugin install arpoflow --marketplace dealni/arpoflow-plugin
```

Em versões anteriores com suporte a marketplaces, adicione a origem e instale o plugin:

```sh
claude plugin marketplace add dealni/arpoflow-plugin
claude plugin install arpoflow@arpoflow-plugins
```

Abra uma nova sessão do Claude Code, digite `/mcp`, selecione ArpoFlow e faça login na página de autorização. Revise as permissões solicitadas e use a conta em que deseja criar ou editar projetos. O catálogo do Claude inclui as ferramentas de autoria e as de gestão habilitadas para a sua conta, como consulta de dados e administração de jobs. O que você pode fazer depende das permissões concedidas.

Para atualizar o plugin, execute `claude plugin update arpoflow@arpoflow-plugins`.

## Codex

Adicione o catálogo do ArpoFlow e instale o plugin:

```sh
codex plugin marketplace add dealni/arpoflow-plugin
codex plugin add arpoflow@arpoflow-plugins
```

Conclua a autorização quando o Codex solicitar. Se precisar iniciar o login pelo terminal, execute `codex mcp login arpoflow` e autorize o acesso no navegador. Em uma nova conversa, selecione ArpoFlow e peça para listar seus projetos. A conexão usa o endpoint `https://api.arpoflow.com.br/mcp/openai`.

## Google Antigravity

Baixe o [plugin 1.0.5](https://github.com/dealni/arpoflow-plugin/releases/download/v1.0.5/arpoflow-antigravity-1.0.5.zip), extraia e execute no diretório que contém a pasta extraída:

```sh
agy plugin install ./arpoflow
agy plugin list
```

No Antigravity, abra **Customizations → Installed → ArpoFlow → MCP Servers** e escolha **Authenticate**. No CLI, abra `/plugin`, expanda **ArpoFlow** em **Installed** e escolha **Sign in**. Autorize sua conta ArpoFlow no navegador e peça para listar os seus projetos. [Guia do pacote](plugins/arpoflow-antigravity/README.md).

## Outro cliente MCP

Use um cliente que aceite Streamable HTTP e OAuth com registro dinâmico. Adicione `https://api.arpoflow.com.br/mcp` como servidor ArpoFlow e autorize sua conta no navegador.

## Abrir a primeira prévia

Se o navegador pedir login no ArpoFlow, entre com o código recebido por e-mail. Revise a conta, o perfil e as permissões na tela de autorização, confirme e volte ao assistente.

1. Ative o ArpoFlow no cliente e peça “Liste meus projetos do ArpoFlow”. Uma lista vazia confirma a leitura em uma conta sem projetos.
2. Envie o exemplo abaixo. Se o cliente pedir confirmação, aprove as ações de criar o rascunho, salvar os arquivos e gerar a prévia.
3. Abra a URL temporária devolvida pelo servidor. Guarde o ID do projeto e a versão para retomar a edição. Quem receber a URL pode abrir a prévia enquanto ela estiver válida.

> Use o ArpoFlow para criar um projeto de teste chamado Agenda de oficinas. Monte uma página com o título Agenda de oficinas e uma oficina de exemplo. Salve tudo em uma versão e gere a prévia dessa versão. Mostre o ID do projeto, a versão, a URL exata retornada pelo ArpoFlow e até quando vale. Mantenha o projeto como rascunho.

Essa jornada usa `list_projects`, `create_project`, `apply_changes` e `create_preview`. A criação retorna o projeto e, quando disponível, os arquivos iniciais. A edição salva a primeira versão em um lote. A prévia usa a versão confirmada pelo servidor. Quando a ferramenta oferecer `includeManifest`, passe `false` para receber só a sessão com a URL e a validade em `data.session`.

ChatGPT e Codex usam o perfil de autoria OpenAI. Gemini e Antigravity usam o perfil de autoria Google. Ambos oferecem ferramentas de conta, projetos, arquivos, verificação, prévia, publicação e exportação. Claude, Claude Code e clientes do recurso `/mcp` usam o catálogo completo, que pode incluir gestão de dados e jobs. Confira as ferramentas carregadas pelo cliente e os escopos autorizados. A prévia exige `projects:read` e `projects:write`. A publicação exige autorização específica para o projeto e a versão.

## Resolver falhas e retomar

Ative o ArpoFlow em outra conversa. Informe o ID do projeto ou o nome exato. Se aparecer mais de um resultado, confirme qual quer editar.

> No ArpoFlow, retome o projeto Agenda de oficinas. Leia a versão atual e os arquivos que precisar. Troque o título da página para Agenda de oficinas comunitárias e mantenha a oficina de exemplo. Salve sobre a versão consultada, gere a prévia da nova versão e mostre os IDs do projeto e da versão, a URL exata e a validade. Mantenha o projeto como rascunho.

| Sintoma                                                               | Como retomar                                                                                                                                                                                                                      |
| --------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Cliente pede login novamente ou mostra outra conta                    | Abra a conexão no cliente e faça login pelo navegador com a conta que contém o projeto. Liste os projetos e confirme o nome ou ID antes de editar.                                                                                |
| Leitura funciona e a escrita está bloqueada                           | Confirme se o cliente carregou as ferramentas de escrita, se a conexão inclui `projects:write` e se a ação foi aprovada. Atualize a descoberta quando o cliente oferecer essa opção.                                              |
| Criação ou gravação ficou sem resposta                                | No mesmo cliente, consulte `get_operation` se tiver o ID do projeto e da operação. Ao repetir a chamada, preserve a chave e os argumentos originais e respeite o horário de nova tentativa. Se faltar a chave ou o servidor indicar `response_omitted`, confira o projeto e a versão atual. |
| A versão-base mudou ou a compilação falhou                            | Releia a versão atual e confira as alterações, ou corrija o erro de compilação informado. Use uma nova chave para o lote revisado.                                                                                                |
| O link expirou ou ficou ausente                                       | Confira primeiro qual versão foi salva. Peça a execução de `create_preview` para essa versão e aguarde a URL do servidor. Você também pode abrir o projeto no painel e conferir a prévia da versão em exibição.                   |

## Revisar e publicar pelo painel

1. Abra o projeto no painel. No **Resumo**, confira o identificador do rascunho, a versão no ar e o estado da compilação e da verificação. Abra **Prévia** para conferir o rascunho.
2. Em **Publicar**, selecione **Versão para publicar** e revise os resultados da versão escolhida. Confirme a publicação e abra o endereço público registrado no painel.
3. Para voltar a uma versão que já esteve no ar, abra **Histórico → Publicações do site**, escolha a publicação e use **Reverter site para esta publicação**. A reversão troca a versão no endereço público e preserva o rascunho atual e os dados do aplicativo.

Os módulos configurados ficam em **Operação**. Os domínios ficam em **Configurações → Domínios**. [Projetos no painel](https://app.arpoflow.com.br/projects)

## Privacidade e suporte

Em todos os clientes, as ferramentas enviam ao ArpoFlow as operações e os dados de projeto necessários à solicitação e devolvem os resultados ao cliente. Você pode revisar ou revogar o acesso pelo painel do ArpoFlow. [Conexões autorizadas](https://app.arpoflow.com.br/oauth/connections) · [Política de Privacidade](https://app.arpoflow.com.br/privacidade) · [Termos de Uso](https://app.arpoflow.com.br/termos).

O publicador é Diogo Vieira dos Santos. Para suporte, escreva para [contato@arpoflow.com.br](mailto:contato@arpoflow.com.br).
