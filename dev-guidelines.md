# Cursor Rules - Development Guidelines

## Core Requirements

### 1. Architecture Documentation
- **Always read `@architecture.md` before writing any code**
- This document contains the complete database schema for the project
- Ensure all code changes align with the documented architecture

### 2. Design Document Reference
- **Must reference `@design-document.md` before adding new components or features**
- Follow the established design patterns and conventions
- Maintain consistency with existing UI/UX decisions

### 3. Documentation Updates
- **Immediately update `@architecture.md` and `@design-document.md`** when:
  - Adding major features
  - Completing milestones
  - Making significant architectural changes
- Keep documentation synchronized with code changes

## Technical Standards

### 4. Component Development
- **All components must be written as React functional components**
- **Use TypeScript for all component files**
- Follow React best practices and hooks patterns
- Ensure proper type definitions for all props and state

### 5. Styling Guidelines
- **Use Tailwind CSS exclusively for styling**
- **Use shadcn/ui components as the default UI library unless user specifies otherwise**
- **Do not add custom CSS files**
- Utilize Tailwind's utility classes for all styling needs
- Maintain consistent design system through Tailwind configuration
- Prefer shadcn/ui components over custom implementations for common UI elements

### 6. API Integration
- **Use axios library for all API calls**
- **Store API keys and authentication information in environment variables**
- Implement proper error handling for API requests
- Create reusable API service functions

### 7. Testing Requirements
- **Every feature must include unit tests**
- **Write tests using Jest framework**
- **Provide test files alongside the code**
- Aim for comprehensive test coverage
- Include both positive and negative test cases

### 8. Code Organization
- **Avoid code duplication**
- **Extract common logic into separate functions in `/utils` folder**
- Create reusable utility functions for shared functionality
- Maintain clean and modular code structure
- Follow consistent naming conventions

## File Structure Guidelines
```
/src
  /components    # React components
  /utils         # Shared utility functions
  /services      # API service functions
  /types         # TypeScript type definitions
  /tests         # Test files
```

## Workflow Checklist
Before starting any development task:
- [ ] Read `@architecture.md`
- [ ] Check `@design-document.md`
- [ ] Plan the implementation approach
- [ ] Identify reusable utilities needed
- [ ] Write the feature with tests
- [ ] Update architecture and design documents if needed
