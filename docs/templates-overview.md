# Issue Templates Summary

This document provides an overview of the GitHub issue templates created for Mergington High School teachers.

## Template Structure

### 1. Add New Activity (`add-new-activity.yml`)
**Purpose:** Create new clubs, teams, or activities
**Key Fields:**
- Activity name, description, category
- Meeting days and times
- Maximum participants
- Supervising teacher
- Special requirements

**Example Use Case:** "Add Photography Club that meets Thursdays 3:30-5:00 PM"

---

### 2. Modify Existing Activity (`modify-activity.yml`)
**Purpose:** Change existing activity details
**Key Fields:**
- Selection of existing activity to modify
- Checkboxes for types of changes needed
- New values for each field being changed
- Reason for changes and impact on current participants

**Example Use Case:** "Change Chess Club schedule from Tuesday to Wednesday due to conflict"

---

### 3. Bug Report (`bug-report.yml`)
**Purpose:** Report system malfunctions
**Key Fields:**
- Bug area (registration, login, display, etc.)
- Current vs expected behavior
- Steps to reproduce
- Frequency and error messages
- Device/browser information

**Example Use Case:** "Student registration fails with authentication error"

---

### 4. User Interface Improvement (`ui-improvement.yml`)
**Purpose:** Enhance website usability
**Key Fields:**
- Improvement area and target users
- Current problems and proposed solutions
- Priority level and user stories
- Specific feature requests

**Example Use Case:** "Add search box to help students find activities by keyword"

---

### 5. Feature Request (`feature-request.yml`)
**Purpose:** Add new system functionality
**Key Fields:**
- Feature name and category
- Detailed description and problem solving
- User workflow and interaction model
- Success metrics and acceptance criteria

**Example Use Case:** "Add waitlist system for popular activities"

---

### 6. Data & Reporting Request (`data-request.yml`)
**Purpose:** Export data or generate reports
**Key Fields:**
- Type of data needed
- Specific activities and time periods
- Data purpose and required fields
- Output format preferences

**Example Use Case:** "Export Chess Club participant list for permission slips"

---

### 7. Other Request (`other-request.yml`)
**Purpose:** General requests not fitting other categories
**Key Fields:**
- Request title and category
- Detailed description and urgency
- Attempted solutions and success criteria

**Example Use Case:** "Help setting up email notifications for activity updates"

---

### 8. Configuration (`config.yml`)
**Purpose:** Control template display and provide contact links
**Features:**
- Disables blank issues (forces template use)
- Provides emergency IT contact
- Links to school main office
- Links to GitHub documentation

## Teacher Experience

When teachers click "New Issue" on GitHub, they will see:

1. **Template Selection Page** - Choose from 7 clearly labeled options
2. **Guided Form** - Structured fields with helpful placeholders
3. **Required Fields** - Marked with * to ensure completeness
4. **Dropdown Menus** - Reduce typing, ensure consistency
5. **Examples** - Show teachers what good requests look like
6. **Context Sections** - Provide Copilot agent with implementation details

## Copilot Agent Benefits

Each template includes an "Implementation Context" section with:
- Technical hints for code changes
- File paths and function names
- School-specific constraints
- Testing requirements
- Integration considerations

This enables the Copilot coding agent to implement requests without requiring additional clarification from teachers.

## Quality Features

- **YAML Validation**: All templates checked for syntax correctness
- **School Context**: Mergington-specific details included
- **Non-Technical Language**: Written for teachers, not developers
- **Complete Specifications**: Enough detail for autonomous implementation
- **User-Friendly**: Dropdowns, examples, and clear instructions