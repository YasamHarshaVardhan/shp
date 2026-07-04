SilverCare AI: Proactive Senior Companion

SilverCare AI is an autonomous, voice-enabled assistant designed to help senior citizens manage their health independently. This project serves as a submission for the Kaggle "AI Agents: Intensive Vibe Coding Capstone" (Agents for Good track).

It is built using a secure Django backend, a local SQLite database for data privacy, and the Google Gemini API for intelligent conversation and task orchestration.

Key Features

Proactive Alerts: The system autonomously monitors medication and appointment schedules, providing voice-based alerts 5 minutes before medications and 1 hour before appointments.

Secure Agent Architecture: All AI tools are strictly scoped to the authenticated user. The agent can only access health data belonging to the logged-in individual, ensuring multi-tenant isolation.

Custom Interface: Built with a custom, high-contrast, accessibility-focused HTML/CSS frontend, designed to be simple and easy for older adults to navigate.

Dual-Input Interaction: Supports both natural voice conversation (via Web Speech API) and manual input for users who prefer typing or need to add records manually.

Installation and Setup

1. Prerequisites

Python 3.10 or higher installed.

A free Google Gemini API Key (get it at Google AI Studio).

2. Environment Setup

Clone this repository and set up your virtual environment:

git clone https://github.com/yourusername/silvercare-ai.git
cd silvercare-ai

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# Install dependencies
pip install django google-genai python-dotenv


3. API Configuration (CRITICAL)

For security, your Gemini API key must be stored in a local .env file.

In your project root directory (where manage.py is located), create a new file named .env.

Open the file and paste your key in this format:

GEMINI_API_KEY=your_actual_api_key_here


Save the file. The project will automatically load this key when running.

4. Database Setup

Apply the migrations to initialize your local SQLite database:

python manage.py makemigrations
python manage.py migrate


5. Running the Server

Start the application:

python manage.py runserver


Open your browser to http://127.0.0.1:8000. When prompted, click "Allow" for microphone access to enable voice features.

Testing for Judges

To verify the proactive alerting and multi-tenant security:

Register: Create an account to isolate your data.

Add Data: Use the "Manage Records" dashboard to add a medication scheduled 2 minutes in the future.

Verify Proactive Alerts: Keep the "Companion" tab open. When the time arrives, the browser will verbally alert you to take your medication.

Security Check: Log out and log in with a different account. You will see that your medications and appointments are completely hidden and isolated, proving the agent's scoped tool permissions.

Developed for the Kaggle AI Agents Intensive Capstone | July 2026


***

### Your Next Step

With the README done, your repository is ready for judges to clone. 

Would you like me to start drafting the **2,500-word Kaggle Writeup** now? I can structure it exactly according to the 30-point "Pitch" and 20-point "Writeup" rubrics so you have a massive head start!
