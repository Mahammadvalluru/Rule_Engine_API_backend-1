# Rule Engine Backend

This repository contains the backend of a rule engine system built using FastAPI, SQLite, and uvicorn. The system allows users to define, store, and evaluate logical rules based on data inputs. Additionally, rules can be combined using logical `AND` and `OR` conditions.

## Features

- Define rules using a simple string format (e.g., "temperature > 30 AND humidity < 50").
- Convert rules into an Abstract Syntax Tree (AST) for evaluation.
- Store rules in an SQLite database.
- Fetch, evaluate, and combine rules through API endpoints.
- CORS middleware to allow interaction with the frontend.
- FastAPI-based API with endpoints to create, evaluate, and combine rules.
- Built-in error handling and logging.

## Frontend

The frontend for this rule engine project is a React-based application that provides a user interface for interacting with the backend API. Users can create, view, and evaluate rules through the frontend.

- **Frontend repository**: [Rule Engine Frontend](https://github.com/shivateja20013/rule_engine_frontend)
- The frontend is built with React and communicates with the backend via API requests.

## Technologies Used

### Backend
- **FastAPI**: High-performance backend API framework.
- **SQLite**: Database for storing rules.
- **Uvicorn**: ASGI server for FastAPI.
- **CORS Middleware**: To handle cross-origin requests from the frontend.
- **Logging**: For detailed logging of errors and requests.

### Frontend
- **React.js**: For building the user interface.
- **Axios**: For handling API requests between the frontend and backend.

## Prerequisites

- Python 3.x
- SQLite
- Node.js (for the frontend)
- FastAPI dependencies (listed in `requirements.txt`)
- React (for frontend)

## Installation

### Backend Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Mahammadvalluru/Rule_Engine_API_Backend.git
   cd Rule_Engine_API_Backend
   ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Create a database: The database will be automatically created when you run the app for the first time.

4. Run the FastAPI application:
uvicorn main:app --reload

## Frontend Setup:
1. Clone the frontend repository:
```bash
git clone https://github.com/Mahammadvalluru/Rule_Engine_API_.git
cd Rule_Engine_API_ 
```

2. Install the frontend dependencies: 
```bash 
npm install 
```

3. Start the React application:
```bash
npm start
```

The frontend will run on http://localhost:3000 and will interact with the backend at http://localhost:8000.

## API Endpoints
#### Create a Rule
+ Endpoint: /create_rule
+ Method: POST
+ Payload:
```json
{
  "rule_string": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)"
}
```

### Evaluate a Rule
+ Endpoint: /evaluate_rule
+ Method: POST
+ Payload:
```json
{
  "rule_id": 1,
  "data": {
    "age": 32,
    "department": "Sales",
    "salary": 60000,
    "experience": 6
  }
}

```

### Combine Rules
+ Endpoint: /combine_rules
+ Method: POST
+ Payload:
```json
{
  "rule_ids": [1, 2],
  "condition": "and"
}

```

### Fetch All Rules
+ Endpoint:/rules
+ method:GET

## Project Structure
├── main.py            
├── requirements.txt   
├── rules.db             
└── README.md            

