# ArpoFlow para Claude Code e Codex

Crie sites e aplicativos na sua conta ArpoFlow a partir de uma conversa no Claude Code ou no Codex. O plugin conecta o cliente ao servidor MCP do ArpoFlow e inclui instruções para trabalhar com versões, prévias e publicação. Apps novos podem usar React, TypeScript e TanStack Start com funções de servidor próprias.

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

## Codex

Adicione o catálogo do ArpoFlow e instale o plugin:

```sh
codex plugin marketplace add dealni/arpoflow-plugin
codex plugin add arpoflow@arpoflow-plugins
```

Conclua a autorização de acesso quando o Codex solicitar. Em uma nova conversa, selecione ArpoFlow e peça para listar seus projetos. A conexão usa o endpoint `https://api.arpoflow.com.br/mcp/openai`.

O catálogo do Codex contém 22 ferramentas para consultar a conta e trabalhar com arquivos, versões, prévias, verificação, exportação e publicação de projetos. Os quatro escopos contemplados são `account:read`, `projects:read`, `projects:write` e `deployments:write`. A autorização concedida determina quais ferramentas estarão disponíveis.

## Exemplos de uso

- “Liste os projetos da minha conta e mostre a última versão de cada um.”
- “Crie um app de lista de tarefas com TanStack Start e gere uma prévia para eu revisar.”
- “Verifique a versão que acabei de editar e mostre o resultado antes de publicar.”

Ao aprovar uma publicação, identifique o projeto e a versão. O ArpoFlow aplica as permissões da sua conta e os limites disponíveis no seu plano. No Claude Code, para atualizar este plugin, execute `claude plugin update arpoflow@arpoflow-plugins`.

## Privacidade e suporte

No Claude Code, o plugin se conecta a `https://api.arpoflow.com.br/mcp`. As ferramentas enviam ao ArpoFlow as operações e os dados de projeto necessários à solicitação e devolvem os resultados ao cliente. Você pode revisar ou revogar o acesso pelo painel do ArpoFlow. [Conexões autorizadas](https://app.arpoflow.com.br/oauth/connections) · [Política de Privacidade](https://app.arpoflow.com.br/privacidade) · [Termos de Uso](https://app.arpoflow.com.br/termos).

Para suporte, escreva para [contato@arpoflow.com.br](mailto:contato@arpoflow.com.br).
