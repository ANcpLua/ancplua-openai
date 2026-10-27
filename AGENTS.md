# ANcpLua marketplace

This is the only marketplace for own plugins. Each plugin owns its source in its
repository; do not copy skill directories into this catalog. Edit
`.agents/plugins/marketplace.json` for distribution and use
`scripts/local_marketplace.py` to link local working sources without copying them.
The generated `.local/marketplace` is machine-local and not committed.

Keep `ancplua-dotnet` responsible for the seven general .NET skills. Preserve
`nami` 0.1.1 as the current owner of its MSTest 4.5.1 APIs, assertions, fixture
ownership, C# unions and native messaging. `mstest-extensions` retains nine
specialized workflows and references; do not let an older overlapping instruction
override a newer verified Nami rule. qyl only packages qyl-specific skills.
Before removing another copy, compare supporting files, callers and build exports.
