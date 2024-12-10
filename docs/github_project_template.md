# GitHub Project Template for FaceID-Based Attendance System

## **Project Overview**
This project is to develop a modular, scalable FaceID-based attendance system integrated with an LMS. The project includes three components:
- **FaceID System**: Handles facial embedding extraction and comparison.
- **LMS Integration**: Manages attendance and database operations.
- **Frontend**: Provides user interface for professors and administrators.

---

## **Repository Structure**
```
/faceid/
    /src/
        api.py               # API endpoints for FaceID
        embeddings.py        # Embedding extraction logic
        comparison.py        # Embedding comparison logic
    /tests/
        test_api.py          # API endpoint tests
        test_embeddings.py   # Embedding logic tests
    Dockerfile              # Containerization setup for FaceID

/lms/
    /src/
        integration.py       # Mock LMS integration logic
    /docs/
        requirements.md      # LMS requirements and documentation

/frontend/
    /src/
        app.js              # Frontend logic (React or other frameworks)
    /tests/
        test_ui.js          # UI tests

/docs/
    requirements.md          # Project requirements (functional & non-functional)
    api.md                   # API specifications
    diagrams/
        use_case_diagram.png
        sequence_diagram.png

/tests/
    integration_tests.py     # End-to-end testing for all components
```

---

## **GitHub Project Board**

### **Columns**
1. **Backlog**
   - All tasks and ideas for the project, including requirements, features, and bugs.
2. **To Do**
   - Tasks ready for development or review.
3. **In Progress**
   - Active tasks being worked on.
4. **Review**
   - Completed tasks awaiting review (e.g., pull requests).
5. **Done**
   - Finished tasks.

---

## **Initial Backlog Items**

### **Documentation**
- [ ] Document functional requirements (`/docs/requirements.md`)
- [ ] Define non-functional requirements (`/docs/requirements.md`)
- [ ] Draft API specifications (`/docs/api.md`)
- [ ] Create architecture and data flow diagrams (`/docs/diagrams`)

### **Development**
- [ ] Set up `/faceid` directory and initial FastAPI structure
- [ ] Implement `/extract_embeddings` endpoint
- [ ] Implement `/compare_embeddings` endpoint
- [ ] Write unit tests for `/extract_embeddings`
- [ ] Write unit tests for `/compare_embeddings`

### **Integration**
- [ ] Mock LMS integration script (`/lms/src/integration.py`)
- [ ] Write integration tests for LMS and FaceID APIs

### **Frontend**
- [ ] Create UI mockups for attendance system
- [ ] Set up basic React project structure (`/frontend/src`)
- [ ] Integrate API calls with FaceID and LMS

### **Testing**
- [ ] Write end-to-end tests for FaceID and LMS workflows (`/tests/integration_tests.py`)
- [ ] Test system scalability under high loads

---

## **Milestones**

### **Milestone 1: Requirements and Design**
- Complete `/docs/requirements.md` and `/docs/api.md`.
- Create architecture and sequence diagrams.

### **Milestone 2: Core API Development**
- Implement `/extract_embeddings` and `/compare_embeddings` endpoints.
- Write unit tests for both endpoints.

### **Milestone 3: Integration and Testing**
- Integrate FaceID with LMS.
- Perform end-to-end testing.

### **Milestone 4: Frontend Development**
- Develop UI and connect it to the FaceID and LMS APIs.
- Validate the system with real-world scenarios.

---

## **Labels for Issues**
- `Documentation`: For tasks related to project documentation.
- `Backend`: For FaceID API and LMS integration tasks.
- `Frontend`: For UI-related tasks.
- `Testing`: For unit, integration, and end-to-end testing.
- `Enhancement`: For future features or improvements.
- `Bug`: For reported issues during development.

