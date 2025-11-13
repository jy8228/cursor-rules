# Rule: Generating a Product Draft

## Goal

To guide an AI assistant in creating a clear, comprehensive Product Draft document that establishes the foundation for the entire product development process. This document defines the product vision, target users, core problem/solution, and value proposition.

## Process

1. **Receive Initial Prompt:** The user provides a product idea, concept, or request to create a new product.
2. **Ask Clarifying Questions:** Before writing the Product Draft, the AI must ask clarifying questions to understand the product vision, target market, and key objectives. AI assistant can skip this step if all details are already clarified by user's prompt or provided documents. Make sure to provide options in letter/number lists so the user can respond easily with their selections.
3. **Generate Product Draft:** Based on the initial prompt and the user's answers to the clarifying questions, generate a Product Draft using the structure outlined below.
4. **Save Product Draft:** Save the generated document as `product-draft.md` inside the `/tasks` directory.

## Clarifying Questions (Examples)

The AI should adapt its questions based on the prompt, but here are some common areas to explore:

### Product Understanding
- **Core Problem:** "What specific problem does this product solve?"
- **Current Solutions:** "How do people currently solve this problem? What are the alternatives?"
- **Product Vision:** "What is your vision for this product? Where do you see it in 1-2 years?"

### Target Market
- **Primary Users:** "Who are the primary users of this product? Can you describe their demographics and characteristics?"
- **User Segments:** "Are there different types of users who will use this product differently?"
- **Market Size:** "Do you have a sense of the market size or target audience size?"

### Value Proposition
- **Key Benefits:** "What are the top 3 benefits users will get from this product?"
- **Differentiation:** "What makes this product different from existing solutions?"
- **Core Features:** "What are the must-have features for the initial version?"

### Business Context
- **Business Model:** "How will this product generate value? (e.g., subscription, one-time purchase, freemium)"
- **Success Metrics:** "How will you measure if this product is successful?"
- **Constraints:** "Are there any technical, budget, or timeline constraints we should know about?"

## Product Draft Structure

The generated Product Draft should include the following sections:

---

### 1. Product Overview

```markdown
# Product Draft: [Product Name]

## Executive Summary
A brief 2-3 sentence description of what the product is and why it matters.

## Product Vision
A clear statement of the product's long-term vision and the change it aims to bring to users' lives.

**Example:**
"To become the go-to platform for small business owners to manage their finances effortlessly, enabling them to focus on growing their business instead of bookkeeping."
```

---

### 2. Problem Statement

```markdown
## Problem Statement

### The Problem
Clearly articulate the problem this product solves. Be specific about:
- What pain point exists?
- Who experiences this problem?
- How frequently does this problem occur?
- What is the impact of this problem?

**Example:**
"Small business owners spend an average of 10 hours per week on manual bookkeeping tasks, taking time away from business growth activities. Current accounting software is either too complex for non-accountants or lacks essential features for business management."

### Current Alternatives
Document how people currently solve this problem:
- Existing solutions (competitors, workarounds)
- Limitations of current approaches
- Why current solutions are insufficient

### Market Opportunity
- Target market size
- Growth trends
- Why now is the right time for this product
```

---

### 3. Target Users

```markdown
## Target Users

### Primary User Persona

#### [Persona Name] - [Role/Title]

**Demographics:**
- Age range: [e.g., 25-45]
- Location: [e.g., Urban areas, United States]
- Education: [e.g., College educated]
- Income level: [if relevant]

**Professional Context:**
- Job role/title
- Industry/sector
- Company size
- Technical proficiency level

**Goals and Motivations:**
- What are they trying to achieve?
- What drives their decisions?
- What does success look like for them?

**Pain Points:**
- Current challenges they face
- Frustrations with existing solutions
- Barriers to achieving their goals

**Behaviors:**
- How do they currently solve this problem?
- What tools/products do they use?
- How do they prefer to interact with software?

### Secondary User Personas
[Repeat structure for any additional user types]
```

---

### 4. Solution Overview

```markdown
## Solution Overview

### Proposed Solution
A clear description of how the product solves the identified problem.

**What it does:**
- Core functionality in plain language
- Key features that address user pain points
- How it improves upon existing solutions

**How it works:**
- High-level explanation of the user experience
- Main workflows and interactions
- Integration with existing tools (if applicable)

### Unique Value Proposition (UVP)

**One-sentence pitch:**
"[Product Name] helps [target user] to [solve problem] by [unique approach/benefit]"

**Example:**
"FinanceFlow helps small business owners manage their finances in under 30 minutes per week by automating bookkeeping and providing actionable insights in plain English."

**Key Differentiators:**
1. [Differentiator 1]: Why this matters to users
2. [Differentiator 2]: Why this matters to users
3. [Differentiator 3]: Why this matters to users
```

---

### 5. Core User Stories

```markdown
## Core User Stories

Define the essential user journeys that the product must support. These are high-level stories that capture the main value propositions.

### Must-Have User Stories (MVP)

**Story 1: [Story Title]**
- **As a** [type of user]
- **I want to** [perform some action]
- **So that** [achieve some goal/benefit]

**Acceptance Criteria:**
- [Specific, testable criterion 1]
- [Specific, testable criterion 2]
- [Specific, testable criterion 3]

**Priority:** Critical
**Estimated Complexity:** [Low/Medium/High]

---

**Story 2: [Story Title]**
[Repeat structure]

### Future User Stories (Post-MVP)
[Stories that are valuable but not essential for initial launch]
```

---

### 6. Success Metrics

```markdown
## Success Metrics

### Key Performance Indicators (KPIs)

**User Acquisition:**
- Target: [e.g., 1,000 sign-ups in first 3 months]
- Measurement method: [How you'll track this]

**User Engagement:**
- Target: [e.g., 70% weekly active users]
- Measurement method: [How you'll track this]

**User Satisfaction:**
- Target: [e.g., NPS score > 50]
- Measurement method: [How you'll track this]

**Business Metrics:**
- Target: [e.g., Revenue, conversion rate, etc.]
- Measurement method: [How you'll track this]

### Success Criteria
What needs to be true for this product to be considered successful?
1. [Criterion 1]
2. [Criterion 2]
3. [Criterion 3]
```

---

### 7. Scope & Constraints

```markdown
## Scope & Constraints

### In Scope for MVP
- [Feature/capability 1]
- [Feature/capability 2]
- [Feature/capability 3]

### Out of Scope for MVP
- [Feature/capability that will come later]
- [Feature/capability that will come later]

### Technical Constraints
- [Any technical limitations or requirements]
- [Platform requirements]
- [Integration requirements]

### Business Constraints
- [Budget limitations]
- [Timeline requirements]
- [Resource constraints]

### Assumptions
- [Key assumption 1]
- [Key assumption 2]
- [Key assumption 3]
```

---

### 8. Competitive Landscape

```markdown
## Competitive Landscape

### Direct Competitors
**[Competitor 1 Name]**
- Strengths: [What they do well]
- Weaknesses: [Where they fall short]
- Our Advantage: [How we're different/better]

**[Competitor 2 Name]**
- Strengths: [What they do well]
- Weaknesses: [Where they fall short]
- Our Advantage: [How we're different/better]

### Indirect Competitors / Alternatives
- [Alternative solution 1]: [Brief description]
- [Alternative solution 2]: [Brief description]

### Competitive Positioning
[A brief statement of how this product positions itself relative to the competition]
```

---

### 9. Go-to-Market Considerations

```markdown
## Go-to-Market Considerations

### Target Launch Strategy
- **Launch Timeline:** [Target date or timeframe]
- **Launch Scope:** [What features will be available at launch]
- **Beta Testing:** [Plans for user testing before full launch]

### Distribution Channels
- [Channel 1]: [How users will discover/access the product]
- [Channel 2]: [How users will discover/access the product]

### Pricing Strategy (if applicable)
- **Model:** [Freemium, subscription, one-time, etc.]
- **Pricing Tiers:** [If applicable]
- **Rationale:** [Why this pricing approach]

### Marketing Approach
- **Primary messaging:** [Key message to target users]
- **Marketing channels:** [Where to reach target users]
- **Launch activities:** [Initial marketing activities]
```

---

### 10. Risks & Mitigation

```markdown
## Risks & Mitigation

### Technical Risks
- **Risk:** [Description of technical risk]
- **Impact:** [High/Medium/Low]
- **Mitigation:** [How to address this risk]

### Market Risks
- **Risk:** [Description of market risk]
- **Impact:** [High/Medium/Low]
- **Mitigation:** [How to address this risk]

### User Adoption Risks
- **Risk:** [Description of adoption risk]
- **Impact:** [High/Medium/Low]
- **Mitigation:** [How to address this risk]
```

---

### 11. Next Steps

```markdown
## Next Steps

### Immediate Actions
1. [Action item 1] - [Owner] - [Due date]
2. [Action item 2] - [Owner] - [Due date]
3. [Action item 3] - [Owner] - [Due date]

### Validation Activities
- [ ] User interviews with [number] target users
- [ ] Competitive analysis deep-dive
- [ ] Technical feasibility assessment
- [ ] Market research validation

### Documentation Needed
- [ ] Design Document - User flows and UX specifications
- [ ] Architecture Document - Technical architecture and database design
- [ ] PRDs for each core feature
```

---

## Target Audience

Assume the primary reader of this document is a **product team member, stakeholder, or developer** who needs to understand the product vision and strategic direction. The document should be clear enough for non-technical stakeholders but detailed enough to guide technical planning.

## Output

- **Format:** Markdown (`.md`)
- **Location:** `/tasks/`
- **Filename:** `product-draft.md`

## Final Instructions

1. **Do NOT start implementing the product** - This is a planning document only
2. **Ask clarifying questions** to ensure you understand the product vision thoroughly
3. **Be comprehensive but concise** - Include all necessary information without excessive detail
4. **Focus on the "what" and "why"** rather than the "how" - Technical implementation comes later
5. **Validate assumptions** - Clearly state assumptions that need validation
6. **Think strategically** - Consider long-term vision while defining MVP scope

## Usage Example with Claude Code

When starting a new product, use this format:

```
@full-process.md @create-product-draft.md
I want to build a [product description]. Help me create a product draft.
```

The AI will ask clarifying questions before generating a comprehensive product draft that serves as the foundation for all subsequent development work.
