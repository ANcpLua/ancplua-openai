# ancplua-openai

The Codex plugin marketplace for everything ANcpLua builds for Codex. The catalog lives in
`.agents/plugins/marketplace.json`; each plugin has one canonical source repository. The former standalone `nami` catalog is retired.

| Plugin | Repository | Purpose |
| --- | --- | --- |
| `ancplua-dotnet` | [ANcpLua/ancplua-dotnet](https://github.com/ANcpLua/ancplua-dotnet) | MSBuild, NuGet version chains, analyzer adoption and layered NuGet releases; routes MSTest work to the companion |
| `mstest-extensions` | [ANcpLua/mstest-extensions-plugin](https://github.com/ANcpLua/mstest-extensions-plugin) | Native MSTest/MTP execution, test writing, reusable extensions, quality reviews and Native AOT |
| `nami` | [ANcpLua/opusfix](https://github.com/ANcpLua/opusfix/tree/main/plugins/nami) | Current C# union, MSTest, assertion, fixture and Codex messaging guidance |
| `prepare-plugin-submission` | [ANcpLua/prepare-plugin-submission](https://github.com/ANcpLua/prepare-plugin-submission) | Submission preparation |

```bash
codex plugin marketplace add ANcpLua/ancplua-openai
codex plugin add ancplua-dotnet@ancplua-openai
codex plugin add mstest-extensions@ancplua-openai
codex plugin add nami@ancplua-openai
```

Plugins bundle their native skills, references and helpers. This GitHub marketplace
uses `nami` 0.1.1 for current MSTest 4.5.1 APIs, assertions and fixture ownership.
`mstest-extensions` retains its specialized execution and review references;
`ancplua-dotnet` owns general build, package, analyzer and release guidance.
Select the matching owner rather than loading both testing packages for one task. The marketplace
supports direct installation independently of the universal OpenAI plugin directory
and its submission eligibility rules. The skills remain available for automatic
selection and explicit invocation after installation.

Refresh this marketplace before installing an updated release:

```bash
codex plugin marketplace upgrade ancplua-openai
codex plugin list --marketplace ancplua-openai --json
```

Start a new session after changing installed plugins. This is the only own Codex marketplace.

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

## Local source development

Generate a machine-local catalog view from the same entries. This links source
directories and does not copy their skills. Explicit local paths preserve edits
that have not been published yet:

```sh
python3 scripts/local_marketplace.py \
  --source ancplua-dotnet=../stale/ancplua-dotnet \
  --source mstest-extensions=../stale/mstest-extensions-plugin \
  --source nami=../nami-plugin/plugins/nami \
  --source prepare-plugin-submission=../stale/prepare-plugin-submission
codex plugin marketplace add ./.local/marketplace
```

The checked-in catalog remains portable and names the source repositories.
The generated local view is ignored by Git and must not be published as a plugin
archive. Installing plugins is a separate action from registering the catalog.
`dedup-map.json` records the sixteen retired qyl copies and canonical fingerprints.


## Skill source ownership after cleanup

- Nami's union source is `../nami/.agents/skills/csharp-union-types`; the copy in
  `../nami-plugin/plugins/nami/skills` is its checked export. The extra
  `stale/csharp-union-types` checkout was removed. Union sync exports only to the
  plugin unless an additional distribution is explicitly selected.
- The eleven macOS skills are maintained in `~/.local/share/chezmoi/.agents/skills`
  and deployed to `~/.agents/skills`. The extra `stale/dotfiles` checkout was
  removed after its already-published commit was fast-forwarded into that source.
- Installed plugin caches, Chezmoi deployment files and the generated Claude
  package for Submission Studio are distribution outputs. Maintain their source;
  do not delete or independently edit those outputs as if they were competing sources.
- Nami's `fixture-lifecycle` owns product-specific workspace retention and cleanup.
  The plugin's `fixture-scope` owns portable MSTest fixture guidance. They have
  different responsibilities and remain separate.
- Qyl remains available for the pending auto-instrumentation comparison. Its
  product-specific skills are outside this cleanup; it is not part of the Nami
  developer plugin. The retired Downloads prototype was explicitly deleted.
