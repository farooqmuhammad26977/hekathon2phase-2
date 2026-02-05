# Secure Multi-User Todo Application

This is a full-stack secure todo application built with Next.js (frontend) and FastAPI (backend).

## Project Structure

```
├── backend/              # FastAPI backend
│   ├── main.py           # Application entry point
│   ├── models/           # Data models
│   ├── db/              # Database services
│   ├── auth/            # Authentication handlers
│   ├── dependencies/    # Security dependencies
│   └── routes/          # API routes
├── frontend/            # Next.js frontend files moved to root
├── app/                 # Next.js app directory (moved to root)
├── components/          # React components
├── lib/                 # Utility libraries
├── styles/              # Global styles
├── requirements.txt     # Python dependencies
├── package.json         # Node.js dependencies
└── .env.example         # Environment variables example
```

## Running the Application

### Frontend (Next.js)

1. Make sure you're in the project root directory
2. Install dependencies: `npm install`
3. Create a `.env.local` file with your environment variables:
   ```
   NEXT_PUBLIC_API_BASE_URL=http://localhost:8000
   ```
4. Run the development server: `npm run dev`
5. Visit `http://localhost:3002` in your browser (or `http://localhost:3000`/`http://localhost:3001` if those ports are available)

### Backend (FastAPI)

1. Navigate to the backend directory: `cd backend`
2. Install Python dependencies: `pip install -r requirements.txt`
3. Set up environment variables (copy from `.env.example`)
4. Run the server: `uvicorn main:app --reload`
5. The backend will be available at `http://localhost:8000`

## Features

- Secure JWT-based authentication
- User data isolation (users can only access their own tasks)
- Full CRUD operations for tasks
- Responsive UI with Tailwind CSS
- Task completion toggle
- Protected routes
- Error handling and validation

## API Endpoints

All endpoints require JWT authentication:

- `GET /api/{user_id}/tasks` - Get all tasks for user
- `POST /api/{user_id}/tasks` - Create new task
- `GET /api/{user_id}/tasks/{id}` - Get specific task
- `PUT /api/{user_id}/tasks/{id}` - Update task
- `DELETE /api/{user_id}/tasks/{id}` - Delete task
- `PATCH /api/{user_id}/tasks/{id}/complete` - Toggle completion status