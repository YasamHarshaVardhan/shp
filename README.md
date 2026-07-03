# 👵🏼 SilverCare AI: Proactive Senior Citizen Companion

**A submission for the Kaggle AI Agents: Intensive Vibe Coding Capstone Project (Agents for Good Track)**

SilverCare AI is a secure, proactive, and accessible multi-agent companion designed to help senior citizens live independently. It utilizes Google's Gemini 2.5 Flash model, Function Calling, and the Web Speech API to provide an intuitive voice-first interface for managing medications, appointments, and proactive health alerts.

---

## 🌟 Key Features

*   **🎙️ Voice-First Interface:** Utilizes the browser's native Web Speech API for seamless Speech-to-Text and Text-to-Speech interactions, eliminating the need for seniors to type.
*   **🧠 Tool-Augmented LLM:** Powered by `gemini-2.5-flash`, the agent dynamically queries the SQLite database via strictly scoped Python functions to retrieve accurate medication schedules and upcoming appointments.
*   **⏰ Proactive Audio Alerts:** A custom frontend polling mechanism checks the Django backend every 60 seconds, verbally alerting the senior exactly 5 minutes before a medication is due, and 1 hour before an appointment.
*   **🔒 Multi-Tenant Data Privacy:** Built with strict user-scoping. The AI tools intercept the Django `request.user` session, mathematically guaranteeing that the LLM can only retrieve and discuss health records belonging to the currently authenticated user.
*   **📱 Accessible UI:** Features a high-contrast, Bootstrap 5 responsive design with large typography, a prominent "Push to Talk" button, and a seamless Light/Dark mode toggle via CSS variables.

---

## 🏗️ Architecture & Course Concepts Applied

This project demonstrates several key concepts from the Kaggle AI Agents Intensive:

1.  **Agent Skills (Tool Use):** The Orchestrator Agent utilizes custom Python functions (`get_daily_medications`, `get_upcoming_appointments`) mapped to the Gemini API to execute real-time database lookups rather than relying on static training data.
2.  **Security Features:** Implements strict Data Privacy. All views are protected by `@login_required`, and database queries passed to the LLM are hardcoded to filter by `user=request.user`, preventing cross-tenant data hallucination or leakage.
3.  **Antigravity IDE:** The entire full-stack architecture was scaffolded, iterated, and refined using the Antigravity Vibe Coding environment.

---

## 🚀 Quickstart: How to Run Locally

Follow these steps to run SilverCare AI on your local machine for judging.

### 1. Prerequisites
*   Python 3.10+
*   A Google Gemini API Key (Get one from [Google AI Studio](https://aistudio.google.com/))

### 2. Installation
Clone the repository and navigate into the project folder:
```bash
git clone [https://github.com/yourusername/silvercare-ai.git](https://github.com/yourusername/silvercare-ai.git)
cd silvercare-ai
