# ancplua-openai

The Codex plugin marketplace for everything ANcpLua builds for Codex. The catalog lives in
`.agents/plugins/marketplace.json`; every plugin is published from its own repository.

| Plugin | Repository | Purpose |
| --- | --- | --- |
| `ancplua-dotnet` | [ANcpLua/ancplua-dotnet](https://github.com/ANcpLua/ancplua-dotnet) | MSBuild, NuGet version chains, analyzer adoption, MSTest on Microsoft.Testing.Platform, layered NuGet releases |
| `mstest-extensions` | [ANcpLua/mstest-extensions-plugin](https://github.com/ANcpLua/mstest-extensions-plugin) | Native MSTest/MTP execution, test writing, reusable extensions, quality reviews and Native AOT |

```bash
codex plugin marketplace add ANcpLua/ancplua-openai
codex plugin add ancplua-dotnet@ancplua-openai
codex plugin add mstest-extensions@ancplua-openai
```

Plugins bundle their native skills, references and helpers. This GitHub marketplace
supports direct installation independently of the universal OpenAI plugin directory
and its submission eligibility rules. The skills remain available for automatic
selection and explicit invocation after installation.

Start a new session after installing. Claude Code has a separate catalog at
[ANcpLua/ancplua-anthropic](https://github.com/ANcpLua/ancplua-anthropic).

## Official documentation inventory

The primary official documentation collection is [OpenAI Plugins](https://developers.openai.com/plugins). Use the [documentation index](https://developers.openai.com/plugins/llms.txt) to discover pages and the [combined documentation export](https://developers.openai.com/plugins/llms-full.txt) as a source for retrieval and indexing. These are not substitutes for checking the current primary page when enforcing a release-sensitive rule.

| Domain | Official documentation |
| --- | --- |
| Architecture | [Plugin concepts](https://developers.openai.com/plugins/concepts/plugins), [MCP server concepts](https://developers.openai.com/plugins/concepts/mcp-server), [Skills concepts](https://developers.openai.com/plugins/concepts/skills) |
| Planning | [Use-case planning](https://developers.openai.com/plugins/plan/use-case), [Tool design](https://developers.openai.com/plugins/plan/tools) |
| Getting started | [Plugin quickstart](https://developers.openai.com/plugins/quickstart), [App quickstart](https://developers.openai.com/plugins/build/app-quickstart) |
| Server implementation | [Build an MCP server](https://developers.openai.com/plugins/build/mcp-server), [Examples](https://developers.openai.com/plugins/build/examples) |
| Skills | [Build skills](https://developers.openai.com/plugins/build/skills) |
| Authentication | [Authentication](https://developers.openai.com/plugins/build/auth) |
| UI | [ChatGPT UI](https://developers.openai.com/plugins/build/chatgpt-ui), [UI guidelines](https://developers.openai.com/plugins/concepts/ui-guidelines), [UI reference](https://developers.openai.com/plugins/reference) |
| Additional capabilities | [MCP Events](https://developers.openai.com/plugins/build/mcp-events), [Extensions](https://developers.openai.com/plugins/build/extensions), [Monetization](https://developers.openai.com/plugins/build/monetization) |
| Packaging | [Package your plugin](https://developers.openai.com/plugins/build/plugins), [Optimize metadata](https://developers.openai.com/plugins/guides/optimize-metadata) |
| Testing | [Connect and test](https://developers.openai.com/plugins/deploy/connect-chatgpt), [Troubleshooting](https://developers.openai.com/plugins/deploy/troubleshooting) |
| Security and policy | [Plugin guidelines](https://developers.openai.com/plugins/plugin-guidelines), [Security and privacy](https://developers.openai.com/plugins/guides/security-privacy) |
| Review | [Remote MCP review](https://developers.openai.com/plugins/deploy/app-review), [Submission errors](https://developers.openai.com/plugins/deploy/submission-errors) |
| Publication | [Upload and submit](https://developers.openai.com/plugins/deploy/submission) |
| Migration | [Submit a Claude plugin to OpenAI](https://developers.openai.com/plugins/guides/submit-claude-plugin) |
| API compatibility | [MCP tools and connectors](https://developers.openai.com/api/docs/guides/tools-connectors-mcp) |
| Evaluation design | [Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) |

Specialized product workflows are conditionally applicable: [local-services quote conversion](https://developers.openai.com/plugins/guides/local-services-request-quote-conversion-spec), [product checkout](https://developers.openai.com/plugins/guides/product-checkout-conversion-spec), and [restaurant reservations](https://developers.openai.com/plugins/guides/restaurant-reservation-conversion-spec).
