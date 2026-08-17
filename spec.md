# AI-Powered Interview Prep Dashboard

## Overview
A simple React app (Vite) that uses a local AI model (Ollama) to generate company research, role insights, and STAR story feedback. User types any company or role — AI generates everything. Runs fully local.

## Constraints
- **React + Vite only** — no extra UI libraries
- **Plain CSS** — simple styles in one CSS file
- **Ollama for AI** — local LLM at localhost:11434
- **No hardcoded data** — AI generates all content
- **Model switcher** — user can pick which local model to use
- **Learn More section** — links to resources so students can go deeper

## Pre-requisites
- Node.js installed
- Ollama installed and running (`ollama serve`)
- At least one model pulled (e.g. `ollama pull llama3.2`)

## Features

### Tab 1: Company Research
- Text input for company name
- "Research" button → asks Ollama about the company
- Displays: summary, products, values
- Shows which model is being used

### Tab 2: Role Insights
- Text input for role title
- Uses company name from Tab 1
- "Get Insights" button → asks Ollama for responsibilities, skills, interview questions

### Tab 3: STAR Stories
- 4 text fields (Situation, Task, Action, Result)
- Save to localStorage, view/delete saved stories
- "Improve with AI" button → Ollama gives personalized feedback on the story

### Tab 4: Export
- Shows all content combined
- "Print as PDF" button → should not be clickable or do any function.

### Tab 5: Learn More
- Links to resources: Ollama, React, Vite, Llama models, Prompt Engineering Guide, Kiro

### Model Switcher (in header)
- Dropdown to switch between available Ollama models
- Selected model is used for all AI calls

## Tech Stack
- React 18 + Vite
- Plain CSS
- Ollama REST API (localhost:11434)
- localStorage

## File Structure
```
src/
├── App.jsx              # Main app with tabs + model state
├── App.css              # All styles
├── main.jsx             # Entry point
├── ai.js                # askAI helper + MODELS list + SOURCES
├── CompanyResearch.jsx  # Company input + AI call
├── RoleInsights.jsx     # Role input + AI call
├── StarBuilder.jsx      # STAR form + save + AI improve
└── PrepSheet.jsx        # Export/print view
```

## Tasks

- [ ] 1. Init Vite React project, create ai.js with model list, sources, and askAI helper
- [ ] 2. Build App.jsx with 5 tabs, model switcher in header, and basic CSS
- [ ] 3. Build CompanyResearch.jsx — input + button + AI call + display results
- [ ] 4. Build RoleInsights.jsx — input + button + AI call + display results
- [ ] 5. Build StarBuilder.jsx — form + save to localStorage + AI improve button
- [ ] 6. Build PrepSheet.jsx — combine all content + print button
