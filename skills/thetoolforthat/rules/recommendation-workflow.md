---
description: How to effectively use the recommend-tools MCP tool
alwaysApply: false
---

# Recommendation Workflow

## When to Use `recommend-tools`

Use the `recommend-tools` MCP tool when:
- User describes what they're building
- User asks "what should I use for..."
- User needs a tech stack suggestion
- User wants to compare options for a use case

## Crafting Good Use Case Descriptions

The `recommend-tools` tool works by keyword matching against tool descriptions. For best results:

### Include Specific Terms
**Good**: "building a SaaS dashboard with React and real-time updates"
**Less effective**: "building an app"

### Mention Technologies
**Good**: "React Native app with authentication"
**Less effective**: "mobile app"

### Describe the Domain
**Good**: "e-commerce checkout with subscription payments"
**Less effective**: "payment system"

## Presenting Recommendations

### Group by Category
Organize results by their category for clarity:

```markdown
## Recommended for building a SaaS dashboard

### Frontend & UI
- **shadcn/ui** - Customizable components for dashboards
- **Tremor Blocks** - 300+ dashboard blocks

### Authentication
- **Clerk** - User management and auth
- **WorkOS** - Enterprise SSO

### Analytics
- **OpenPanel** - Open-source analytics
```

### Highlight Top Picks
When several tools serve similar purposes, indicate which might be best for the specific use case.

### Suggest Combinations
Tools often work together. Mention natural pairings:
- "Supabase + Clerk for backend + auth"
- "shadcn/ui + Motion for animated UI"

## Handling Edge Cases

### Vague Requests
If the user's description is too vague:
1. Run the recommendation anyway
2. Ask clarifying questions based on results
3. Suggest using `list-categories` to narrow down

### No Good Matches
If recommendations don't seem relevant:
1. Use `search-tools` with key terms instead
2. Suggest alternative categories to explore
3. Ask user to describe their needs differently

### Technical Comparisons
When user wants to compare tools:
1. Get recommendations first
2. Highlight differences in descriptions
3. Note category/subcategory distinctions

## Example Interactions

**User**: "I'm building an AI chatbot app"
**Action**: `recommend-tools(useCase: "AI chatbot with voice interface and real-time responses")`
**Present**: Group by AI tools, Voice tools, and Real-time communication

**User**: "What do I need for a landing page?"
**Action**: `recommend-tools(useCase: "landing page design components animation")`
**Present**: Component libraries, Animation tools, Design kits

**User**: "Setting up a new startup"
**Action**: `recommend-tools(useCase: "startup infrastructure deployment authentication payments")`
**Present**: Full stack recommendation covering each area
