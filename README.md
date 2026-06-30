# Planner (proof-of-done)

Evidence-gated task verification for AI agents. Hosted MCP server — nothing to install.

**MCP endpoint:** `https://planner.monopoly-gold.com/_mcp`

## What it does

Planner prevents AI agents from marking tasks "done" on trust alone. Every goal goes through a verification gate:

1. **Decompose** — break a goal into acceptance criteria with behavioral checks
2. **Attach evidence** — screenshot, curl output, file, or text artifact per criterion
3. **Independent judge** — LLM evaluates evidence against the criterion and accepts or rejects

Goals stay open until every acceptance criterion has passing evidence.

## Key features

- **Goal hierarchy** — projects, milestones, goals, tasks with parent-child relationships
- **Acceptance criteria** — behavioral, observable checks (not "Denis approves")
- **Evidence model** — attach files or text per criterion; plain notes don't satisfy the gate
- **LLM judge** — independent verdict on each piece of evidence
- **Gate-keeper interview** — 3 questions on goal creation: why, where in the tree, how we'll verify
- **Dependencies & blockers** — cross-goal blocking with auto-unblock on resolution
- **Tree & summary views** — full hierarchy traversal and project-level summaries

## MCP tools (24)

| Category | Tools |
|----------|-------|
| **Projects** | `project-list`, `project-get`, `project-create`, `project-delete`, `project-add-dependency`, `project-remove-dependency` |
| **Goals** | `goal-list`, `goal-get`, `goal-tree`, `goal-create`, `goal-update`, `goal-delete`, `goal-move`, `goal-reorder`, `goal-summary`, `goal-todo` |
| **Criteria** | `goal-add-criterion` |
| **Evidence** | `goal-attach-evidence`, `goal-add-evidence-text`, `goal-remove-evidence`, `goal-request-upload` |
| **Blockers** | `goal-block`, `goal-remove-blocker` |
| **Account** | `account-delete` |

## Connect

Planner is a hosted remote MCP server using [streamable HTTP transport](https://modelcontextprotocol.io/specification/2025-03-26/basic/transports#streamable-http) with OAuth 2.1 authentication and [Dynamic Client Registration (RFC 7591)](https://datatracker.ietf.org/doc/html/rfc7591).

### Claude Desktop / Claude Code

Add to your MCP configuration:

```json
{
  "mcpServers": {
    "planner": {
      "type": "url",
      "url": "https://planner.monopoly-gold.com/_mcp"
    }
  }
}
```

OAuth login happens automatically on first connection.

### Any MCP client

Point your client to `https://planner.monopoly-gold.com/_mcp` — the server supports MCP discovery and standard OAuth 2.1 flow.

## Directory listings

| Directory | Status | Link |
|-----------|--------|------|
| **Glama** | ✅ Live, Healthy | [glama.ai/mcp/connectors/…/planner-proof-of-done](https://glama.ai/mcp/connectors/com.monopoly-gold.planner/planner-proof-of-done) |
| **mcp.so** | ✅ Published | [mcp.so/server/planner](https://mcp.so/server/planner/Denis%20Davidovich) |
| **awesome-mcp-servers** | ⏳ PR under review | [PR #8708](https://github.com/punkpeye/awesome-mcp-servers/pull/8708) |

## Links

- **Homepage:** https://planner.monopoly-gold.com
- **Demo:** https://planner.monopoly-gold.com/demo
- **MCP endpoint:** `https://planner.monopoly-gold.com/_mcp`

## License

Proprietary. Planner is a hosted service — this repository contains documentation only.
