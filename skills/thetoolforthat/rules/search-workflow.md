---
description: How to effectively use the search-tools MCP tool
alwaysApply: false
---

# Search Workflow

## When to Use `search-tools`

Use the `search-tools` MCP tool when:
- User asks for a specific tool by name ("What is Vercel?")
- User searches for a keyword ("animation libraries")
- User wants to find tools matching criteria ("tools for React")

## Search Strategy

### 1. Direct Name Search
When user mentions a specific tool name:
```
search-tools(query: "Vercel")
```

### 2. Keyword Search
When user describes what they need:
```
search-tools(query: "animation")
```

### 3. Filtered Search
When user wants tools in a specific domain:
```
search-tools(query: "components", category: "Frontend & UI")
```

## Handling Results

### Too Many Results (> 10)
- Suggest filtering by category
- Ask user to be more specific
- Show top 5 with option to see more

### No Results
- Try broader search terms
- Check for typos in query
- Suggest using `list-categories` to explore

### Few Results (1-5)
- Show all results with full details
- Suggest related searches

## Search Tips

1. **Use singular forms**: "animation" finds more than "animations"
2. **Category names work**: "deployment" matches "Deployment Platforms"
3. **Partial matches work**: "auth" finds authentication tools
4. **Case insensitive**: "react" = "React"

## Example Interactions

**User**: "Find me something for creating videos programmatically"
**Action**: `search-tools(query: "video")`

**User**: "I need a database that works well with serverless"
**Action**: `search-tools(query: "serverless database")`

**User**: "Show me design tools for creating mockups"
**Action**: `search-tools(query: "mockup", category: "Design & Creative")`
