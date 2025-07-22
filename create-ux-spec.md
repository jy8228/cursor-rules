# Rule: Generating a UX specifications Document

## Goal
These guidelines help AI assistants create clear, actionable UX/UI specifications that designers and developers can implement effectively. Focus on user experience, visual design, and interaction patterns.

## Process

1.  **Receive Initial Prompt:** The user provides requirments or provides relevant documents to design UX of the product.
2.  **Ask Clarifying Questions:** Before make UX designs, the AI should ask clarifying questions to gather sufficient detail. AI assistant can skip this step if all the details are already clarified by user's prompt or provided documents. Make sure to provide options in letter/number lists so I can respond easily with my selections.
3.  **Generate UX specfications:** Based on the initial prompt and the user's answers to the clarifying questions, generate a UX specifications using the structure outlined below.
4.  **Save UX specifications:** Save the generated document as `ux-spec-[feature-name].md` inside the `/tasks` directory.

## Clarifying Questions (Examples)

The AI should adapt its questions based on the prompt, but here are some common areas to explore:

*   **Target User:** "Who is the primary user of this feature?"
*   **Core Functionality:** "Can you describe the key actions a user should be able to perform with this feature?"
*   **User Stories:** "Could you provide a few user stories? (e.g., As a [type of user], I want to [perform an action] so that [benefit].)"
*   **Design/UI:** "Are there any existing design mockups or UI guidelines to follow?" or "Can you describe the desired look and feel?"

## UX Specification Structure

The generated UX Spec. should include the following sections:

---

1. User Flow
**Define each user flow with:**
- Flow name and primary user goal
- Starting point (page/action that triggers the flow)
- Step-by-step user actions and system responses
- Decision points and branching paths
- Success and failure outcomes

**Example Format:**
```
Flow: User Registration
Goal: New user creates an account
Start: Landing page "Sign Up" button

Steps:
1. User clicks "Sign Up" → Navigate to registration page
2. User fills email field → Real-time validation feedback
3. User fills password field → Password strength indicator appears
4. User clicks "Create Account" → Loading state, then success message
5. System sends verification email → User directed to check email page

Branch: If email already exists → Show error message, suggest login
Success: User redirected to onboarding flow
```


---

2. Information Architecture

2.1 Site Structure
Document the complete navigation hierarchy showing how users move through the product.

**Page Hierarchy:**
```
Homepage
├── About
├── Products
│   ├── Category A
│   ├── Category B
│   └── Product Detail Pages
├── User Account
│   ├── Profile
│   ├── Orders
│   └── Settings
└── Support
    ├── Help Center
    └── Contact
```

2.2 Navigation Systems
**Primary Navigation**
- Main menu items and their order
- How navigation changes for different user types
- Active/current page indicators

**Secondary Navigation**
- Breadcrumbs placement and behavior
- Sub-navigation within sections
- Contextual navigation elements

**Mobile Navigation**
- How primary navigation adapts on mobile
- Hamburger menu structure
- Mobile-specific navigation patterns

2.3 Content Organization
**Page Types and Templates**
- Landing pages structure
- Content pages layout
- List/grid view patterns
- Detail page organization

**Content Relationships**
- How different content connects
- Cross-references and related items
- Search and filtering logic

---

3. Detailed UX Components

- Define UX components for each pages
- Use Shadcn components
- For each page, specify components using this structure:

**Page: [Page Name]**
**Purpose**: Brief description of page goal

**Layout Structure:**
- Header content and behavior
- Main content areas
- Sidebar elements (if any)
- Footer content

**Components Used:**

---

4. Responsive Design Specifications

4.1 Breakpoints
Define how components adapt across screen sizes:
- Desktop (1024px+)
- Tablet (768px - 1023px) 
- Mobile (below 768px)

4.2 Mobile Adaptations
**Navigation Changes**
- Primary navigation becomes hamburger menu
- Tab navigation becomes scrollable
- Complex tables become card-based layouts

**Content Adaptations**
- Multi-column layouts become single column
- Modal dialogs become full-screen on mobile
- Form layouts optimize for touch input

**Interaction Changes**
- Hover states become tap states
- Touch targets meet minimum size requirements
- Gestures for mobile-specific interactions


## Target Audience

Assume the primary reader of the document is a **junior developer/designer**. Therefore, requirements should be explicit, unambiguous, and avoid jargon where possible. Provide enough detail for them to understand the feature's purpose and core logic.

## Output

*   **Format:** Markdown (`.md`)
*   **Location:** `/tasks/`
*   **Filename:** `ux-spec-[feature-name].md`

## Final instructions

1. Do NOT start implementing the UX specfications
2. Make sure to ask the user clarifying questions
3. Take the user's answers to the clarifying questions and improve the UX specfications
