# Rule: Full Product Development Process

## Goal

To define a complete, step-by-step product development process that guides you through building applications from concept to implementation. This document serves as the master guide that links to detailed rule files for each development phase.

## Overview

This process ensures a systematic approach to product development, starting from high-level product definition down to detailed implementation tasks. Each step builds upon the previous one, creating a comprehensive foundation for successful product delivery.

## Process Flow

### Step 1: Define Product Vision

**Create Product Draft** - Establish the foundation of your product

- Define what the product is about
- Identify target users and their needs
- Articulate the problem/solution fit
- Establish your Unique Value Proposition (UVP)
- Document core user stories

**→ See detailed guide:** [create-product-draft.md](create-product-draft.md)

---

### Step 2: Design User Experience

**Create Design Document** - Design the complete user experience

- Map out user flows and journeys
- Define information architecture
- Specify detailed UX components for each page
- Document responsive design specifications
- Establish UI patterns and navigation systems

**→ See detailed guide:** [create-design-document.md](create-design-document.md)

---

### Step 3: Define System Architecture

**Create Architecture Document** - Establish technical foundation

- Design project folder hierarchy
- Define database schema and relationships
- Document API architecture
- Specify authentication and authorization
- Plan for performance and security

**→ See detailed guide:** [create-architecture.md](create-architecture.md)

---

### Step 4: Break Down Into Features

**Write PRD for Each Feature** - Detail feature requirements

- Create Product Requirements Documents (PRDs) for each major feature
- Define functional requirements and acceptance criteria
- Document user stories specific to the feature
- Establish success metrics
- Clarify scope and non-goals

**→ See detailed guide:** [create-prd.md](create-prd.md)

---

### Step 5: Generate Implementation Tasks

**Create Task Lists** - Break features into actionable tasks

- Generate detailed task lists from each PRD
- Break down features into parent and sub-tasks
- Identify relevant files and components
- Create clear, actionable items for implementation

**Important:** Prioritize frontend tasks over backend tasks to make the final output more visually predictable and testable early in the development cycle.

**→ See detailed guide:** [generate-tasks.md](generate-tasks.md)

---

### Step 6: Implement & Develop

**Develop Each Task** - Build the product following best practices

- Follow coding standards and conventions
- Reference architecture and design documents
- Write tests alongside implementation
- Maintain documentation as you build
- Follow all technical guidelines

**→ See detailed guide:** [dev-guidelines.md](dev-guidelines.md)
**→ See detailed guide:** [process-task-list.md](process-task-list.md)

---

## Using This Process with Claude Code

When starting a new project or feature, reference this file along with the specific step guide:

```
@full-process.md @create-product-draft.md
Let's start building [your product idea]
```

As you progress through each step, reference the next guide:

```
@full-process.md @create-design-document.md
I've completed the product draft, let's design the UX
```

## Process Principles

1. **Sequential but Iterative**: Follow steps in order, but iterate as needed
2. **Documentation First**: Document before coding to ensure clarity
3. **User-Centered**: Keep user needs at the center of all decisions
4. **Test-Driven**: Include testing at every stage
5. **Maintainable**: Write code and docs that others can understand

## Quick Reference

| Step | Document to Create | Rule File to Reference |
|------|-------------------|----------------------|
| 1 | Product Draft | [create-product-draft.md](create-product-draft.md) |
| 2 | Design Document | [create-design-document.md](create-design-document.md) |
| 3 | Architecture Document | [create-architecture.md](create-architecture.md) |
| 4 | PRD per feature | [create-prd.md](create-prd.md) |
| 5 | Task lists | [generate-tasks.md](generate-tasks.md) |
| 6 | Implementation | [dev-guidelines.md](dev-guidelines.md) |

## Next Steps

Start with Step 1: Reference [create-product-draft.md](create-product-draft.md) to begin defining your product vision.