# Prompt Engineering
[← Return to Home](readMe.md)

---

## Working with Github CoPilot in VSCode
---
Notes from: https://code.visualstudio.com/docs/copilot/guides/context-engineering-guide

### [File Structure](https://code.visualstudio.com/docs/copilot/customization/overview#_parent-repository-discovery)
```
/project
    ARCHITECTURE.md
    PRODUCT.md
    CONTRIBUTING.md
    .github/
        copilot-instructions.md
    instructions/
        style.instuctions.md
    prompts/
        review.prompt.md
    agents/
        reviewer.agent.md
    skills/
        createAVerilogFile/
            SKILL.md
            /scripts

```

### copilot-instructions.md
---
Added to context at the begining of every new session.

Putting the below in this file will always add the basic project scope to the session.

```md
# [Project Name] Guidelines

* [Product Vision and Goals](../PRODUCT.md): Understand the high-level vision and objectives of the product to ensure alignment with business goals.
* [System Architecture and Design Principles](../ARCHITECTURE.md): Overall system architecture, design patterns, and design principles that guide the development process.
* [Contributing Guidelines](../CONTRIBUTING.md): Overview of the project's contributing guidelines and collaboration practices.

Suggest to update these documents if you find any incomplete or conflicting information during your work.
```

#### architecture.md
- Not part of Github Copilot
- Describes the overall architecture.

#### product.md
- Not part of Github Copilot
- Describes teh overall product

#### contributing.md
- Not part of Github Copilot
- rules for contributing to the project.

### Context Window Management
https://code.visualstudio.com/docs/copilot/concepts/customization#_customization-options-at-a-glance

| Item | When added to Context |
|---|---|
| Fresh Session| Clear Context|
| /clear| Clear Context|
|./github/copilot-instructions.md| Added to every request|
|.github/instructions/xxx.instructions.md| rules for specific file types as specified by YAML applyTo:|
|.github/prompts/xxx.prompt.md| Specific prompt that you use over and over|
|.github/agents/xxx.agent.md| Specific instructions for a designer, tester, reviewer  |
|.github/skills/xxx/SKILL.md| skills yo|

