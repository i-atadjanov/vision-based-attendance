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

---

## **Lesson 1 Outputs**

### **Functional Requirements**
```
# Functional Requirements
- Extract embeddings from a facial image.
- Compare live embeddings to stored embeddings.
- Return similarity scores and potential matches.
- Integrate with LMS to update attendance.
```

### **Non-Functional Requirements**
```
# Non-Functional Requirements
- Process images in real-time (<500ms per image).
- Ensure high accuracy (95%+ identification rate).
- Maintain privacy: no image or embedding storage in the FaceID system.
- Scalable to handle multiple classrooms concurrently.
```

### **API Draft**
```
# API Specifications
## Endpoint: /extract_embeddings
- Method: POST
- Input:
  ```json
  {
    "image": "<base64_encoded_image>"
  }
  ```
- Output:
  ```json
  {
    "embedding": [0.123, 0.456, 0.789],
    "version": "v1.0"
  }
  ```

## Endpoint: /compare_embeddings
- Method: POST
- Input:
  ```json
  {
    "live_embedding": [0.123, 0.456, 0.789],
    "stored_embeddings": [
      {"student_id": "123", "embedding": [0.122, 0.457, 0.788]},
      {"student_id": "456", "embedding": [0.321, 0.654, 0.987]}
    ]
  }
  ```
- Output:
  ```json
  {
    "matches": [
      {"student_id": "123", "similarity": 0.98},
      {"student_id": "456", "similarity": 0.67}
    ]
  }
  ```

## Endpoint: /health
- Method: GET
- Output:
  ```json
  {
    "status": "healthy"
  }
  ```
```
