# AI Agent Operational Rules

## 1. Memory Management (Anti-Pollution Policy)
To prevent "Memory Pollution" and context decay:
- **Explicit Trigger Only**: Do NOT use the `save_memory` tool for general conversation or temporary context.
- **Fact Verification**: Only save high-level user preferences or permanent project facts.
- **Ambiguity Check**: If unclear, ask: *"Should I add this to permanent memory?"* before saving.
- **No Redundancy**: Do not save facts that are already present in project files (e.g., tech stack in `package.json`).

## 2. Tool Usage Guidelines (Anti-Laziness Policy)
To ensure depth and accuracy:
- **Mandatory Search**: When answered with "I don't know" or general knowledge, MUST use `google_web_search` or `search_file_content` first.
- **Verification Loop**: If a tool returns empty results, try a broader query or a different directory before giving up.
- **Filesystem First**: Always `list_directory` or `glob` to verify file existence before attempting to read or edit.
