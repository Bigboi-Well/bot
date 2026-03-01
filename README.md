# Chatbot Web App

A simple single-page chat interface built with React, TypeScript, Vite, and Tailwind CSS.

## Features

- Single-page chat UI with scrollable message history
- User and bot messages displayed in distinct chat bubbles
- **Ollama-powered AI** for intelligent, context-aware responses
- Conversation context (the bot remembers the chat)
- Loading state while the bot thinks
- Error handling with helpful messages

## Tech Stack

- **Frontend:** React 18 + TypeScript + Vite
- **Styling:** Tailwind CSS
- **AI:** Ollama (local LLM)
- **State:** React hooks (useState, useCallback, useEffect)

## Prerequisites

- Node.js 18+ (LTS recommended)
- npm or yarn
- **Ollama** (for AI responses) — [ollama.com](https://ollama.com)

## Project Structure

```
chatbot-app/
├── index.html          # HTML entry
├── package.json
├── vite.config.ts
├── tsconfig.json
├── tailwind.config.js
├── postcss.config.js
├── README.md
├── public/
│   └── vite.svg
└── src/
    ├── main.tsx        # React entry point
    ├── App.tsx         # Root component
    ├── index.css       # Tailwind imports
    ├── vite-env.d.ts
    ├── components/
    │   ├── ChatContainer.tsx   # Chat layout + state
    │   ├── ChatMessage.tsx     # Single message bubble
    │   └── ChatInput.tsx       # Input + Send button
    └── utils/
        └── chatbot.ts          # Placeholder bot logic
```

## Installation

### Using npm

```bash
cd chatbot-app
npm install
```

### Using yarn

```bash
cd chatbot-app
yarn
```

## Running the App

### Development server (npm)

```bash
npm run dev
```

### Development server (yarn)

```bash
yarn dev
```

Then open [http://localhost:5173](http://localhost:5173) in your browser.

## Ollama Setup (Required for AI)

1. Install [Ollama](https://ollama.com) and ensure it's running.
2. Pull a model (one-time):
   ```bash
   ollama run llama3.2
   ```
   Or use another model: `llama3`, `mistral`, `phi3`, etc.

3. The chatbot uses `llama3.2` by default. To change it, edit `DEFAULT_MODEL` in `src/utils/chatbot.ts`.

If Ollama isn't running, you'll see: *"Can't reach Ollama. Make sure Ollama is running."*

### Build for production

```bash
npm run build
# or
yarn build
```

### Preview production build

```bash
npm run preview
# or
yarn preview
```

## Chatbot Logic (Ollama)

The bot uses **Ollama** for AI responses. It sends the full conversation history so the bot can give context-aware answers. The default model is `llama3.2`; you can change it in `src/utils/chatbot.ts`.

## Error Handling

- Empty or invalid input is handled with user-friendly messages
- Errors are displayed inline in the chat UI
- Form validation prevents sending empty messages
