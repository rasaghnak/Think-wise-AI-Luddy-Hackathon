# ThinkWise AI

AI-Powered Idea Prioritization Platform


## Overview

**ThinkWise AI** is an AI-driven platform designed to help organizations prioritize ideas and enhancement requests collected through enterprise portals such as ServiceNow Idea Portals or internal innovation management systems.

It leverages multi-agent LLM architectures to objectively assess ideas based on **implementation effort** and **return on investment (ROI)**, delivering explainable rankings and actionable insights for innovation and product teams.

---

## Problem Statement

Modern enterprises collect large volumes of ideas, but lack systematic and explainable ways to prioritize them.

Challenges include:

* Balancing **implementation effort** and **business impact**
* Managing large volumes of submissions
* Reducing bias in selection
* Aligning decisions with strategic goals
* Providing transparency to stakeholders

---

## Solution Approach

ThinkWise AI implements an AI-driven decision assistant using the **ReAct (Reasoning + Action)** framework combined with multi-agent workflows to:

* Score and rank ideas
* Provide explainable reasoning
* Visualize decision outcomes
* Enable human-in-the-loop interaction
* Support ongoing learning and tuning

---

## Architecture

### System Workflow

1. **Input Layer**

   * Single idea submission or CSV batch upload

2. **AI Multi-Agent Workflow**

   * **Effort Estimator Agent**
     Evaluates time, resources, complexity, and dependencies
   * **ROI Estimator Agent**
     Estimates market value, demand, business impact using external intelligence
   * **Aggregator Agent**
     Combines scores and reasoning for final ranking

3. **Explainability Layer**

   * AI-powered conversational agent to explain rankings
   * Transparent logging of reasoning steps

4. **Visualization Layer**

   * Interactive dashboard with trends, rankings, and insights

---

### Agent Architecture Diagram

```
┌────────────────────┐
│  Idea Input (UI/API) │
└─────────┬──────────┘
          ↓
┌──────────────────────────────────┐
│   ReAct Multi-Agent Pipeline      │
└──────────────────────────────────┘
    ↓ Effort Estimator Agent
    ↓ ROI Estimator Agent (with Tavily API)
    ↓ Aggregator Node
          ↓
┌────────────────────┐
│    Final Output    │
└────────────────────┘
    ↓
Interactive Dashboard + AI Chat
```

---

## Key Features

* **Effort vs. ROI Scoring**
  Automated scoring of ideas based on objective models
* **Interactive AI Chat**
  Conversational agent to explain reasoning per idea
* **Real-time Analytics Dashboard**
  Track trends, score distributions, and performance
* **Team Collaboration**
  Personalized team page with user insights
* **Parameter Tuning**
  Adjustable weightings for scoring dimensions
* **Secure Authentication**
  JWT-based token authentication
* **Batch Processing**
  Support for single or bulk (CSV) idea evaluation

---

## Technology Stack

### Frontend

* **Framework:** React.js
* **Styling:** Tailwind CSS
* **Animations:** Framer Motion
* **Data Visualization:** Chart.js
* **API Communication:** Axios

### Backend

* **Framework:** FastAPI (Python)
* **AI/LLM Engine:** LangChain, LangGraph, LangSmith
* **LLM Platform:** Google Cloud Vertex AI
* **Data Storage:** MongoDB
* **Search & External Intelligence:** Tavily API
* **Authentication:** JWT-based token system

---

## API Endpoints

The backend exposes a RESTful API for:

### Health

* `GET /health` — Service status

### Authentication

* `POST /auth/register` — Register user
* `POST /auth/login` — Obtain token
* `GET /auth/me` — Current user details
* `POST /auth/forgot-password` — Initiate password reset
* `POST /auth/reset-password` — Complete password reset

### Idea Analysis

* `POST /analyze/single` — Analyze a single idea
* `POST /analyze/csv` — Batch analysis via CSV upload

### Chat with AI Agent

* `POST /chat/idea/{id}` — Conversational query about specific idea

### Idea Management

* `GET /ideas/` — List ideas for current user
* `GET /ideas/{id}` — Get idea details
* `GET /ideas/{id}/history` — Chat history for an idea
* `DELETE /ideas/{id}` — Delete idea
* `DELETE /ideas/` — Bulk delete user ideas

### Rankings & Analytics

* `GET /ideas/top` — Top-ranked ideas (per file)
* `GET /ideas/overall_top` — Top-ranked ideas across all submissions
* `GET /ideas/data` — All idea data (analytics processing)
* `GET /ideas/analytics` — Aggregated analytics



## Potential Enhancements (Roadmap)

* Learning feedback loop for model refinement
* Enterprise integrations (ServiceNow, Jira, Confluence)
* Advanced scoring heuristics (industry-specific models)
* Improved visualization and storytelling reports
* CI/CD pipeline for production deployment
* Cloud-native architecture with containerization (Docker/Kubernetes)

---

## Target Users

* Innovation teams
* Product managers
* Corporate strategy groups
* R\&D organizations
* Accelerators and incubators

---

## Contributors

* **Siddartha Koppaka**
* **Rasaghna Kuturu**
* **Adithya Singupati**
* **Mohit T**



