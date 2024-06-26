
# FlaskPostgresAPI

FlaskPostgresAPI is a simple RESTful API built using Flask and PostgreSQL. It allows you to perform CRUD (Create, Read, Update, Delete) operations on a database through HTTP requests.

## Installation

1. Clone this repository:
    ```
    git clone https://github.com/olusesa/FlaskPostgresAPI.git
    ```

2. Navigate into the project directory:
    ```
    cd FlaskPostgresAPI
    ```

3. Install the dependencies:
    ```
    pip install -r requirements.txt
    ```

4. Set up your PostgreSQL database and configure the connection details as environment variable.

5. Run the application:
    ```
    python main.py
    ```

By default, the application will run on `http://localhost:5000`.

## Endpoints

- **GET /**: Retrieve all users.
- **GET /search/user/<id>**: Retrieve a specific user by ID.
- **POST /add/user/<username>**: Create a new user.
- **PUT /update/user/<id>**: Update a user by ID.
- **PATCH /update/user/<id>**: Update a user entry by ID.
- **DELETE /delete/user/<id>**: Delete a user by ID.

## Request & Response Examples

### GET all ("/")

Request:
```
curl http://localhost:5000/
```

Response:
```
[
    {
        "id": #,
        "username": "<username>
        "name": "<name>",
        "email": "<email>",
        "phone": "<phone>"
    },
    {
        "id": #,
        "username": "<username>
        "name": "<name>",
        "email": "<email>",
        "phone": "<phone>"
    }
]
```

### GET /search/user/1

Request:
```
curl http://localhost:5000/1
```

Response:
```
{
        "id": 1,
        "username": "<username>
        "name": "<name>",
        "email": "<email>",
        "phone": "<phone>"
}
```

### POST /add/user/<username>

Request:
```
curl -X POST -H "Content-Type: application/json" -d '{"username":"<username>, "name": "New user name", "email": "New user email", "phone": "New user phone number"}' http://localhost:5000/add/user/<username>
```

Response:
```
{
        "id": "new user ID",
        "username": "<username>
        "name": "<name>",
        "email": "<email>",
        "phone": "<phone>"
}
```

### PATCH /update/user/3

Request:
```
curl -X PATCH -H "Content-Type: application/json" -d '{"name": "New Name", "Message": "name entry updated successfully"}' http://localhost:5000/update/user/3
```

Response:
```
{
        "id": 3,
        "username": "<username>
        "name": "<name>",
        "email": "<email>",
        "phone": "<phone>"
}
```

### DELETE /delete/user/3

Request:
```
curl -X DELETE http://localhost:5000/delete/user/3
```

Response:
```
{
    "message": "User with ID 3 has been deleted successfully"
}
```

## License

This project is licensed under the MIT License