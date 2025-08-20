# Mergington High School Activities

A comprehensive web application for managing extracurricular activities at Mergington High School. This modern system provides teachers with tools to manage student registrations while offering students an intuitive interface to discover and join activities.

## Features

### For Teachers
- **Secure Authentication**: Login system for teachers to manage student registrations
- **Student Registration Management**: Register and unregister students for activities
- **Activity Oversight**: View participant lists and manage activity capacity

### For Students & Visitors
- **Activity Discovery**: Browse all available extracurricular activities
- **Advanced Filtering**: Filter activities by:
  - Category (Sports, Arts, Academic, Technology, Community)
  - Day of the week (Monday through Sunday)
  - Time slots (Before School, After School, Weekend)
- **Search Functionality**: Search activities by name or description
- **Detailed Information**: View activity descriptions, schedules, and participant counts

### Activity Categories
The system supports diverse extracurricular activities including:
- **Sports**: Soccer Team, Basketball Team, Morning Fitness
- **Academic**: Math Club, Debate Team, Science Olympiad, Chess Club
- **Arts**: Art Club, Drama Club, Manga Maniacs
- **Technology**: Programming Class, Weekend Robotics Workshop
- And many more!

## Technology Stack

- **Backend**: FastAPI (Python web framework)
- **Database**: MongoDB with structured activity and user data
- **Server**: Uvicorn ASGI server
- **Frontend**: Modern HTML5, CSS3, and JavaScript
- **Security**: Argon2 password hashing for teacher authentication
- **Dependencies**: See `requirements.txt` for complete list

## Development Guide

For detailed setup and development instructions, please refer to our [Development Guide](../docs/how-to-develop.md).

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/activities/` | Get all activities with optional filtering by day/time |
| GET | `/activities/days` | Get list of all days that have activities scheduled |
| POST | `/activities/{activity_name}/signup` | Register a student for an activity (requires teacher auth) |
| POST | `/activities/{activity_name}/unregister` | Remove a student from an activity (requires teacher auth) |
| POST | `/auth/login` | Teacher login authentication |
| GET | `/auth/check-session` | Validate teacher session |

## Data Persistence

The application uses MongoDB for persistent data storage, ensuring that activity registrations and user data are maintained across server restarts. The database includes:

- **Activities Collection**: Stores activity details, schedules, participant lists, and capacity limits
- **Teachers Collection**: Manages teacher accounts with secure password hashing

## Quick Start

1. Install dependencies: `pip install -r requirements.txt`
2. Ensure MongoDB is running locally
3. Run the application: `python app.py`
4. Visit `http://localhost:8000` to access the application
5. API documentation available at `http://localhost:8000/docs`
