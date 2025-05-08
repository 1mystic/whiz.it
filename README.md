# Whiz.it - The Intelligent Quiz Master

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Flask](https://img.shields.io/badge/Flask-%E2%98%AB%EF%B8%8F%202.x-brightgreen.svg)
![Vue.js](https://img.shields.io/badge/Vue.js-3.x-success.svg)
![Redis](https://img.shields.io/badge/Redis-brightred.svg)
![Celery](https://img.shields.io/badge/Celery-orange.svg)

**Whiz.it** is a modern, fresh, and minimalist quiz master application designed to provide an engaging and insightful learning experience. Users can test their knowledge across various subjects and chapters, benefit from instant AI-powered feedback, track their progress, and engage with a comprehensive set of features to enhance their learning journey.

## ✨ Key Features

* **Diverse Quizzes:** Attempt quizzes organized by subjects and chapters.
* **Bookmarks:** Save questions for later review.
* **Score Revisits:** Access and analyze past quiz scores.
* **Instant AI Feedback:** Receive immediate, intelligent feedback on answers powered by Google Generative AI.
* **Score History:** Track the evolution of your performance over time.
* **User Profiles:** Personalized profiles with a leaderboard to foster healthy competition.
* **Dedicated Summary Page:** A consolidated view of your quiz activity and progress.
* **Report Generation:** Options to download and email detailed quiz reports.
* **Daily Reminders:** Stay on track with daily quiz reminders delivered via email.
* **Monthly Activity Reports:** Gain insights into your monthly learning activity through comprehensive email reports.
* **AI-Powered Analysis Page:** Delve deeper into your strengths and weaknesses with intelligent analysis powered by AI.
* **Admin Panel (RBAC):** A robust administration interface with Role-Based Access Control (RBAC) for platform management.
* **Modern UI:** A clean and minimalist user interface built with Vue 3 Options API.

## 🛠️ Built With

* **Backend:**
    * [Python](https://www.python.org/)
    * [Flask](https://flask.palletsprojects.com/) - A microframework for Python based on Werkzeug, Jinja 2 and good intentions.
    * [Celery](https://docs.celeryq.dev/) - A distributed task queue.
    * [Celery Beat](https://docs.celeryq.dev/en/stable/schedule.html) - A scheduler for Celery tasks.
    * [Redis](https://redis.io/) - An in-memory data structure store, used for caching and as a message broker.
    * [Flask-Mailman](https://flask-mailman.readthedocs.io/en/stable/) - A Flask extension for sending emails.
    * [Google Generative AI](https://ai.google.dev/) - For providing intelligent feedback on quiz answers.
* **Frontend:**
    * [Vue.js](https://v3.vuejs.org/) - A progressive JavaScript framework.
    * [Vue 3 Options API](https://vuejs.org/guide/introduction.html#options-api) - The Options API for structuring Vue components.

## 🚀 Getting Started

To get Whiz.it up and running on your local machine, follow these steps:

### Prerequisites

* Python 3.x
* Node.js and npm (or yarn)
* Redis server installed and running
* Google Cloud Project with the Generative AI API enabled and API key configured
* Email service credentials for Flask-Mailman

### Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository_url>
    cd whiz.it
    ```

2.  **Set up the backend:**
    ```bash
    cd backend
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    pip install -r requirements.txt
    ```

3.  **Configure environment variables:**
    Create a `.env` file in the `backend` directory and configure the necessary environment variables, including:
    * Flask application settings (e.g., `FLASK_APP`, `FLASK_ENV`)
    * Redis connection details (`REDIS_URL`)
    * Celery broker and backend URLs (`CELERY_BROKER_URL`, `CELERY_RESULT_BACKEND`)
    * Google Generative AI API key (`GOOGLE_API_KEY`)
    * Email configuration for Flask-Mailman (e.g., `MAIL_SERVER`, `MAIL_PORT`, `MAIL_USERNAME`, `MAIL_PASSWORD`)
    * Database connection details (if applicable)

4.  **Initialize the database:**
    ```bash
    # Example for Flask-SQLAlchemy (adjust based on your ORM/database)
    flask db init
    flask db migrate -m "Initial migration"
    flask db upgrade
    ```

5.  **Run the Celery worker and beat:**
    Open two separate terminal windows in the `backend` directory:
    ```bash
    celery -A your_app_name.celery worker -l info
    celery -A your_app_name.celery beat -l info
    ```
    *(Replace `your_app_name` with the name of your Flask application instance)*

6.  **Run the Flask development server:**
    ```bash
    flask run
    ```

7.  **Set up the frontend:**
    ```bash
    cd ../frontend
    npm install  # Or yarn install
    ```

8.  **Configure frontend environment variables:**
    Create a `.env` file in the `frontend` directory (if needed) to configure API endpoints or other environment-specific settings.

9.  **Run the Vue.js development server:**
    ```bash
    npm run serve  # Or yarn serve
    ```

    The frontend application should now be accessible at `http://localhost:8080` (or a different port if configured). The backend API will likely be running on `http://localhost:5000`.

## ⚙️ Usage

Once the application is running, users can:

* **Browse Quizzes:** Explore available quizzes by subject and chapter.
* **Attempt Quizzes:** Select a quiz and answer the questions.
* **Receive AI Feedback:** Get instant explanations and insights on their answers.
* **Manage Bookmarks:** Add and review challenging questions later.
* **View Scores:** Check past quiz results and track their progress.
* **Access Profile:** See their leaderboard ranking and manage their account.
* **Explore Summary:** Get a quick overview of their quiz activity.
* **Download/Email Reports:** Generate and share their performance reports.
* **Receive Notifications:** Get daily quiz reminders and monthly activity summaries via email.
* **Utilize AI Analysis:** Gain deeper insights into their learning patterns and areas for improvement.

Administrators can access the admin panel (usually at a specific route like `/admin`) to manage users, quizzes, subjects, chapters, and other platform configurations based on their assigned roles.

## 🖼️ Screenshots

*(Consider adding a `screenshots` folder and including a few enticing screenshots of the UI here to showcase the modern and clean design.)*

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

* Thanks to the developers of Flask, Vue.js, Celery, Redis, Flask-Mailman, and Google Generative AI for their amazing tools and libraries.
* *(Optional: Mention any other libraries, resources, or individuals who contributed to the project.)*

## 📬 Contact

*(Optional: Add your contact information or a link to your portfolio/website.)*