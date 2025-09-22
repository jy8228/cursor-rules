# Rule: Generating a Archtecture Document

## Goal
These guidelines help AI assistants create clear architecture of the system that developers can implement product system based on the architecture.

## Process

1.  **Receive Initial Prompt:** The user provides requirments or provides relevant documents to design architecture of the product.
2.  **Ask Clarifying Questions:** Before design architecture, the AI should ask clarifying questions to gather sufficient detail. AI assistant can skip this step if all the details are already clarified by user's prompt or provided documents. Make sure to provide options in letter/number lists so I can respond easily with my selections.
3.  **Generate system architecture:** Based on the initial prompt and the user's answers to the clarifying questions, generate a architecture document using the structure outlined below.
4.  **Save Architecture Document:** Save the generated document as `architecture.md` inside the `/tasks` directory.

## Clarifying Questions (Examples)

To be defined..

## Architecture Structure

### Overview
The `architecture.md` file serves as the technical blueprint for the entire project. It should provide AI assistants and developers with all the information needed to understand the system structure, data flow, and technical implementation details.

---

### 1. Project Overview

#### 1.1 System Description
```markdown
# Project Architecture

## System Overview
Brief description of what the system does, its primary purpose, and target users.

### Key Features
- Feature 1: Description
- Feature 2: Description
- Feature 3: Description

### Technology Stack
- **Frontend**: React, TypeScript, Tailwind CSS, shadcn/ui
- **Backend**: [Backend technology if applicable]
- **Database**: [Database technology]
- **Authentication**: [Auth method]
- **Deployment**: [Deployment platform]
```

---

### 2. Database Schema

#### 2.1 Entity Relationship Documentation
```markdown
## Database Schema

### Entities Overview
List of all main entities in the system with their relationships.

### Entity Definitions

#### User Entity
```sql
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  email VARCHAR(255) UNIQUE NOT NULL,
  name VARCHAR(100) NOT NULL,
  avatar_url TEXT,
  role ENUM('admin', 'user', 'guest') DEFAULT 'user',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);
```

**Fields Description:**
- `id`: Unique identifier for the user
- `email`: User's email address (used for authentication)
- `name`: Display name for the user
- `avatar_url`: Optional profile picture URL
- `role`: User permission level
- `created_at`: Record creation timestamp
- `updated_at`: Last modification timestamp

**Relationships:**
- Has many: Posts, Comments
- Belongs to: Organization (optional)

##### [Other Entities...]
Follow the same pattern for all entities.
```

#### 2.2 Relationship Mapping
```markdown
### Entity Relationships

```
Users ||--o{ Posts : creates
Users ||--o{ Comments : writes
Posts ||--o{ Comments : has
Organizations ||--o{ Users : contains
```

### Indexes and Constraints
- Primary indexes on all `id` fields
- Unique constraint on `users.email`
- Foreign key constraints on all relationship fields
- Performance indexes on frequently queried fields
```

---

### 3. API Architecture

#### 3.1 API Design Patterns
```markdown
## API Architecture

### REST API Endpoints

#### Authentication Endpoints
- `POST /auth/login` - User login
- `POST /auth/register` - User registration
- `POST /auth/logout` - User logout
- `POST /auth/refresh` - Token refresh

#### User Management
- `GET /users` - List users (admin only)
- `GET /users/:id` - Get user details
- `PUT /users/:id` - Update user
- `DELETE /users/:id` - Delete user

#### [Other endpoint groups...]

### Request/Response Formats

#### Standard Response Structure
```json
{
  "success": boolean,
  "data": object | array | null,
  "error": {
    "code": string,
    "message": string
  } | null,
  "pagination": {
    "page": number,
    "limit": number,
    "total": number
  } | null
}
```

### Error Handling
- 400: Bad Request - Invalid input data
- 401: Unauthorized - Authentication required
- 403: Forbidden - Insufficient permissions
- 404: Not Found - Resource doesn't exist
- 500: Internal Server Error - Server-side issues
```

---

### 4. Frontend Architecture

#### 4.1 Component Architecture
```markdown
## Frontend Architecture

### Component Hierarchy
```
App
├── Layout
│   ├── Header
│   │   ├── Navigation
│   │   └── UserMenu
│   ├── Sidebar (conditional)
│   └── Footer
├── Router
│   ├── PublicRoutes
│   │   ├── HomePage
│   │   ├── LoginPage
│   │   └── RegisterPage
│   └── PrivateRoutes
│       ├── Dashboard
│       ├── ProfilePage
│       └── SettingsPage
└── Providers
    ├── AuthProvider
    ├── ThemeProvider
    └── QueryProvider
```

### State Management
- **Authentication State**: Global context for user auth status
- **Theme State**: Light/dark mode preference
- **API State**: React Query for server state management
- **Local State**: Component-level useState for UI state

### Routing Structure
```typescript
interface Route {
  path: string;
  component: React.Component;
  protected: boolean;
  roles?: string[];
}
```
```

#### 4.2 Data Flow Architecture
```markdown
### Data Flow Patterns

#### Authentication Flow
1. User submits login form
2. API call to `/auth/login`
3. Store JWT token in secure storage
4. Update global auth context
5. Redirect to dashboard

#### Data Fetching Pattern
1. Component mounts
2. React Query hook triggers API call
3. Loading state displayed
4. Data received and cached
5. Component re-renders with data
6. Error handling if request fails
```

---

### 5. File Structure

#### 5.1 Project Organization
```markdown
## File Structure

```
/src
├── /components
│   ├── /ui                 # shadcn/ui components
│   ├── /forms             # Form components
│   ├── /layout            # Layout components
│   └── /features          # Feature-specific components
├── /pages                 # Page components
├── /hooks                 # Custom React hooks
├── /services              # API service functions
├── /utils                 # Utility functions
├── /types                 # TypeScript type definitions
├── /stores                # State management
├── /tests                 # Test files
└── /assets               # Static assets
```

### Component Organization
- **UI Components**: Reusable, presentational components
- **Feature Components**: Business logic components
- **Layout Components**: Page structure components
- **Form Components**: Form-specific components with validation

### Naming Conventions
- Components: PascalCase (e.g., `UserProfile.tsx`)
- Hooks: camelCase with 'use' prefix (e.g., `useAuth.ts`)
- Utilities: camelCase (e.g., `formatDate.ts`)
- Types: PascalCase (e.g., `User.ts`)
```

---

### 6. Authentication & Authorization

#### 6.1 Auth Implementation
```markdown
## Authentication Architecture

### Authentication Method
- JWT-based authentication
- Tokens stored in secure HTTP-only cookies
- Refresh token rotation for security

### Authorization Levels
- **Guest**: Public pages only
- **User**: Authenticated user features
- **Admin**: User management and system settings

### Protected Route Implementation
```typescript
interface ProtectedRouteProps {
  children: React.ReactNode;
  requiredRole?: 'user' | 'admin';
}
```

### Session Management
- Automatic token refresh before expiration
- Logout on token invalidity
- Remember me functionality (optional)
```

---

### 7. Performance & Security

#### 7.1 Performance Considerations
```markdown
## Performance Architecture

### Optimization Strategies
- **Code Splitting**: Route-based lazy loading
- **Image Optimization**: WebP format with fallbacks
- **Caching**: React Query for API response caching
- **Bundle Optimization**: Tree shaking and minification

### Loading Strategies
- Skeleton screens for initial loads
- Progressive loading for large datasets
- Infinite scrolling for long lists

### Performance Metrics
- First Contentful Paint (FCP) < 1.5s
- Largest Contentful Paint (LCP) < 2.5s
- Time to Interactive (TTI) < 3s
```

#### 7.2 Security Implementation
```markdown
## Security Architecture

### Data Protection
- Input validation on all forms
- SQL injection prevention
- XSS protection through React's built-in escaping
- CSRF protection with tokens

### Authentication Security
- Password hashing with bcrypt
- Rate limiting on auth endpoints
- Secure cookie settings
- Token expiration and rotation

### API Security
- Request validation with TypeScript
- Authorization checks on all protected endpoints
- Environment variable protection
- HTTPS enforcement
```

---

### 8. Development Workflow

#### 8.1 Environment Configuration
```markdown
## Development Environment

### Environment Variables
```bash
# Database
DATABASE_URL=postgresql://...
DATABASE_POOL_SIZE=10

# Authentication
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=7d
REFRESH_TOKEN_EXPIRES_IN=30d

# External Services
API_BASE_URL=https://api.example.com
STORAGE_BUCKET=your-bucket-name
```

### Development Commands
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run test` - Run test suite
- `npm run lint` - Code linting
- `npm run type-check` - TypeScript validation
```

#### 8.2 Deployment Architecture
```markdown
## Deployment Strategy

### Production Environment
- **Hosting**: [Platform name]
- **Database**: [Database service]
- **CDN**: [CDN service for static assets]
- **Monitoring**: [Error tracking service]

### CI/CD Pipeline
1. Code push to main branch
2. Automated tests run
3. Build process executes
4. Deployment to staging
5. Manual approval for production
6. Production deployment

### Environment Promotion
- **Development**: Local development
- **Staging**: Pre-production testing
- **Production**: Live application
```

---

## Target Audience

Assume the primary reader of the document is a **junior developer/designer**. Therefore, requirements should be explicit, unambiguous, and avoid jargon where possible. Provide enough detail for them to understand the feature's purpose and core logic.

## Output

*   **Format:** Markdown (`.md`)
*   **Location:** `/tasks/`
*   **Filename:** `architecture.md`

## Final instructions

1. Do NOT start implementing the architecture
2. Make sure to ask the user clarifying questions
3. Take the user's answers to the clarifying questions and improve the architecture
