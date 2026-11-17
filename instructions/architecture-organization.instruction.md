# General source organization principle

Organize source code around recognizable responsibilities and dependency
boundaries as a project grows. Choose names that describe the domain and the
role of a component, and place coordinating workflows above the services and
adapters they compose. Keep entry points thin where practical; make dependencies
and public interfaces explicit. Avoid adding directories or abstraction layers
that do not clarify ownership, reuse, or change boundaries. Adapt the structure
to the size and conventions of each project rather than applying a fixed tree.

Before a structural change, map existing behavior, public interfaces and
cross-module dependencies. Preserve compatibility when it matters, or document
and coordinate an intentional breaking change. Move in coherent stages and run
relevant behavior, integration and packaging checks; update navigation and
operational documentation. A directory name alone is not proof of a clean
architecture, so identify remaining cycles or cross-layer coupling honestly.

Examples, to adapt rather than copy:

- A GPU experiment service might separate packs, execution, artifacts,
  resources, scheduling and durable state.
- A web shop might separate catalog and checkout domain logic, persistence and
  payment integrations, and HTTP entry points.
- A small data analysis might keep related loading, transformation and plotting
  functions together until their responsibilities warrant separate modules.

