# GHC Workshop

**Build Your AI-Powered Company Research & Interview Prep Dashboard in 60 Minutes**

This dashboard runs entirely on your own laptop using a local AI model through [Ollama](https://ollama.com). No cloud, no accounts, no API keys.

---

## Prerequisites:

### 1. Download Kiro

Kiro is the AI IDE you'll use to build the dashboard.

1. Go to https://kiro.dev/ and download Kiro for your operating system.
2. Run the installer and open Kiro.
3. Sign in with your email to create a free account.

### 2. Install Ollama

**macOS:**

```
curl -fsSL https://ollama.com/install.sh | sh
```

**Windows:**

```
irm https://ollama.com/install.ps1 | iex
```

### 3. Pull a model

```
ollama pull llama3.2
```

This downloads the LLama3.2 model that we will use

### 4. Start Ollama (with browser access enabled)

The dashboard runs in your browser, and Ollama blocks browser requests by
default. You **must** start it with `OLLAMA_ORIGINS` set, or you'll see a
"Failed to fetch" error in the app.

**macOS:**

```
OLLAMA_ORIGINS='*' ollama serve
```

**Windows (PowerShell):**

```
$env:OLLAMA_ORIGINS='*'; ollama serve
```

Leave this terminal running during the workshop.

> If you already have Ollama running as a background service, stop it first so
> this command's CORS setting takes effect `ollama serve` will say the address
> is already in use otherwise).

### 5. Verify it works

In a new terminal:

```
curl http://localhost:11434/api/tags
```

If you get JSON back listing your models, you're ready.

---

## Workshop Spec File

Once you have opened up a new repo with the spec file, you will prompt Kiro to build it out.

---

## Running the dashboard

```
npm install
npm run dev
```

Then open the URL Vite prints (usually http://localhost:5173).

Pick your model from the dropdown in the header, and start researching.

---

## Troubleshooting

**"Failed to fetch" or "Could not reach Ollama"**

- Ollama isn't running, or it wasn't started with `OLLAMA_ORIGINS='*'`.
- Restart it: `OLLAMA_ORIGINS='*' ollama serve`

**"Ollama returned 404" / model errors**

- The selected model isn't pulled. Run `ollama pull llama3.2` (or the model shown in the dropdown).

**Responses are slow**

- Local models take a few seconds, especially on the first call.
