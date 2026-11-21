# ArpoFlow no ChatGPT, Claude, Gemini, Codex, Claude Code e Antigravity

Use o ArpoFlow diretamente em uma conversa no ChatGPT, no Claude ou no Google Gemini. Você também pode instalar os plugins para Codex, Claude Code e Google Antigravity. Com as permissões da sua conta, você pode criar e editar sites e aplicativos, conferir prévias e publicar a versão escolhida.

## ChatGPT na web

Se o ArpoFlow já estiver disponível na sua conta, abra uma conversa no ChatGPT, digite `@`, selecione **ArpoFlow** e peça “Liste meus projetos”.

Para configurar a conexão em uma conta com permissão para adicionar servidores MCP, abra **Plugins → + → Adicionar servidor MCP personalizado**. Use o nome **ArpoFlow**, informe `https://api.arpoflow.com.br/mcp/openai` e escolha **OAuth**. Conclua a autorização na sua conta ArpoFlow e instale o plugin. A disponibilidade de ações de edição e publicação depende do plano e das permissões do workspace. [Guia da OpenAI](https://help.openai.com/en/articles/12584461-connecting-custom-mcp-servers-in-chatgpt).

## Claude na web

No Claude, abra **Personalizar → Conectores**. Se o ArpoFlow já estiver disponível, selecione **Conectar**. Para cadastrá-lo, adicione um conector web personalizado com o nome **ArpoFlow** e a URL `https://api.arpoflow.com.br/mcp`. Autorize o acesso no ArpoFlow. Em uma conversa, abra **+ → Conectores**, ative **ArpoFlow** e peça “Liste meus projetos”. Em contas de equipe, o administrador pode precisar adicionar o conector primeiro. [Guia da Anthropic](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp).

## Google Gemini

Se a sua conta oferecer apps personalizados, abra os [apps conectados do Gemini](https://gemini.google.com/customize/connectors), escolha **Personalizado** e cadastre o servidor MCP abaixo. Autorize a conexão pelo navegador e selecione o ArpoFlow usando `@` no chat.

```text
https://arpoflow-api.diogovieiradealni.workers.dev/mcp/gemini/v1
```

A disponibilidade depende da conta, do idioma e da região. [Guia de conexão do ArpoFlow](https://app.arpoflow.com.br/integracoes) · [Disponibilidade no Gemini](https://support.google.com/gemini/answer/17209137).

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

Conclua a autorização de acesso quando o Codex solicitar. Em uma nova conversa, selecione ArpoFlow e peça para listar seus projetos. A conexão usa o endpoint `https://api.arpoflow.com.br/mcp/openai`.

O catálogo do Codex contém 22 ferramentas para consultar a conta e trabalhar com arquivos, versões, prévias, verificação, exportação e publicação de projetos. Os quatro escopos contemplados são `account:read`, `projects:read`, `projects:write` e `deployments:write`. A autorização concedida determina quais ferramentas estarão disponíveis.

## Google Antigravity

Baixe o [plugin 1.0.4](https://github.com/dealni/arpoflow-plugin/releases/download/v1.0.4/arpoflow-antigravity-1.0.4.zip), extraia e execute no diretório que contém a pasta extraída:

```sh
agy plugin install ./arpoflow
agy plugin list
```

Inicie a autenticação pelo servidor MCP do plugin e autorize sua conta ArpoFlow. Em seguida, peça para listar os seus projetos. Consulte o [guia do pacote](plugins/arpoflow-antigravity/README.md).

## Exemplos de uso

- “Liste os projetos da minha conta e mostre a última versão de cada um.”
- “Crie um app de lista de tarefas com TanStack Start e gere uma prévia para eu revisar.”
- “Verifique a versão que acabei de editar e mostre o resultado antes de publicar.”

Ao aprovar uma publicação, identifique o projeto e a versão. O ArpoFlow aplica as permissões da sua conta e os limites disponíveis no seu plano.

## Privacidade e suporte

Em todos os clientes, as ferramentas enviam ao ArpoFlow as operações e os dados de projeto necessários à solicitação e devolvem os resultados ao cliente. Você pode revisar ou revogar o acesso pelo painel do ArpoFlow. [Conexões autorizadas](https://app.arpoflow.com.br/oauth/connections) · [Política de Privacidade](https://app.arpoflow.com.br/privacidade) · [Termos de Uso](https://app.arpoflow.com.br/termos).

O publicador é Diogo Vieira dos Santos. Para suporte, escreva para [contato@arpoflow.com.br](mailto:contato@arpoflow.com.br).
