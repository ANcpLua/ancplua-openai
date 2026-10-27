# Marketplace moved to ancplua-dotnet

The active marketplace and all four plugin sources are now maintained together in [ANcpLua/ancplua-dotnet](https://github.com/ANcpLua/ancplua-dotnet).

This archived catalog keeps the existing `ancplua-openai` identity and forwards its entries to the new package paths so existing registrations remain resolvable. New registrations should use `ANcpLua/ancplua-dotnet`. The plugin IDs are unchanged.

Submission Studio now resolves to the verified **2.3.0** Account source imported with the owner's explicit authorization. The previous local 1.6.0 source is retired. Source migration does not automatically uninstall a separately installed Account plugin.

The old implementation and ownership notes remain in Git history. Maintain sources and run verification in the new repository.
