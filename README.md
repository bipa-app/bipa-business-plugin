# Bipa Business

Connect your company's Bipa Business account to compatible MCP clients, including Grok Bot, Grok Build, Cursor and Gemini CLI. Read balances, statements, payment requests, Pix charges, payment links, documents and payables. Create receiving links and charges, organize records and request outgoing payments.

## You control the account

- OAuth connects one company through an authorized member. Current company permissions and the granted OAuth scopes constrain access.
- Outgoing Pix and boleto requests wait for member confirmation and company approval in Bipa Business. No MCP tool approves them.
- Conversions, accepted target orders and savings movements execute immediately with their separate permissions and explicit confirmation. They do not pass through the outgoing-payment approval queue.
- Receiving operations and record changes also need their own scopes and confirmation. Sending a Pix charge by email or SMS is a separate action from creating it.
- Do not enter CPF, identity documents, passwords, PINs, authentication codes or tokens in chat. Account opening and identity verification happen on Bipa's own pages.

## Connect

Use `https://mcp.bipa.app/business/connector/mcp` with Streamable HTTP and OAuth. Sign in through Bipa, select the company and grant only the permissions you need. Never paste an access token into chat or a repository.

The package includes `.grok-plugin/plugin.json`, `.cursor-plugin/plugin.json`, `.mcp.json` and `mcp.json` for compatible plugin loaders, and `gemini-extension.json` for Gemini CLI. It runs no local code, hooks or scripts as part of installation or use.

For Gemini CLI:

```sh
gemini extensions install https://github.com/bipa-app/bipa-business-plugin
```

Example requests:

- What are my company's balances and this week's cash movements?
- Which payment requests are waiting for approval?
- Create a Pix charge for R$ 180 after I confirm.
- Which company bills are unpaid?
- Show a conversion quote and its exact terms before asking me to confirm.

## Validation and review

Hosted fictional verification on November 26, 2026 exercised all 52 Business account tools: 395 checks passed, with zero failures. It covered receiving, record changes, payment requests, conversions, target orders, savings, retries, refresh, account/resource isolation and revocation. No real funds or financial rails were used.

Dynamic client registration returned a timeout in that verification; the successful run used an existing public client. Real-member OAuth and fresh connections in Grok, Cursor, Gemini CLI and Perplexity remain unverified. Hosted tests do not establish client-specific approval or listing. Directory applications may still require provider review and testing.

Reviewers can request access to the isolated fictional reviewer flow through the submission contact. Credentials are exchanged privately and are never stored in this package. Keep the production connector URL and OAuth enabled during review.

The agent skill is synchronized from the public Bipa Business package at `bipa-app/claude-plugin`, revision `9f462772021a295febc2f714178c27417204ff4a`.

## Documentation and support

- [Business connector guide](https://agents.bipa.app/docs/business)
- [Business MCP reference](https://agents.bipa.app/docs/business/claude-code)
- [Privacy policy](https://suporte.bipa.app/hc/pt-br/articles/36305196684315)
- [Terms of use](https://suporte.bipa.app/hc/pt-br/articles/55072595716507-Termos-de-uso-aplicativo-Bipa)
- [Help center](https://suporte.bipa.app/hc/pt-br)

MIT license. See [LICENSE](LICENSE).
