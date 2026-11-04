# synapse

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

# Synapse ⚡

**Synapse** is a modern Flutter application built for cross-platform seamless interaction, powered by Supabase for backend services and configured for Web/Cross-platform deployment.

Synapse is a modern cross-platform application built with Flutter and powered by a robust Supabase backend. It provides a seamless, high-performance experience across mobile (iOS & Android) and web platforms.

🚀 Key Features
Cross-Platform Compatibility: Runs smoothly on iOS, Android, and Web platforms.

Backend Services: Integrated with Supabase for real-time database management, user authentication, and file storage.

Clean Architecture: Built using structured state management and clear separation of concerns for easy maintenance and scaling.

Deployment Ready: Pre-configured for seamless web hosting and cross-platform deployment via Vercel.

🛠️ Tech Stack
Frontend: Flutter / Dart

Backend & Database: Supabase

Hosting & CI/CD: Vercel
---

## 🚀 Features

- **Cross-Platform Support**: Mobile (iOS & Android) and Web compatibility.
- **Backend Integration**: Powered by Supabase for authentication, real-time database, and storage.
- **Clean Architecture**: Structured with maintainable state management and clear separation of concerns.

---

## 🛠️ Tech Stack

- **Frontend**: [Flutter](https://flutter.dev/) (Dart)
- **Backend & Database**: [Supabase](https://supabase.com/)
- **Hosting/Deployment**: [Vercel](https://vercel.com/)

---

## 📋 Prerequisites

Before running this project, ensure you have the following installed:

- [Flutter SDK](https://docs.flutter.dev/get-started/install) (`>=3.0.0`)
- [Dart SDK](https://dart.dev/get-dart)
- [Git](https://git-scm.com/)

---

## ⚙️ Setup & Installation

### 1. Clone the Repository
```bash
git clone [https://github.com/Venkatesh-Web-dev01/synapse.git](https://github.com/Venkatesh-Web-dev01/synapse.git)
cd synapse

Project Structure
Plaintext
lib/
├── core/            # App constants, utilities, and theme data
├── features/        # Feature modules (UI, Logic, Data layers)
│   ├── ai_chat/     # LLM integration & streaming logic
│   ├── auth/        # Supabase authentication flows
│   └── dashboard/   # Main application view
├── services/        # Supabase client, local cache, and network APIs
└── main.dart        # Entry point of the application

graph TD
    A[Flutter App UI] -->|User Input / Voice / Text| B[State Management / Bloc or Riverpod]
    B -->|Local Processing / Offline Cache| C[(SQLite / Hive Cache)]
    B -->|API Request / Streaming| D[AI Gateway / Orchestrator]
    
    subgraph AI Layer
        D -->|LLM Calls| E[LLM Provider / OpenAI / Anthropic / Local Model]
        D -->|Embedding Generation| F[Vector Embeddings Model]
    end

    subgraph Supabase Backend
        F -->|Store / Query Vectors| G[(pgvector Database)]
        D -->|RAG Retrieval| G
        B -->|Auth & Realtime Sync| H[Supabase Auth & Database]
        B -->|Storage| I[Supabase Storage]
    end

Key Concepts
Client Layer: Manages UI state, captures user inputs (text/voice), and handles immediate updates via local cache.

AI Layer: Routes prompt requests, generates vector embeddings, and streams context-aware LLM responses.

Database & Storage (Supabase): Handles relational user data, authenticates requests, and provides vector similarity search (pgvector) for contextual knowledge extraction.

📋 Prerequisites
Before running this project, ensure you have the following installed:

Flutter SDK: >=3.0.0

Dart SDK

Git

A active Supabase project instance

⚙️ Setup & Installation
1. Clone the Repository
Bash
git clone https://github.com/Venkatesh-Web-dev01/synapse.git
cd synapse
2. Configure Environment Variables
Copy the sample environment file and configure your API keys:

Bash
cp .env.example .env
Add your Supabase and AI provider configurations in .env:

Code snippet
SUPABASE_URL=https://your-supabase-url.supabase.co
SUPABASE_ANON_KEY=your-anon-key
AI_API_KEY=your-ai-api-key
3. Install Dependencies
Bash
flutter pub get
4. Run the Application
Mobile (iOS/Android):

Bash
flutter run
Web:

Bash
flutter run -d chrome
