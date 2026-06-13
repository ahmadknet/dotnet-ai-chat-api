# dotnet-ai-chat-api Project Plan

## Goal

Build a real-world AI application using:

```text
React (Frontend)
        ↓
ASP.NET Core Web API
        ↓
Azure OpenAI
        ↓
Response
```

This will become your **flagship GitHub project** and can be showcased on your resume.

---

# Phase 1: Foundation (Days 1–3)

## Day 1

### Create Solution

```bash
mkdir dotnet-ai-chat-api

cd dotnet-ai-chat-api

dotnet new sln
```

---

### Create API

```bash
dotnet new webapi -n AIChatApi
```

---

### Add to Solution

```bash
dotnet sln add AIChatApi
```

---

### Folder Structure

```text
AIChatApi
│
├── Controllers
├── Services
├── Models
├── Interfaces
├── DTOs
├── Configuration
└── Program.cs
```

---

## Day 2

### Create Chat Endpoint

```text
GET
/api/chat
```

Return:

```json
{
  "message":"Hello AI"
}
```

Learn:

* Controllers
* Routing
* Dependency Injection

---

## Day 3

### Convert to POST

```text
POST
/api/chat
```

Request:

```json
{
  "message":"Explain Dependency Injection"
}
```

Response:

```json
{
  "answer":"..."
}
```

---

# Phase 2: Clean Architecture (Days 4–7)

---

## Day 4

### Create DTOs

```text
DTOs
│
├── ChatRequestDto.cs
└── ChatResponseDto.cs
```

---

### ChatRequestDto

```csharp
public class ChatRequestDto
{
    public string Message { get; set; }
}
```

---

### ChatResponseDto

```csharp
public class ChatResponseDto
{
    public string Answer { get; set; }
}
```

---

## Day 5

### Create Service Layer

```text
Services
│
└── ChatService.cs
```

---

### Interface

```text
Interfaces
│
└── IChatService.cs
```

---

### Benefits

* Loose Coupling
* Testability
* SOLID Principles

---

## Day 6

### Dependency Injection

Register:

```csharp
builder.Services
       .AddScoped<IChatService,
                  ChatService>();
```

---

## Day 7

### Unit Test Setup

Create:

```bash
dotnet new xunit
```

Learn:

* Unit Testing
* Mocking

---

# Phase 3: Azure OpenAI Integration (Days 8–12)

---

## Day 8

Learn:

### Azure OpenAI Concepts

* Deployment
* Endpoint
* API Key

---

## Day 9

Install Package

```bash
dotnet add package Azure.AI.OpenAI
```

---

## Day 10

Create:

```text
Services
│
└── AzureOpenAIService.cs
```

---

### Flow

```text
User
 ↓
Controller
 ↓
Service
 ↓
Azure OpenAI
 ↓
Response
```

---

## Day 11

Add Configuration

```json
{
  "AzureOpenAI": {
      "Endpoint":"",
      "ApiKey":"",
      "DeploymentName":""
  }
}
```

---

## Day 12

Test Prompt

Request:

```json
{
 "message":"What is CQRS?"
}
```

---

# Phase 4: React Frontend (Days 13–17)

---

## Day 13

Create React Project

```bash
npm create vite@latest ai-chat-ui -- --template react-ts
```

---

## Day 14

Create Chat Page

```text
Pages
│
└── ChatPage.tsx
```

---

## Day 15

Create Components

```text
Components
│
├── ChatInput.tsx
├── ChatWindow.tsx
└── Message.tsx
```

---

## Day 16

API Integration

Install:

```bash
npm install axios
```

---

## Day 17

Connect:

```text
React
 ↓
ASP.NET Core API
 ↓
Azure OpenAI
```

---

# Phase 5: Chat History (Days 18–20)

---

## Day 18

Create Model

```csharp
ChatMessage
```

Fields:

```text
Id
Question
Answer
CreatedDate
```

---

## Day 19

Store Messages

Using:

```text
SQL Server
```

or

```text
SQLite
```

---

## Day 20

Show History

React:

```text
Previous Chats
```

---

# Phase 6: Production Features (Days 21–25)

---

## Day 21

Error Handling

---

## Day 22

Logging

Use:

```text
ILogger
```

---

## Day 23

Swagger Documentation

---

## Day 24

Rate Limiting

---

## Day 25

Authentication

JWT

---

# Phase 7: AI Enhancements (Days 26–30)

---

## Day 26

System Prompts

Example:

```text
You are a Senior .NET Architect.
```

---

## Day 27

Conversation Context

Remember previous questions.

---

## Day 28

Prompt Templates

Examples:

* Code Review
* Resume Review
* Interview Questions

---

## Day 29

Add AI Personas

Examples:

```text
.NET Architect

Azure Architect

Technical Lead
```

---

## Day 30

Deployment

Deploy:

### Backend

* Azure App Service

### Frontend

* Azure Static Web Apps

---

# GitHub Structure

```text
dotnet-ai-chat-api
│
├── backend
│   └── AIChatApi
│
├── frontend
│   └── ai-chat-ui
│
├── docs
│   ├── Architecture.md
│   ├── API.md
│   └── Screenshots
│
└── README.md
```

---

# Resume Value

After completing this project, you can honestly add:

### Projects

**AI Chat Assistant (.NET + Azure OpenAI + React)**

* Designed and developed an AI-powered chat application using ASP.NET Core, React, and Azure OpenAI.
* Implemented clean architecture, dependency injection, REST APIs, and prompt engineering techniques.
* Built conversational AI capabilities with configurable system prompts and chat history management.
* Deployed cloud-ready application architecture suitable for enterprise AI integrations.

This single project aligns perfectly with your target positioning:

> **Senior .NET Technical Lead | Azure Cloud | AI-Powered Applications**
