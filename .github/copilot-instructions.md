# Mergington High School Activities Management System

**ALWAYS follow these instructions first** and only fall back to additional search and context gathering if the information in the instructions is incomplete or found to be in error.

## Working Effectively

### Environment Setup and Dependencies
- Install Python dependencies:
  ```bash
  python3 -m pip install -r src/requirements.txt
  ```
  **Takes < 1 second if dependencies already installed**

- Start MongoDB using Docker (REQUIRED):
  ```bash
  docker run -d --name mongodb -p 27017:27017 mongo:7.0
  ```
  **Takes 15 seconds on first run (image download). NEVER CANCEL - set timeout to 300+ seconds for initial setup.**

- Verify MongoDB connection:
  ```bash
  python3 -c "from pymongo import MongoClient; client = MongoClient('mongodb://localhost:27017/'); print(f'Connected to MongoDB: {client.server_info()[\"version\"]}')"
  ```

### Running the Application
- Start the development server:
  ```bash
  python3 -m uvicorn src.app:app --host 0.0.0.0 --port 8000 --reload
  ```
  **Starts in < 5 seconds. Use --reload for development (auto-restarts on code changes).**

- Access the application:
  - Main website: http://localhost:8000/static/index.html  
  - API documentation: http://localhost:8000/docs
  - Activities API: http://localhost:8000/activities

### VS Code Debugging
- Use the pre-configured "Launch Mergington WebApp" debug configuration
- Press F5 or use Run and Debug view (Ctrl+Shift+D)
- The debugger runs: `uvicorn src.app:app --reload`

## Validation

### Manual Testing Requirements
**ALWAYS test actual functionality after making changes. Simply starting/stopping the application is NOT sufficient.**

**Critical Validation Scenarios:**
1. **API Functionality Test:**
   ```bash
   curl -s http://localhost:8000/activities | head -n 50
   ```
   Verify activities data returns JSON with school activities.

2. **Web Interface Test:**
   ```bash
   curl -s http://localhost:8000/static/index.html | head -n 20
   ```
   Verify HTML page loads with "Mergington High School" title.

3. **Authentication Test:**
   - Load http://localhost:8000/static/index.html in browser
   - Click Login button
   - Test with sample teacher credentials (check `src/backend/database.py` for initial teacher accounts)

4. **End-to-End Activity Signup:**
   - Login as teacher
   - View activities list  
   - Test activity signup/viewing functionality

### Code Quality Validation
- Python syntax check: `python3 -m py_compile src/app.py`
- ALWAYS run this before committing Python changes

## Common Tasks

### Repository Structure
```
.
├── README.md              # Project overview
├── docs/
│   └── how-to-develop.md  # Development guide
├── src/
│   ├── app.py            # FastAPI main application
│   ├── requirements.txt  # Python dependencies  
│   ├── backend/
│   │   ├── database.py   # MongoDB connection and initial data
│   │   └── routers/      # FastAPI route handlers
│   │       ├── activities.py  # Activity management API
│   │       └── auth.py        # Authentication API
│   └── static/           # Frontend files
│       ├── index.html    # Main web interface
│       ├── app.js        # JavaScript functionality  
│       └── styles.css    # Styling
├── .devcontainer/        # Development container config
├── .vscode/              # VS Code settings
└── .github/              # GitHub workflows and this file
```

### Key Application Details
- **FastAPI web application** serving both API and static frontend
- **MongoDB database** for storing activities and teacher accounts
- **No build step required** - runs directly with uvicorn
- **Port 8000** used for development server
- **Authentication required** for activity signup (teachers can manage)

### School Context
- School name: "Mergington High School"  
- Public high school in Mergington, Florida
- School motto: "Branch out and grow"
- Serves grades 9-12, ~100-150 students per grade
- Academic year: August to May, 3 trimesters + optional summer cycle

## Development Guidelines

### User Interaction
- Staff is not technical - explain in simple terms, avoid software jargon
- Code must be easy to maintain without significant coding experience

### Architecture Constraints  
- Website users: students and teachers - keep UX simple
- Do not create additional apps, services, or command line tools
- Use only HTML, CSS, JavaScript, and Python
- Maintain clear directory structure (do not create single large files)

### Security Considerations
- Personal information is processed - privacy/security are important
- Do not hardcode secrets, passwords, or sensitive information
- Use proper login dialogs and local credential storage

### Quality Requirements
- For grades/scores/numerical data: isolate functions and add unit tests
- Always update documentation when making changes
- Test functionality manually after changes

## Troubleshooting

### MongoDB Issues
- If connection fails: ensure Docker container is running with `docker ps`
- Restart container: `docker restart mongodb`
- If port conflicts: `docker stop mongodb && docker rm mongodb` then restart

### Application Won't Start
- Verify Python dependencies: `pip install -r src/requirements.txt`
- Check MongoDB connection before running application
- Ensure port 8000 is available

### VS Code Debugging Issues  
- Use the configured "Launch Mergington WebApp" launch configuration
- Do not modify the uvicorn command in launch.json without testing
