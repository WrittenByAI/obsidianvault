# AI Agent Workflow Strategy

## 1. Problem Identification
### Interaction Quality
- **Inconsistency**: Gemini 3 Pro demonstrates variable performance, specifically failing to adhere to instructions when prompts are unstructured (natural language).
- **Preference**: The user prefers natural language interaction (90% of the time) over rigid prompt engineering.

### Tool Usage
- **Laziness**: Significant reluctance to utilize external tools (specifically Search).
- **Superficiality**: often provides irrelevant data or lacks deep research capabilities (estimated 50% ineffective rate).

### Memory System
- **Opaque Mechanism**: The behavior of adding data to agent memory is unclear.
- **Pollution Risk**: High probability of accumulating obsolete, contradictory, or context-clogging information ("Knowledge Pollution").

---

## 2. Proposed Solution (The "Hybrid Model")

### Role Allocation
| Model | Assigned Function | Reasoning |
| :--- | :--- | :--- |
| **Opus 4.5** | **Primary Communication** | Superior adherence to complex instructions and natural language nuances. |
| **Gemini** | **Specialized Tasks** | Best for Multimodal inputs (Images/Video), Large Context handling, and rigidly structured automation where error rates can be calculated. |

### Implementation Steps
1. **Shift Interface**: Move all primary chat/reasoning tasks to Opus.
2. **Define Boundaries**: Use Gemini only when specific "Hard Skills" (Vision, massive context) are required.
3. **Memory Hygiene**: Implement stricter rules for what gets saved to long-term memory to avoid context decay.
