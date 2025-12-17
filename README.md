# Reusable Embedded Feedback Collection System – Next.js FullStack Feedback Widget Project

![Screenshot 2025-06-24 at 00 39 22](https://github.com/user-attachments/assets/26adec5e-1b6a-4fd7-ba36-ef77e8997920)
![Screenshot 2025-06-24 at 00 32 52](https://github.com/user-attachments/assets/fbae9823-52ee-47cf-aa7b-6aa006453a07)
![Screenshot 2025-06-24 at 00 39 05](https://github.com/user-attachments/assets/ad5163c6-0401-4d1b-812c-0cf1c6119a5a)

---

## 📋 Table of Contents

1. [Project Overview](#-project-overview)
2. [Live Demo & Integration](#-live-demo--integration)
3. [Features](#-features)
4. [Technology Stack](#️-technology-stack)
5. [Project Structure](#-project-structure)
6. [Prerequisites](#-prerequisites)
7. [Installation Guide](#-installation-guide)
8. [Environment Variables Setup](#-environment-variables-setup)
9. [Database Setup](#️-database-setup)
10. [Running the Project](#️-running-the-project)
11. [Project Walkthrough](#-project-walkthrough)
12. [Components Documentation](#-components-documentation)
13. [API Routes & Endpoints](#-api-routes--endpoints)
14. [Widget Integration Guide](#-widget-integration-guide)
15. [Reusing Components in Other Projects](#-reusing-components-in-other-projects)
16. [Development & Customization](#️-development--customization)
17. [Building for Production](#-building-for-production)
18. [Deployment](#-deployment)
19. [Keywords & Topics](#️-keywords--topics)
20. [Learn More](#-learn-more)
21. [About](#-about)
22. [Conclusion](#-conclusion)

---

## 🎯 Project Overview

**Embedded Feedback Widget** is a modern, production-ready, full-stack feedback collection system built with Next.js. This project demonstrates best practices for building reusable, embeddable web widgets that can be integrated into any website or web application.

### What This Project Does

- **Collects User Feedback**: Allows users to submit feedback with name, email, message, and a 1-5 star rating
- **Database Storage**: Stores feedback entries in MongoDB using Prisma ORM
- **Widget Embedding**: Can be embedded in any HTML page as a standalone web component
- **API Integration**: Provides RESTful API endpoints for creating and retrieving feedback
- **Modern UI**: Built with Radix UI primitives and Tailwind CSS for a beautiful, accessible interface

### Educational Value

This project is designed as a comprehensive learning resource covering:

- Next.js App Router architecture
- React Server and Client Components
- Web Components and Shadow DOM
- API Route handlers
- Database integration with Prisma
- Modern JavaScript/TypeScript patterns
- Component reusability and modularity
- Build tooling and bundling strategies

---

## 🌐 Live Demo & Integration

- **Live Widget**: [https://embedded-feedback.vercel.app/](https://embedded-feedback.vercel.app/)
- **Integrated Example**: [https://embedded-marketing.netlify.app/](https://embedded-marketing.netlify.app//)
- **Integration Repository**: [Embedded-Widget-Marketing-Interactive-Landing--React-Frontend](https://github.com/arnobt78/Embedded-Widget-Marketing-Interactive-Landing--React-Frontend)

---

## ✨ Features

### Core Functionality

- **📝 Feedback Collection Form**: User-friendly form with name, email, message fields, and interactive star rating
- **⭐ Star Rating System**: Interactive 5-star rating component with visual feedback
- **💾 Database Persistence**: All feedback is stored in MongoDB with timestamps
- **🔌 RESTful API**: Clean API endpoints for creating and retrieving feedback
- **🌍 CORS Support**: Cross-origin resource sharing enabled for widget embedding

### Technical Features

- **🎨 Modern UI Components**: Built with Radix UI for accessibility and Tailwind CSS for styling
- **🔒 Type Safety**: TypeScript support with gradual typing approach
- **📦 Web Component Support**: Can be embedded as a custom HTML element (`<my-widget>`)
- **🚀 Production Ready**: Optimized builds, error handling, and loading states
- **📱 Responsive Design**: Works seamlessly on desktop and mobile devices
- **♿ Accessible**: WCAG compliant components with keyboard navigation support

### Developer Experience

- **🛠️ Hot Module Replacement**: Fast development with Turbopack
- **📝 Comprehensive Comments**: Educational comments throughout codebase
- **🔍 ESLint Configuration**: Code quality and consistency checks
- **📚 Well Documented**: Extensive documentation for learning and reference

---

## 🛠️ Technology Stack

### Core Framework & Libraries

- **Next.js 15.3.8** - React framework with App Router, Server Components, and API Routes
- **React 18.2.0** - UI library with hooks and functional components
- **TypeScript 5** - Type-safe JavaScript with gradual typing
- **Prisma 6.10.0** - Next-generation ORM for database access

### Styling & UI

- **Tailwind CSS 3.4.4** - Utility-first CSS framework
- **Radix UI** - Unstyled, accessible UI primitives
  - `@radix-ui/react-popover` - Popover component
  - `@radix-ui/react-label` - Accessible label component
  - `@radix-ui/react-separator` - Visual separator
  - `@radix-ui/react-slot` - Component composition utility
- **Lucide React** - Beautiful icon library
- **class-variance-authority** - Component variant management
- **clsx** & **tailwind-merge** - Class name utilities

### Database

- **MongoDB** - NoSQL document database (can also use PostgreSQL)
- **Prisma Client** - Type-safe database client

### Build Tools

- **Vite 6.3.5** - Fast build tool for widget bundling
- **PostCSS** - CSS processing
- **ESLint** - Code linting
- **Turbopack** - Next.js's fast bundler (development)

### Deployment

- **Vercel** - Recommended hosting platform (serverless functions, edge network)

---

## 📁 Project Structure

Understanding the project structure is crucial for navigation and development:

```bash
feedback-widget-next/
├── .env                    # Environment variables (not in git)
├── .env.example            # Environment variables template
├── .gitignore              # Git ignore patterns
├── components.json         # shadcn/ui configuration
├── eslint.config.mjs       # ESLint configuration
├── next.config.ts          # Next.js configuration
├── package.json            # Dependencies and scripts
├── package-lock.json       # Dependency lock file
├── postcss.config.js       # PostCSS configuration
├── tailwind.config.js      # Tailwind CSS configuration
├── tsconfig.json           # TypeScript configuration
├── vite.config.widget.js   # Vite config for widget bundling
│
├── prisma/
│   └── schema.prisma       # Database schema definition
│
├── public/
│   ├── favicon.ico         # Site favicon
│   └── widget.umd.js       # Built widget bundle (generated)
│
└── src/
    ├── app/                # Next.js App Router directory
    │   ├── api/            # API routes
    │   │   └── feedback/
    │   │       └── route.js  # Feedback API endpoints (GET, POST, OPTIONS)
    │   ├── favicon.ico     # App favicon
    │   ├── globals.css     # Global styles and CSS variables
    │   ├── layout.tsx      # Root layout component (metadata, fonts)
    │   ├── page.jsx        # Home page component
    │   └── page.module.css # Page-specific styles
    │
    ├── components/         # React components
    │   ├── ui/             # Reusable UI components (shadcn/ui)
    │   │   ├── button.jsx/tsx    # Button component
    │   │   ├── card.tsx          # Card component
    │   │   ├── input.jsx/tsx     # Input field component
    │   │   ├── label.jsx/tsx     # Label component
    │   │   ├── popover.jsx/tsx   # Popover component
    │   │   ├── separator.jsx     # Separator component
    │   │   └── textarea.jsx/tsx  # Textarea component
    │   └── Widget.jsx      # Main feedback widget component
    │
    ├── lib/                # Utility libraries
    │   ├── prisma.js       # Prisma client singleton
    │   ├── utils.js        # Utility functions (JavaScript)
    │   └── utils.ts        # Utility functions (TypeScript)
    │
    └── web-component.jsx   # Web Component wrapper for embedding
```

### Key File Explanations

- **`src/app/layout.tsx`**: Root layout that wraps all pages, contains SEO metadata and global fonts
- **`src/app/page.jsx`**: Home page that displays the widget
- **`src/app/api/feedback/route.js`**: API route handlers for feedback operations
- **`src/components/Widget.jsx`**: Main feedback widget component with form and state management
- **`src/web-component.jsx`**: Web Component wrapper that enables embedding in any HTML page
- **`src/lib/prisma.js`**: Prisma client singleton to prevent multiple database connections
- **`prisma/schema.prisma`**: Database schema definition for the Feedback model
- **`vite.config.widget.js`**: Configuration for building the widget as a UMD bundle

---

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

### Required

- **Node.js** 18.x or higher ([Download](https://nodejs.org/))
- **npm**, **yarn**, **pnpm**, or **bun** package manager
- **Git** for version control
- **MongoDB Atlas account** (free tier available) or local MongoDB instance

### Recommended

- **VS Code** with extensions:
  - ESLint
  - Prettier
  - Prisma
  - Tailwind CSS IntelliSense
- **MongoDB Compass** for database visualization (optional)

### Knowledge Requirements

- Basic understanding of JavaScript/TypeScript
- Familiarity with React concepts (hooks, components, props)
- Basic understanding of REST APIs
- Basic knowledge of Git

---

## 🚀 Installation Guide

Follow these steps to set up the project on your local machine:

### Step 1: Clone the Repository

```bash
# Clone the repository
git clone <your-repo-url>

# Navigate to the project directory
cd feedback-widget-next
```

### Step 2: Install Dependencies

Choose your preferred package manager:

```bash
# Using npm
npm install

# Using yarn
yarn install

# Using pnpm
pnpm install

# Using bun
bun install
```

This will install all required dependencies listed in `package.json`.

### Step 3: Set Up Environment Variables

Create a `.env` file in the root directory:

```bash
# Copy the example file
cp .env.example .env

# Or create manually
touch .env
```

See the [Environment Variables Setup](#-environment-variables-setup) section for detailed instructions on configuring your `.env` file.

### Step 4: Set Up the Database

```bash
# Generate Prisma Client
npx prisma generate

# Push the schema to your database
npx prisma db push
```

See the [Database Setup](#️-database-setup) section for more details.

### Step 5: Run the Development Server

```bash
# Using npm
npm run dev

# Using yarn
yarn dev

# Using pnpm
pnpm dev

# Using bun
bun dev
```

The application will be available at [http://localhost:3000](http://localhost:3000).

---

## 🔐 Environment Variables Setup

Environment variables are crucial for configuring your application. They keep sensitive information like database credentials out of your codebase.

### Creating the `.env` File

Create a `.env` file in the root directory of your project. This file should **never** be committed to Git (it's already in `.gitignore`).

### Required Environment Variables

#### `DATABASE_URL`

This is the connection string for your MongoDB database.

**Format for MongoDB Atlas (Cloud):**

```env
DATABASE_URL="mongodb+srv://<username>:<password>@<cluster-url>/<database-name>?retryWrites=true&w=majority"
```

**Getting Your MongoDB Atlas Connection String:**

1. Sign up at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) (free tier available)
2. Create a new cluster (choose free M0 tier)
3. Create a database user:
   - Go to "Database Access" → "Add New Database User"
   - Choose "Password" authentication
   - Save the username and password
4. Whitelist your IP address:
   - Go to "Network Access" → "Add IP Address"
   - Add `0.0.0.0/0` for development (allows all IPs) or your specific IP
5. Get your connection string:
   - Go to "Database" → "Connect" → "Connect your application"
   - Copy the connection string
   - Replace `<password>` with your database user password
   - Replace `<dbname>` with your database name (e.g., "feedback-widget")

**Example `.env` file:**

```env
DATABASE_URL="mongodb+srv://myuser:mypassword123@cluster0.abc123.mongodb.net/feedback-widget?retryWrites=true&w=majority"
```

**Format for Local MongoDB:**

```env
DATABASE_URL="mongodb://localhost:27017/feedback-widget"
```

### Environment Variables for Production

When deploying to production (e.g., Vercel), add environment variables in your hosting platform's dashboard:

1. **Vercel**: Go to Project Settings → Environment Variables
2. Add `DATABASE_URL` with your production database connection string
3. Redeploy your application

### Security Best Practices

- ✅ Never commit `.env` files to Git
- ✅ Use different databases for development and production
- ✅ Rotate database passwords regularly
- ✅ Use environment-specific `.env` files (`.env.development`, `.env.production`)
- ✅ Restrict MongoDB network access in production

---

## 🗄️ Database Setup

This project uses Prisma ORM to interact with MongoDB. Prisma provides type-safe database access and automatic migrations.

### Understanding the Schema

The database schema is defined in `prisma/schema.prisma`:

```prisma
model Feedback {
  id        String   @id @default(auto()) @map("_id") @db.ObjectId
  name      String?
  email     String?
  message   String
  rating    Int?
  createdAt DateTime @default(now())
}
```

**Field Descriptions:**

- `id`: Unique identifier (MongoDB ObjectId)
- `name`: User's name (optional)
- `email`: User's email (optional)
- `message`: Feedback message (required)
- `rating`: Star rating 1-5 (optional)
- `createdAt`: Timestamp when feedback was created (auto-set)

### Setting Up Prisma

1. **Generate Prisma Client:**

```bash
npx prisma generate
```

This command reads your schema and generates a type-safe Prisma Client that you can use in your application.

1. **Push Schema to Database:**

```bash
npx prisma db push
```

This command creates/updates the database structure based on your schema. It's perfect for development and prototyping.

**For Production:** Use `prisma migrate` for proper migrations:

```bash
npx prisma migrate dev --name init
```

### Verifying Database Connection

You can verify your database connection using Prisma Studio:

```bash
npx prisma studio
```

This opens a visual database browser at [http://localhost:5555](http://localhost:5555) where you can view and manage your data.

### Switching to PostgreSQL (Optional)

If you prefer PostgreSQL over MongoDB:

1. Update `prisma/schema.prisma`:

```prisma
datasource db {
  provider = "postgresql"  // Changed from "mongodb"
  url      = env("DATABASE_URL")
}

model Feedback {
  id        String   @id @default(uuid())  // Changed from ObjectId
  name      String?
  email     String?
  message   String
  rating    Int?
  createdAt DateTime @default(now())

  @@map("feedbacks")  // Optional: custom table name
}
```

1. Update your `.env` file with PostgreSQL connection string:

```env
DATABASE_URL="postgresql://user:password@localhost:5432/feedback-widget"
```

1. Regenerate and push:

```bash
npx prisma generate
npx prisma db push
```

---

## ▶️ Running the Project

### Development Mode

Start the development server with hot module replacement:

```bash
npm run dev
```

**Features:**

- Fast refresh (instant updates on file changes)
- Turbopack bundler for faster builds
- Error overlay in browser
- Accessible at [http://localhost:3000](http://localhost:3000)

### Production Build

Build the project for production:

```bash
npm run build
```

This command:

1. Generates Prisma Client
2. Builds the Next.js application
3. Builds the widget UMD bundle

### Start Production Server

Run the production build locally:

```bash
npm run build
npm start
```

### Building Only the Widget

Build just the widget bundle for embedding:

```bash
npm run build:widget
```

This outputs `widget.umd.js` in the `public/` directory.

---

## 🎓 Project Walkthrough

This section provides a detailed walkthrough of how the application works.

### Application Flow

1. **User Interaction:**

   - User clicks the floating "Feedback" button (bottom-right corner)
   - A popover opens with the feedback form

2. **Form Submission:**

   - User fills in name, email, message, and selects a star rating
   - User clicks "Submit"
   - Form data is sent to `/api/feedback` via POST request

3. **API Processing:**

   - API route handler receives the request
   - Validates the message field (required)
   - Creates a new feedback entry in the database using Prisma
   - Returns success response

4. **UI Update:**
   - Widget shows success message
   - Form is hidden
   - User can close the popover

### Component Hierarchy

```text
RootLayout (layout.tsx)
  └── Home Page (page.jsx)
      └── Widget Component (Widget.jsx)
          ├── Popover (Radix UI)
          │   ├── PopoverTrigger (Button)
          │   └── PopoverContent
          │       ├── Form (conditional: if not submitted)
          │       │   ├── Name Input
          │       │   ├── Email Input
          │       │   ├── Message Textarea
          │       │   ├── Star Rating (5 StarIcon components)
          │       │   └── Submit Button
          │       └── Success Message (conditional: if submitted)
          └── Separator
```

### State Management

The Widget component uses React hooks for state:

```javascript
const [rating, setRating] = useState(3); // Current star rating
const [submitted, setSubmitted] = useState(false); // Form submission status
const [loading, setLoading] = useState(false); // API call loading state
const [error, setError] = useState(""); // Error message
```

### Data Flow

```text
User Input → Widget Component State → API Call → Database
                                    ↓
                              Success/Error → UI Update
```

---

## 📚 Components Documentation

### Main Components

#### Widget Component (`src/components/Widget.jsx`)

The main feedback collection component.

**Props:**

- `apiBase` (string, optional): API endpoint URL (defaults to "/api/feedback")

**Usage:**

```jsx
import Widget from "@/components/Widget";

// With default API endpoint
<Widget />

// With custom API endpoint
<Widget apiBase="https://api.example.com/feedback" />
```

**Features:**

- Floating button that opens a popover
- Form with name, email, message, and rating fields
- Star rating system (1-5 stars)
- Loading states during submission
- Error handling and display
- Success state after submission

**Key Functions:**

```javascript
// Handle star rating selection
const onSelectStar = (index) => {
  setRating(index + 1);
};

// Handle form submission
const submit = async (e) => {
  e.preventDefault();
  // ... submission logic
};
```

#### UI Components (`src/components/ui/`)

Reusable UI components built with Radix UI and Tailwind CSS.

**Button Component:**

```jsx
import { Button } from "@/components/ui/button";

<Button variant="default" size="default">Click me</Button>
<Button variant="outline" size="sm">Outline</Button>
<Button variant="ghost" size="lg">Ghost</Button>
```

**Variants:** `default`, `destructive`, `outline`, `secondary`, `ghost`, `link`  
**Sizes:** `default`, `sm`, `lg`, `icon`

**Input Component:**

```jsx
import { Input } from "@/components/ui/input";

<Input type="email" placeholder="Enter email" id="email" />;
```

**Textarea Component:**

```jsx
import { Textarea } from "@/components/ui/textarea";

<Textarea
  placeholder="Enter message"
  id="feedback"
  className="min-h-[100px]"
/>;
```

**Label Component:**

```jsx
import { Label } from "@/components/ui/label";

<Label htmlFor="email">Email Address</Label>;
```

**Popover Component:**

```jsx
import {
  Popover,
  PopoverTrigger,
  PopoverContent,
} from "@/components/ui/popover";

<Popover>
  <PopoverTrigger asChild>
    <Button>Open</Button>
  </PopoverTrigger>
  <PopoverContent>
    <p>Content goes here</p>
  </PopoverContent>
</Popover>;
```

**Separator Component:**

```jsx
import { Separator } from "@/components/ui/separator";

<Separator className="my-4" />;
```

---

## 🔌 API Routes & Endpoints

The API routes are located in `src/app/api/feedback/route.js`. This file uses Next.js App Router's route handlers.

### Base URL

- Development: `http://localhost:3000/api/feedback`
- Production: `https://embedded-feedback.vercel.app/api/feedback`

### Endpoints

#### POST `/api/feedback`

Creates a new feedback entry.

**Request:**

```javascript
fetch("/api/feedback", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    name: "John Doe",
    email: "john@example.com",
    message: "Great product!",
    rating: 5,
  }),
});
```

**Request Body:**

- `name` (string, optional): User's name
- `email` (string, optional): User's email
- `message` (string, required): Feedback message
- `rating` (number, optional): Star rating (1-5)

**Response (Success - 201):**

```json
{
  "id": "507f1f77bcf86cd799439011",
  "name": "John Doe",
  "email": "john@example.com",
  "message": "Great product!",
  "rating": 5,
  "createdAt": "2025-01-15T10:30:00.000Z"
}
```

**Response (Error - 400):**

```json
{
  "error": "Message is required"
}
```

**Response (Error - 500):**

```json
{
  "error": "Failed to save feedback"
}
```

#### GET `/api/feedback`

Retrieves all feedback entries, ordered by creation date (newest first).

**Request:**

```javascript
fetch("/api/feedback")
  .then((res) => res.json())
  .then((data) => console.log(data));
```

**Response (Success - 200):**

```json
[
  {
    "id": "507f1f77bcf86cd799439011",
    "name": "John Doe",
    "email": "john@example.com",
    "message": "Great product!",
    "rating": 5,
    "createdAt": "2025-01-15T10:30:00.000Z"
  },
  {
    "id": "507f1f77bcf86cd799439012",
    "name": "Jane Smith",
    "email": "jane@example.com",
    "message": "Love it!",
    "rating": 4,
    "createdAt": "2025-01-14T15:20:00.000Z"
  }
]
```

#### OPTIONS `/api/feedback`

Handles CORS preflight requests. This is automatically called by browsers before cross-origin requests.

**Response (204):**

No content, just CORS headers.

### CORS Configuration

The API includes CORS headers to allow cross-origin requests:

```javascript
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: GET, POST, OPTIONS
Access-Control-Allow-Headers: Content-Type
```

This allows the widget to be embedded on different domains.

---

## 🔗 Widget Integration Guide

The widget can be embedded in any HTML page, even outside of React applications, using the Web Component approach.

### Method 1: Web Component (Recommended)

Build the widget bundle and embed it as a custom HTML element.

#### Step 1: Build the Widget

```bash
npm run build:widget
```

This creates `public/widget.umd.js`.

#### Step 2: Embed in HTML

Add the following to any HTML page:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My Website</title>
  </head>
  <body>
    <h1>Welcome to My Website</h1>

    <!-- Load React and ReactDOM (required for the widget) -->
    <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>

    <!-- Load the widget bundle -->
    <script src="https://embedded-feedback.vercel.app/widget.umd.js"></script>

    <!-- Use the widget as a custom HTML element -->
    <my-widget
      api-base="https://embedded-feedback.vercel.app/api/feedback"
    ></my-widget>

    <!-- Your other content -->
  </body>
</html>
```

#### Customization

You can customize the API endpoint:

```html
<my-widget api-base="https://your-api.com/feedback"></my-widget>
```

### Method 2: React Component (Within React Apps)

If you're building a React application, you can import the component directly:

```jsx
import Widget from "@/components/Widget";

function MyPage() {
  return (
    <div>
      <h1>My React App</h1>
      <Widget apiBase="/api/feedback" />
    </div>
  );
}
```

### Method 3: iframe Embedding

You can also embed the entire page in an iframe:

```html
<iframe
  src="https://embedded-feedback.vercel.app/"
  width="400"
  height="600"
  frameborder="0"
></iframe>
```

### Styling Considerations

- The widget uses Shadow DOM, so its styles are isolated
- The widget is positioned fixed in the bottom-right corner
- You can override positioning with CSS:

```css
my-widget {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 9999;
}
```

---

## 🔄 Reusing Components in Other Projects

All components in this project are designed to be reusable. Here's how to use them in other projects:

### Copying UI Components

The UI components in `src/components/ui/` are framework-agnostic React components that can be used anywhere.

#### Step 1: Copy Component Files

Copy the component file(s) you need to your project:

```bash
# Example: Copy Button component
cp src/components/ui/button.jsx your-project/src/components/ui/
cp src/lib/utils.ts your-project/src/lib/  # Required dependency
```

#### Step 1: Install Dependencies

Install required dependencies:

```bash
npm install @radix-ui/react-slot class-variance-authority clsx tailwind-merge
```

#### Step 2: Import and Use

```jsx
import { Button } from "./components/ui/button";

function MyComponent() {
  return <Button variant="default">Click me</Button>;
}
```

### Copying the Widget Component

To reuse the entire widget:

1. Copy `src/components/Widget.jsx` to your project
2. Copy required UI components (`button`, `input`, `textarea`, `label`, `popover`, `separator`)
3. Install all dependencies from `package.json`
4. Adjust import paths as needed

### Creating a Component Library

You can extract these components into a separate npm package:

1. Create a new repository for your component library
1. Copy components and configure build tools
1. Publish to npm:

```bash
npm publish
```

1. Install in other projects:

```bash
npm install your-component-library
```

---

## 🛠️ Development & Customization

### Adding New UI Components

To add new UI components using shadcn/ui:

```bash
npx shadcn-ui@latest add [component-name]
```

Example:

```bash
npx shadcn-ui@latest add dialog
npx shadcn-ui@latest add toast
```

### Customizing Tailwind CSS

Edit `tailwind.config.js` to customize your theme:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        // Add custom colors
        brand: {
          primary: "#your-color",
          secondary: "#your-color",
        },
      },
      borderRadius: {
        // Add custom border radius
        custom: "12px",
      },
    },
  },
};
```

### Modifying the Database Schema

1. Edit `prisma/schema.prisma`:

```prisma
model Feedback {
  id        String   @id @default(auto()) @map("_id") @db.ObjectId
  name      String?
  email     String?
  message   String
  rating    Int?
  category  String?  // New field
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt  // New field
}
```

1. Push changes:

```bash
npx prisma generate
npx prisma db push
```

### Adding Form Validation

You can add client-side validation to the Widget component:

```javascript
const submit = async (e) => {
  e.preventDefault();

  // Validation
  if (!message.trim()) {
    setError("Message is required");
    return;
  }

  if (email && !/\S+@\S+\.\S+/.test(email)) {
    setError("Please enter a valid email");
    return;
  }

  // ... rest of submission logic
};
```

### Adding New API Endpoints

Create a new route file in `src/app/api/`:

```javascript
// src/app/api/feedback/[id]/route.js
import { NextResponse } from "next/server";
import { prisma } from "@/lib/prisma";

export async function GET(request, { params }) {
  const { id } = params;

  try {
    const feedback = await prisma.feedback.findUnique({
      where: { id },
    });

    if (!feedback) {
      return NextResponse.json({ error: "Not found" }, { status: 404 });
    }

    return NextResponse.json(feedback);
  } catch (error) {
    return NextResponse.json({ error: "Failed to fetch" }, { status: 500 });
  }
}
```

---

## 📦 Building for Production

### Next.js Build

Build the entire Next.js application:

```bash
npm run build
```

This creates an optimized production build in the `.next` directory.

### Widget Bundle Build

Build just the widget for embedding:

```bash
npm run build:widget
```

This creates `public/widget.umd.js` using Vite.

### Build Process Explained

The build script (`npm run build`) does three things:

1. **Generates Prisma Client**: Creates type-safe database client
2. **Builds Next.js App**: Compiles and optimizes the Next.js application
3. **Builds Widget Bundle**: Creates UMD bundle for embedding

---

## 🚀 Deployment

### Deploying to Vercel (Recommended)

Vercel is the recommended platform for Next.js applications.

#### Step 1: Push to GitHub

```bash
git add .
git commit -m "Ready for deployment"
git push origin main
```

#### Step 2: Import to Vercel

1. Go to [vercel.com](https://vercel.com)
2. Click "Import Project"
3. Select your GitHub repository
4. Configure environment variables:
   - Add `DATABASE_URL` with your production database connection string
5. Click "Deploy"

#### Step 3: Update Widget Embedding

Update the widget embedding URLs to use your Vercel deployment:

```html
<script src="https://your-app.vercel.app/widget.umd.js"></script>
<my-widget api-base="https://your-app.vercel.app/api/feedback"></my-widget>
```

### Deploying to Other Platforms

#### Netlify

1. Connect your GitHub repository
2. Build command: `npm run build`
3. Publish directory: `.next`
4. Add environment variables in Netlify dashboard

#### Railway

1. Connect your GitHub repository
2. Add environment variables
3. Railway automatically detects Next.js and deploys

#### Docker Deployment

Create a `Dockerfile`:

```dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm ci

COPY . .
RUN npm run build

EXPOSE 3000

CMD ["npm", "start"]
```

Build and run:

```bash
docker build -t feedback-widget .
docker run -p 3000:3000 -e DATABASE_URL="your-db-url" feedback-widget
```

---

## 🏷️ Keywords & Topics

This project covers and demonstrates the following concepts and technologies:

**Frontend:**

- React, React Hooks, Functional Components, Client Components, Server Components
- Next.js, App Router, API Routes, Server-Side Rendering
- Tailwind CSS, Utility-First CSS, Responsive Design
- Web Components, Custom Elements, Shadow DOM
- TypeScript, JavaScript ES6+, Modern JavaScript

**Backend:**

- RESTful API, HTTP Methods, API Routes
- CORS, Cross-Origin Resource Sharing
- Serverless Functions, Edge Functions

**Database:**

- MongoDB, NoSQL, Document Database
- Prisma ORM, Database Migrations, Type-Safe Database Access
- Database Schema Design, Data Modeling

**UI/UX:**

- Radix UI, Accessible Components, ARIA Attributes
- Form Handling, Input Validation, User Feedback
- Loading States, Error Handling, Success States

**Build Tools:**

- Vite, Module Bundling, UMD Format
- Turbopack, Fast Refresh, Hot Module Replacement
- PostCSS, CSS Processing

**Development:**

- Git, Version Control
- ESLint, Code Quality
- Environment Variables, Configuration Management
- Component Reusability, Modular Architecture

**Deployment:**

- Vercel, Serverless Deployment
- Production Builds, Performance Optimization

**Keywords:**
feedback-widget, reactjs, nextjs, feedback-form, mongodb, prisma, tailwindcss, widget-embedding, web-components, reusable-components, fullstack, typescript, api-integration, vercel, modern-web, component-library, teaching-resource, educational-project, real-world-example

---

## 📖 Learn More

### Official Documentation

- [Next.js Documentation](https://nextjs.org/docs) - Comprehensive Next.js guide
- [React Documentation](https://react.dev) - Official React documentation
- [Prisma Documentation](https://www.prisma.io/docs/) - Prisma ORM guide
- [Tailwind CSS Documentation](https://tailwindcss.com/docs) - Tailwind CSS reference
- [Radix UI Documentation](https://www.radix-ui.com/docs) - Radix UI components
- [Vercel Documentation](https://vercel.com/docs) - Vercel deployment guide

### Learning Resources

- [Next.js Learn Course](https://nextjs.org/learn) - Interactive Next.js tutorial
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) - Testing React components
- [Web Components Guide](https://developer.mozilla.org/en-US/docs/Web/Web_Components) - MDN Web Components documentation
- [MongoDB University](https://university.mongodb.com/) - Free MongoDB courses

### Related Projects

- [Next.js Examples](https://github.com/vercel/next.js/tree/canary/examples) - Official Next.js examples
- [shadcn/ui](https://ui.shadcn.com/) - Re-usable components built with Radix UI and Tailwind CSS

---

## 👨‍💻 About

**Author:** Arnob Mahmud  
**Portfolio:** [https://arnob-mahmud.vercel.app/](https://arnob-mahmud.vercel.app/)

This project is designed as a comprehensive teaching and demonstration tool for modern web development workflows. It showcases:

- **Best Practices**: Industry-standard patterns and conventions
- **Modern Stack**: Latest versions of popular frameworks and tools
- **Real-World Patterns**: Practical solutions to common problems
- **Educational Focus**: Extensive comments and documentation for learning

### Use Cases

- **Learning**: Understand modern React and Next.js patterns
- **Reference**: Use as a reference for similar projects
- **Starting Point**: Fork and customize for your own needs
- **Production**: Deploy and use in real applications

### Contributing

Contributions, issues, and feature requests are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## 🎯 Conclusion

This **Embedded Feedback Widget** project demonstrates a complete, production-ready full-stack application built with modern web technologies. It showcases:

✅ **Component Reusability** - Modular, reusable components that can be used across projects  
✅ **Modern Architecture** - Next.js App Router, React Server Components, API Routes  
✅ **Type Safety** - TypeScript and Prisma for type-safe code  
✅ **Best Practices** - Proper error handling, loading states, and user feedback  
✅ **Accessibility** - WCAG-compliant components with keyboard navigation  
✅ **Production Ready** - Optimized builds, CORS support, and deployment configurations  
✅ **Educational Value** - Comprehensive comments and documentation for learning

Whether you're learning modern web development, building a feedback system for your application, or creating reusable components, this project provides a solid foundation to build upon.

The codebase is well-structured, thoroughly commented, and follows industry best practices, making it an excellent resource for developers at all levels.

---

## Happy Coding! 🎉

Feel free to use this project repository and extend this project further!

If you have any questions or want to share your work, reach out via GitHub or my portfolio at [https://arnob-mahmud.vercel.app/](https://arnob-mahmud.vercel.app/).

**Enjoy building and learning!** 🚀

Thank you! 😊

---
