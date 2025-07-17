# One Brave Thing - Backend API

## Project Overview
This is the backend API for the "One Brave Thing" application, a goal-setting and personal development platform that helps users achieve their goals through daily tasks and consistent feedback.

## Setup Instructions

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Set up environment variables:
Create a `.env` file with:
```env
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_key
```

3. Run the application:
```bash
python main.py
```

## API Endpoints

### Authentication
- `POST /api/register` - Register new user
- `POST /api/login` - User login

### Goal Management
- `POST /api/goal/discovery` - Start goal discovery process
- `POST /api/goal/set` - Set user goal
- `POST /api/goal/personalise` - Personalize goal approach

### Task Management
- `POST /api/task/daily` - Get daily task
- `POST /api/task/confirm-adjust` - Confirm or adjust task
- `POST /api/task/complete` - Mark task as complete
- `POST /api/task/self-reflection` - Submit task reflection
- `GET /api/tasks/all` - Get all tasks
- `GET /api/tasks/incomplete` - Get incomplete tasks
- `GET /api/tasks/completed` - Get completed tasks

### Feedback and Progress
- `POST /api/feedback/weekly` - Submit weekly feedback
- `GET /api/feedback/progress` - Get progress report
- `GET /api/profile/stats` - Get user stats
- `POST /api/summary/generate` - Generate weekly summary

### Utilities
- `GET /api/quote` - Get motivational quote
- `POST /api/freeze` - Use freeze day

## Database Schema

### Tables
1. profiles
   - id (UUID)
   - name
   - username
   - password (hashed)
   - age
   - gender
   - streak
   - points
   - freeze_days
   - goal

2. daily_tasks
   - id (UUID)
   - user_id (FK)
   - date
   - description
   - difficulty
   - completed
   - feedback

3. weekly_feedback
   - id (UUID)
   - user_id (FK)
   - week_start
   - improvement_rating
   - comment

4. weekly_summaries
   - id (UUID)
   - user_id (FK)
   - summary
   - date_generated

## Security Notes
- Passwords are hashed using bcrypt before storage
- API endpoints will require authentication (to be implemented)
- Environment variables are used for sensitive data