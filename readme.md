# DjangoWebSockets

This project demonstrates the implementation of WebSockets in a Django application, enabling real-time message exchange between users in the same chat room. Redis is used as the message broker, running on Docker.

---

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Setup](#setup)
3. [Testing the Application](#testing-the-application)
4. [Notes](#notes)


## Prerequisites

1. **Python** (3.8 or later)
2. **Django** 
3. **Channels** library for WebSocket support
4. **Redis** running on the default port (6379) 

---
## Setup

1. **Clone the repository:**
    ```babash
    git clone <repository-url>
    cd <repository-directory>
    ```

2. **Create and activate a virtual environment:**
    ```bash
    python -m venv env
    source env/bin/activate  # On Windows use `env\Scripts\activate`
    ```

3. **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4. **Run database migrations:**
    ```bash
    python manage.py makemigrations     
    python manage.py migrate
    ```

5. **Install and run Redis:**
    ```bash
    sudo apt-get install redis-server
    sudo service redis-server start
    ```
    Or use **docker** (optional):
    ```bash
    docker pull redis:latest
    docker run -d --name redis-container -p 6379:6379 redis:latest
    ```

6. **Start the development server:**
    ```bash
    python manage.py runserver
    ```

## Testing the Application

1. Open two tabs in your browser.
2. Navigate to the chat interface (e.g., http://127.0.0.1:8000/chat/).
3. Enter the same room name in both tabs.
4. Send a message from one tab, and observe it appearing in real time on the other tab.

## Notes

1. Ensure Docker is running and the Redis container is active before starting the server.
2. For any issues with Redis connectivity, verify that port 6379 is not blocked and that Redis is accessible
