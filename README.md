# Full Stack + NLP Project

This project is a web-based chat application with an integrated meeting scheduler. It uses a React frontend and a Django backend. The application allows users to chat in groups and schedule Google Meet meetings based on natural language processing of the chat messages.

## Features

-   **User Authentication**: Users can register and log in to the application.
-   **Group Chat**: Authenticated users can send and receive messages within their assigned group.
-   **Meeting Scheduling**: The application uses NLP to detect the intent to schedule a meeting from chat messages.
-   **Google Meet Integration**: Automatically generates a Google Meet link when a meeting is scheduled.
-   **Real-time Updates**: The chat interface polls for new messages every 5 seconds to provide a near real-time experience.

## Technologies Used

**Frontend:**

-   React
-   Vite
-   Axios
-   React Router

**Backend:**

-   Django
-   Django REST Framework
-   Simple JWT for authentication
-   Spacy for NLP
-   Google API Client for Google Meet integration

## Setup and Installation

### Backend

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/provivo_aiml.git
    cd provivo_aiml/backend
    ```

2.  **Create a virtual environment and install dependencies:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    pip install -r requirements.txt
    ```

3.  **Set up Google API credentials:**
    -   Obtain a `service_account.json` file from the Google Cloud Console with the "Google Calendar API" enabled.
    -   Place the `service_account.json` file in the `backend/chat/` directory.

4.  **Run database migrations:**
    ```bash
    python manage.py migrate
    ```

### Frontend

1.  **Navigate to the frontend directory:**
    ```bash
    cd ../frontend
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

## Running the Application

### Backend

1.  **Start the Django development server:**
    ```bash
    cd backend
    python manage.py runserver
    ```
    The backend will be running at `http://127.0.0.1:8000`.

### Frontend

1.  **Start the Vite development server:**
    ```bash
    cd frontend
    npm run dev
    ```
    The frontend will be running at `http://localhost:5173`.

## API Endpoints

The following are the main API endpoints provided by the backend:

-   `POST /api/auth/register/`: Register a new user.
-   `POST /api/auth/login/`: Log in an existing user.
-   `GET, POST /api/chat/messages/`: Get all messages for the user's group or send a new message.
-   `POST /api/chat/schedule/`: Schedule a meeting.
-   `POST /api/chat/availability/`: Update a user's availability for a meeting.
-   `GET /api/chat/group/`: Get details of the user's group.
-   `GET /api/chat/groups/`: Get a list of all available groups.
