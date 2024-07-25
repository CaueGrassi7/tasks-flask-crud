# Tasks Flask CRUD

This project is a simple CRUD (Create, Read, Update, Delete) application for managing tasks, built using Flask.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Endpoints](#endpoints)
- [Contributing](#contributing)

## Introduction

This Flask application provides functionalities for managing tasks. It includes endpoints to create, read, update, and delete tasks.

## Installation

### Requirements

- Python 3.7+
- MySQL

### Installation Steps

1. Clone the repository:
    ```sh
    git clone https://github.com/CaueGrassi7/tasks-flask-crud.git
    ```
2. Navigate to the project directory:
    ```sh
    cd tasks-flask-crud
    ```
3. Create a virtual environment:
    ```sh
    python -m venv venv
    ```
4. Activate the virtual environment:
    - On Windows:
        ```sh
        venv\Scripts\activate
        ```
    - On macOS/Linux:
        ```sh
        source venv/bin/activate
        ```
5. Install the dependencies:
    ```sh
    pip install -r requirements.txt
    ```
6. Configure the MySQL database connection string in the configuration file:
    ```python
    app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql+pymysql://user:password@host:port/database_name'
    ```
7. Run the application:
    ```sh
    python app.py
    ```

## Usage

The application will run at `http://127.0.0.1:5000/`.

### Endpoints

#### Create Task
- **URL:** `/tasks`
- **Method:** `POST`
- **Description:** Creates a new task.
- **Request Data:**
    ```json
    {
        "title": "Task Title",
        "description": "Task Description"
    }
    ```
- **Success Response:**
    ```json
    {
        "message": "Task created"
    }
    ```

#### Read Tasks
- **URL:** `/tasks`
- **Method:** `GET`
- **Description:** Retrieves all tasks.
- **Success Response:**
    ```json
    [
        {
            "id": 1,
            "title": "Task Title",
            "description": "Task Description"
        },
        ...
    ]
    ```

#### Read Task
- **URL:** `/tasks/<int:task_id>`
- **Method:** `GET`
- **Description:** Retrieves a task by ID.
- **Success Response:**
    ```json
    {
        "id": 1,
        "title": "Task Title",
        "description": "Task Description"
    }
    ```

#### Update Task
- **URL:** `/tasks/<int:task_id>`
- **Method:** `PUT`
- **Description:** Updates a task by ID.
- **Request Data:**
    ```json
    {
        "title": "Updated Title",
        "description": "Updated Description"
    }
    ```
- **Success Response:**
    ```json
    {
        "message": "Task updated"
    }
    ```

#### Delete Task
- **URL:** `/tasks/<int:task_id>`
- **Method:** `DELETE`
- **Description:** Deletes a task by ID.
- **Success Response:**
    ```json
    {
        "message": "Task deleted"
    }
    ```

## Contributing

Contributions are welcome! Follow the steps below to contribute:

1. Fork the project.
2. Create a branch for your feature or bugfix (`git checkout -b feature/new-feature`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature/new-feature`).
5. Open a Pull Request.
