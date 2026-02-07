# YarnBot – Cloud-Native Aussie AI Assistant

A modern, full-stack conversational AI platform featuring the Qwen 2.5 LLM with a distinctive Australian accent, advanced document analysis, and a sleek futuristic interface.

<img width="1912" height="1193" alt="image" src="https://github.com/user-attachments/assets/27fd0e08-f9ef-4bbb-b899-8435e0997c21" />


## Overview

YarnBot combines cutting-edge AI technology with cloud-native architecture to deliver an engaging conversational experience. Built with Next.js and FastAPI, it leverages the Qwen 2.5 Large Language Model to provide intelligent responses in an authentic Aussie accent. The platform supports document analysis (PDF and Word files) with instant summarization and key point extraction, all wrapped in a responsive, real-time markdown-enabled UI.

## Architecture

Here’s an overview of YarnBot’s architecture:
graph TB
    subgraph "Client Layer"
        A[Web Browser] --> B[Next.js Frontend<br/>TypeScript]
        B --> C[Shadcn & Aceternity UI]
    end

    subgraph "CDN & Security"
        D[Cloudflare CDN]
    end

    subgraph "Authentication"
        E[Firebase Auth]
    end

    subgraph "Backend Services - AWS EC2"
        F[FastAPI Backend<br/>Python]
        G[Document Processor<br/>PDF/Word Parser]
        H[MLflow<br/>Model Tracking]
    end

    subgraph "AI Services"
        I[Hugging Face API<br/>Qwen 2.5 LLM]
    end

    subgraph "Data Layer"
        J[(MongoDB Atlas<br/>Session & User Data)]
    end

    subgraph "Infrastructure"
        K[Docker Containers]
    end

    A -->|HTTPS| D
    D -->|Secured Traffic| B
    B -->|Auth Request| E
    B -->|API Calls| F
    E -->|User Verification| B
    
    F -->|Document Upload| G
    F -->|AI Inference| I
    F -->|Model Metrics| H
    F -->|CRUD Operations| J
    
    I -->|Aussie AI Response| F
    G -->|Extracted Content| F
    J -->|Session Data| F
    
    F -->|Response| B
    B -->|Rendered UI| A
    
    K -.->|Containerized| F
    K -.->|Deployed on| AWS[AWS EC2]
    
    style A fill:#4A90E2
    style B fill:#50C878
    style F fill:#FF6B6B
    style I fill:#FFD93D
    style J fill:#6BCF7F
    style D fill:#FF8C42
    style E fill:#F97316
    style K fill:#8B5CF6

## Demo

Try YarnBot live at: [https://yarn-bot.vercel.app/](https://yarn-bot.vercel.app/)

## Features

- **Aussie AI Chat** – Conversational AI powered by Qwen 2.5 with a unique Australian accent
- **Document Analysis** – Upload PDF and Word files for instant context-aware summarization and key insights
- **Real-time Markdown Rendering** – Futuristic, responsive UI with live message formatting
- **Secure Multi-user Sessions** – Firebase Authentication with MongoDB session management

## Tech Stack

- **Frontend:** Next.js (TypeScript), Shadcn UI, Aceternity UI
- **Backend:** FastAPI (Python), Hugging Face API (Qwen 2.5), MLflow
- **Database:** MongoDB Atlas
- **Infrastructure:** Docker, AWS EC2, Cloudflare (CDN & Security)

## Installation
```bash
# Clone the repository
git clone https://github.com/AMG786/YarnBot.git

# Navigate to the project directory
cd YarnBot

# Install dependencies
npm install

# Set up environment variables
# Create a .env.local file with your API keys and configuration

# Run the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to see the application.

## Usage

1. Sign in using Firebase Authentication
2. Start a conversation with YarnBot in the chat interface
3. Upload PDF or Word documents using the upload feature for instant analysis
4. View summarized insights and key points extracted from your documents
5. Enjoy AI-powered responses delivered in an engaging Aussie accent

## Contact

**Author:** Abdul Mueez
**Email:** abdulmueez917@gmail.com
**GitHub:** [https://github.com/AMG786/YarnBot](https://github.com/AMG786/YarnBot)
