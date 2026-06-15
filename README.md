# CodeForge - AI-Powered Code Playground & IDE

A full-stack web application that provides an AI-assisted code development environment with real-time code execution, GitHub integration, and intelligent code suggestions.

## 🚀 Live Demo

Visit the live application: [CodeForge](#) *(Add your deployment link here)*

## 📸 Screenshots

### Main Playground Interface
![Playground](./docs/screenshots/playground.png)

### Code Editor with AI Suggestions
![AI Suggestions](./docs/screenshots/ai-suggestions.png)

### GitHub Integration & Push
![GitHub Push](./docs/screenshots/github-push.png)

### Dashboard & Project Management
![Dashboard](./docs/screenshots/dashboard.png)

## ✨ Key Features

- **🎯 AI-Powered Code Assistant** - Real-time code suggestions and ghost text completions
- **💻 Live Code Execution** - WebContainer-based sandboxed code execution (Node.js environment)
- **🔗 GitHub Integration** - Push projects directly to your GitHub repositories
- **📁 File Explorer** - Manage project files with an intuitive explorer interface
- **🎨 Multi-Template Support** - Pre-built starters for React, Next.js, Angular, Vue, Astro, and more
- **⚡ Real-time Terminal** - Execute commands and view output instantly
- **🔐 Authentication** - Secure OAuth-based login (GitHub & Google)
- **📊 Project Dashboard** - Manage all your projects in one place
- **💾 Cloud Persistence** - Save projects and sync across devices

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 14+ with TypeScript
- **UI Library**: React 18+
- **Styling**: Tailwind CSS with shadcn/ui components
- **State Management**: React Query (TanStack Query)
- **Code Editor**: Monaco Editor
- **Real-time Execution**: WebContainers

### Backend
- **Runtime**: Node.js with Next.js API Routes
- **Database**: PostgreSQL with Prisma ORM
- **Authentication**: NextAuth.js v5
- **AI Integration**: Claude AI API
- **External APIs**: GitHub REST API

### DevOps & Tools
- **Package Manager**: npm
- **Version Control**: Git
- **Code Quality**: ESLint, Prettier
- **Testing**: Jest, Vitest

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js**: v18.0.0 or higher
- **npm**: v9.0.0 or higher
- **Git**: For version control
- **PostgreSQL**: Local or cloud instance

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Nitin2004577/Nitin-Kumar-Shah-CodeForge.git
cd Nitin-Kumar-Shah-CodeForge
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Configuration

Create a `.env.local` file in the root directory with the following variables:

```env
# Database
DATABASE_URL="postgresql://user:password@localhost:5432/codeforge"

# NextAuth Configuration
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-secret-key-here"

# GitHub OAuth
GITHUB_ID="your-github-oauth-app-id"
GITHUB_SECRET="your-github-oauth-app-secret"

# Google OAuth (Optional)
GOOGLE_ID="your-google-oauth-app-id"
GOOGLE_SECRET="your-google-oauth-app-secret"

# Claude AI API
ANTHROPIC_API_KEY="your-claude-api-key"

# GitHub Token (for push operations)
GITHUB_TOKEN="your-github-personal-access-token"
```

### 4. Database Setup

Initialize Prisma and create the database schema:

```bash
npx prisma migrate dev --name init
npx prisma generate
```

### 5. Start Development Server

```bash
npm run dev
```

The application will be available at `http://localhost:3000`

## 📚 Project Structure

```
CodeForge/
├── src/
│   ├── app/                    # Next.js app directory
│   │   ├── (auth)/            # Authentication pages
│   │   ├── (root)/            # Main application routes
│   │   ├── api/               # API routes
│   │   │   ├── auth/          # Authentication endpoints
│   │   │   ├── chat/          # AI chat endpoint
│   │   │   └── github/        # GitHub integration endpoints
│   │   └── layout.tsx         # Root layout
│   ├── components/            # Reusable UI components
│   ├── lib/                   # Utility functions and helpers
│   │   ├── db.ts             # Database client
│   │   └── query-client.ts   # React Query configuration
│   └── proxy.ts              # API proxy configuration
├── features/
│   ├── playground/           # Code playground feature
│   │   ├── components/       # Playground UI components
│   │   ├── hooks/            # Custom React hooks
│   │   └── actions/          # Server actions
│   ├── dashboard/            # Dashboard feature
│   ├── webcontainers/        # WebContainer integration
│   ├── ai-chat/             # AI chat feature
│   ├── auth/                # Authentication features
│   └── settings/            # User settings
├── CodeForge-starters/       # Project starter templates
│   ├── angular/
│   ├── astro-shadcn/
│   ├── bolt-expo/
│   ├── bolt-qwik/
│   ├── bolt-vite-react-ts/
│   └── ... (more templates)
├── prisma/
│   └── schema.prisma         # Database schema
├── __tests__/                # Unit and integration tests
├── auth.ts                   # NextAuth configuration
├── auth.config.ts            # Auth provider setup
└── package.json
```

## 🔧 Available Scripts

```bash
# Development
npm run dev              # Start development server

# Production
npm run build            # Build for production
npm run start            # Start production server

# Code Quality
npm run lint             # Run ESLint
npm run format           # Format code with Prettier

# Database
npx prisma migrate dev   # Create and apply migrations
npx prisma studio       # Open Prisma Studio UI

# Testing
npm run test             # Run tests
npm run test:watch       # Run tests in watch mode
```

## 🔐 Authentication Setup

### GitHub OAuth Setup

1. Go to GitHub Settings → Developer settings → OAuth Apps
2. Create a new OAuth application
3. Set Authorization callback URL to `http://localhost:3000/api/auth/callback/github`
4. Copy Client ID and Client Secret to `.env.local`

### Suggested LinkedIn Headline

```
Full Stack Developer | Next.js | React | TypeScript | Node.js | PostgreSQL | AI Integration
```

This headline highlights your full-stack capabilities and core technologies used in CodeForge.

### Google OAuth Setup (Optional)

1. Go to Google Cloud Console
2. Create a new project and enable Google+ API
3. Create OAuth 2.0 credentials (Web application)
4. Add `http://localhost:3000/api/auth/callback/google` to authorized redirect URIs
5. Copy Client ID and Client Secret to `.env.local`

## 🤖 AI Integration

CodeForge uses the Claude AI API for intelligent code suggestions. To enable:

1. Get your API key from [Anthropic Console](https://console.anthropic.com)
2. Add `ANTHROPIC_API_KEY` to `.env.local`

## 🐙 GitHub Integration

### Push Projects to GitHub

1. Authenticate with GitHub via the login page
2. In the playground, click the "Push to GitHub" button
3. Follow the prompts to create a new repository or push to an existing one

**Required Permissions**:
- `repo` - Full control of private repositories
- `workflow` - Update GitHub Actions workflows

## 📦 Deployment

### Deploy to Vercel (Recommended)

```bash
npm install -g vercel
vercel
```

Follow the prompts and configure environment variables in Vercel dashboard.

### Deploy to Other Platforms

This is a Next.js application that can be deployed to any Node.js hosting provider (Netlify, Railway, Heroku, etc.).

## 🧪 Testing

```bash
# Run all tests
npm run test

# Run specific test file
npm run test -- specific-test.test.ts

# Run tests in watch mode
npm run test:watch
```

## 📖 API Documentation

### Chat Endpoint

```
POST /api/chat
Content-Type: application/json

{
  "prompt": "Your code prompt here",
  "context": "Current code context"
}

Response:
{
  "suggestion": "AI-generated code suggestion"
}
```

### GitHub Push Endpoint

```
POST /api/github/push
Content-Type: application/json

{
  "files": [...],
  "repositoryName": "my-project",
  "description": "Project description"
}
```

### Repository Fetch Endpoint

```
GET /api/github/repos
Response:
{
  "repositories": [...]
}
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org/) - React framework
- [Prisma](https://www.prisma.io/) - Database ORM
- [WebContainers](https://webcontainers.io/) - Sandboxed code execution
- [Anthropic Claude](https://www.anthropic.com/) - AI code suggestions
- [shadcn/ui](https://ui.shadcn.com/) - Beautiful UI components
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS

## 📧 Contact & Support

- **GitHub**: [@Nitin2004577](https://github.com/Nitin2004577)
- **Email**: shahnitin500@gmail.com
- **LinkedIn**: [Nitin Kumar Shah](https://www.linkedin.com/in/nitin-kumar-shah/)

## 🎯 Portfolio Highlights

### For Full Stack Developer Interviews:

- **Full-Stack Architecture**: Demonstrates proficiency in both frontend (React, Next.js, TypeScript) and backend (Node.js, PostgreSQL, Prisma)
- **Real-Time Features**: WebContainer integration for live code execution
- **Third-Party Integrations**: GitHub API, Google Cloud Auth, Anthropic AI
- **Database Design**: Complex schema with user projects, files, and execution logs
- **Authentication**: Secure OAuth implementation with NextAuth.js
- **Performance**: Optimized with React Query, server components, and code splitting
- **Scalability**: Ready for production deployment

---

**Made with ❤️ for Full Stack Development**
