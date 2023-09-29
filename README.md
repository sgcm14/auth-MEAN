Auth App
========
- Este proyecto se realizó siguiendo el curso [Angular: De cero a experto](https://www.udemy.com/course/angular-fernando-herrera/# "Angular: De cero a experto") 
> En este proyecto se usó Nest

  `POST` /auth/login

    REQUEST BODY:

     * email (required)
     * password (required)


Request Samples:

| Key           | Value                          |
| ------------- | ------------------------------ |
| `email`       | fernando@gooe.com              |
| `password`    | 123456                         |

Response samples:

    {
        "user": {
            "_id": "651389d9d89b35156ea801fb",
            "email": "fernando@gooe.com",
            "name": "fernando",
            "isActive": true,
            "roles": [
                "user"
            ],
            "__v": 0
        },
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY1MTM4OWQ5ZDg5YjM1MTU2ZWE4MDFmYiIsImlhdCI6MTY5NTk1NjI0NSwiZXhwIjoxNjk1OTc3ODQ1fQ.44g0exwFdxcX5TEdX4M-zJkHkUspZwtdP-MbI7KJHlo"
    }

Failed:

    {
        "message": "Not valid credentials - email",
        "error": "Unauthorized",
        "statusCode": 401
    }

    {
        "message": "Not valid credentials - password",
        "error": "Unauthorized",
        "statusCode": 401
    }

  `POST` /auth/register

    REQUEST BODY:

     * name (required)
     * email (required)
     * password (required)


Request Samples:

| Key           | Value                          |
| ------------- | ------------------------------ |
| `name`        | John Doe                       |
| `email`       | user1@email.com              |
| `password`    | 123456                         |

Response samples:

    {
    "user": {
        "email": "user1@email.com",
        "name": "John Doe",
        "isActive": true,
        "roles": [
            "user"
        ],
        "_id": "65163fef9a4fd0fcad9a1fd1",
        "__v": 0
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY1MTYzZmVmOWE0ZmQwZmNhZDlhMWZkMSIsImlhdCI6MTY5NTk1Njk3NSwiZXhwIjoxNjk1OTc4NTc1fQ.T3_eV6H-nxaqrSsx9Gree_tUIlUwm_-dnhZnq-CrMBM"
    }

Failed:

    {
      "message": "user1@email.com already exist!",
      "error": "Bad Request",
      "statusCode": 400
    }


`GET` /auth/check-token

    Authorization:

     * token (required)


Request Samples:

    Type (Bearer)
    Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY1MTYzZmVmOWE0ZmQwZmNhZDlhMWZkMSIsImlhdCI6MTY5NTk1Njk3NSwiZXhwIjoxNjk1OTc4NTc1fQ.T3_eV6H-nxaqrSsx9Gree_tUIlUwm_-dnhZnq-CrMBM

Response samples:

    {
      "user": {
          "_id": "65163fef9a4fd0fcad9a1fd1",
          "email": "user1@email.com",
          "name": "John Doe",
          "isActive": true,
          "roles": [
              "user"
          ],
          "__v": 0
      },
      "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY1MTYzZmVmOWE0ZmQwZmNhZDlhMWZkMSIsImlhdCI6MTY5NTk1NzU5MiwiZXhwIjoxNjk1OTc5MTkyfQ.YUBJcVIRY3_MlJb4ahhV7_Nu6gLNl18zmU8ADqvICls"
    }

Failed:

    {
      "message": "Unauthorized",
      "statusCode": 401
    }

    {
    "message": "There is no bearer token",
    "error": "Unauthorized",
    "statusCode": 401
}

En la siguiente captura se muestra la BD
![](https://github.com/sgcm14/auth-MEAN/blob/main/src/doc/Pantalla1.PNG)
> Pantalla de **BD**


**Realizado por :** Sammy Gigi Cantoral Montejo (sgcm14)

<img src ="https://raw.githubusercontent.com/sgcm14/sgcm14/main/sammy.jpg" width="200">
