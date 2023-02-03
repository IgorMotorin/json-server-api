# JSON-server-api
Api for task "RS Clone".

## Setup and Running

- Use `node 14.x` or higher.
- Clone this repo: `$ git clone https://github.com/igormotorin/json-server-api.git`.
- Go to downloaded folder: `$ cd json-server-api`.
- Install dependencies: `$ npm install`.
- Start server: `$ npm start`.
- Now you can send requests to the address: `http://127.0.0.1:3000`.

## Usage

- **User**
    - [Register User](https://github.com/igormotorin/json-server-api#register-user)
    - [Login User](https://github.com/igormotorin/json-server-api#login-user)
    - [Get User](https://github.com/igormotorin/json-server-api#get-user)
    - [Update User](https://github.com/igormotorin/json-server-api#update-user)
    - [Delete User](https://github.com/igormotorin/json-server-api#delete-user)

- **Settings**
    - [Set settings User](https://github.com/igormotorin/json-server-api#set-settings-user)
    - [Get all settings user](https://github.com/igormotorin/json-server-api#get-all-settings-user)
    - [Update settings user](https://github.com/igormotorin/json-server-api#update-settings-user)
    - [Delete settings user](https://github.com/igormotorin/json-server-api#delete-settings-user)
    

- **Transactions**
    - [Set transactions User](https://github.com/igormotorin/json-server-api#set-transactions-user)
    - [Get all transactions user](https://github.com/igormotorin/json-server-api#get-all-transactions-user)
    - [Update transactions user](https://github.com/igormotorin/json-server-api#update-transactions-user)
    - [Delete transactions user](https://github.com/igormotorin/json-server-api#delete-transactions-user)



**Register User**
----
Register a new user.

<details>

* **URL**

    /register

* **Method:**

    `POST`

* **Headers:**

    `'Content-Type': 'application/json'`

*  **URL Params**

    None

* **Query Params**

    None

* **Data Params**

    ```typescript
      {
        email: string,
        password: string
      }
    ```

* **Success Response:**

  * **Code:** 201 CREATED <br />
    **Content:** 
    ```json
      {
        "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXJAbWFpbC5jb20iLCJpYXQiOjE2NzU0MDAyMDEsImV4cCI6MTY3NTQwMzgwMSwic3ViIjoiMyJ9.rb6HiOz3JLsY8JUNovCE6vTjtBBXBQiC80Ru7_ADcl4",
        "user": {
            "email": "olivier@mail.com",
            "id": 3
        }
    }
    ```
 
* **Error Response:**

   * **Code:** 400 Bad Request <br />
    **Content:** 
    `"Email and password are required"`

    * **Code:** 400 Bad Request <br />
    **Content:** 
    `"Email already exists"`



* **Notes:**

    None

</details>


**Login User**
----
Login user.

<details>

* **URL**

    /login

* **Method:**

    `POST`

* **Headers:**

    `'Content-Type': 'application/json'`

*  **URL Params**

    None

* **Query Params**

    None

* **Data Params**

    ```typescript
      {
        email: string,
        password: string
      }
    ```

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
      {
        "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXJAbWFpbC5jb20iLCJpYXQiOjE2NzU0MDAyMDEsImV4cCI6MTY3NTQwMzgwMSwic3ViIjoiMyJ9.rb6HiOz3JLsY8JUNovCE6vTjtBBXBQiC80Ru7_ADcl4",
        "user": {
            "email": "olivier@mail.com",
            "id": 3
        }
    }
    ```
 
* **Error Response:**

   * **Code:** 400 Bad Request <br />
    **Content:** 
    `"Cannot find user"`

    * **Code:** 400 Bad Request <br />
    **Content:** 
    `"Incorrect password"`

    * **Code:** 400 Bad Request <br />
    **Content:** 
    `"Email and password are required"`


* **Notes:**

    None

</details>



**Get User**
----
Get user data

<details>

* **URL**

    /users/:id

* **Method:**

    `GET`

* **Headers:**
   
    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

    **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    None

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
      {
        "email": "olivier12@mail.com",
        "password": "$2a$10$dvRIbUcWuFkuY/gJsi5fAORBJ9DsHmSOLawKzT4Rzf7C6mon/cwWe",
        "id": 1
     }
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource replacement: request body must have a reference to the owner id"`

* **Notes:**

    None

</details>


**Update User**
----
Update user data

<details>

* **URL**

    /users/:id

* **Method:**

    `PUT`

* **Headers:**

    `'Content-Type': 'application/json'`
    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

    **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

   ```typescript
      {
        email: string,
        password: string
      }
    ```

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
      {
        "email": "olivier12@mail.com",
        "password": "$2a$10$dvRIbUcWuFkuY/gJsi5fAORBJ9DsHmSOLawKzT4Rzf7C6mon/cwWe",
        "id": 1
     }
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource replacement: request body must have a reference to the owner id"`

* **Notes:**

    None

</details>



**Delete User**
----
Delete user

<details>

* **URL**

    /users/:id

* **Method:**

    `DELETE`

* **Headers:**
    
    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

    **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    None

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
      {}
    ```
 
* **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    `"Cannot read properties of undefined (reading 'id')"`

* **Notes:**

    None

</details>




**Set settings user**
----
Set settings user (id = user id).

<details>

* **URL**

    /users/:id/settings

* **Method:**

    `POST`

* **Headers:**

    `'Content-Type': 'application/json'`

    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

    **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    ```typescript
    {
    "lang": "en",
    "theme": "black",
    "currency": "usd",
    "userId": 3    
    }
    ```

* **Success Response:**

  * **Code:** 201 Created <br />
    **Content:** 
    ```json
      {
    "lang": "en",
    "theme": "black",
    "currency": "usd",
    "userId": 3,
    "id": 7
    }
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource creation: request body must have a reference to the owner id"`

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    `"invalid token"`

* **Notes:**

    None

</details>



**Get all settings user**
----
Get all settings user (id = user id).

<details>

* **URL**

    /user/:id/settings

* **Method:**

    `GET`

* **Headers:**
    
    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

     **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    none

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
      [
    {
        "lang": "en",
        "theme": "dddd",
        "currency": "usd",
        "userId": "3",
        "id": 6
    },
    {
        "lang": "en",
        "theme": "rrrrr",
        "currency": "usd",
        "userId": 3,
        "id": 7
    },
    {
        "lang": "en",
        "theme": "rrrrr",
        "currency": "usd",
        "userId": 3,
        "id": 8
    }
    ]
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource creation: request body must have a reference to the owner id"`

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    `"invalid token"`

* **Notes:**

    None

</details>



**Update settings user**
----
Update settings user (id = setting id).

<details>

* **URL**

    /settings/:id

* **Method:**

    `PUT`

* **Headers:**

    `'Content-Type': 'application/json'`

    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

   **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    ```typescript
      {
        "lang": "en",
        "theme": "black",
        "currency": "usd",
        "userId": 3
    }
    ```

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
      {
    "lang": "en",
    "theme": "black",
    "currency": "usd",
    "userId": 3,
    "id": 7
    }
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource creation: request body must have a reference to the owner id"`

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    `"invalid token"`

* **Notes:**

    None

</details>




**Delete settings user**
----
Delete settings user (id = setting id).

<details>

* **URL**

    /settings/:id

* **Method:**

    `DELETE`

* **Headers:**
    

    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

    
   **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    None

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
      {}
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource creation: request body must have a reference to the owner id"`

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    `"invalid token"`

* **Notes:**

    None

</details>




**Set transactions user**
----
Set transactions user (id = user id).

<details>

* **URL**

    /users/:id/transactions

* **Method:**

    `POST`

* **Headers:**

    `'Content-Type': 'application/json'`

    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

    **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    ```typescript
    {
        "type": "expense",
        "category": "mobile",
        "subcategory": "tele2",
        "description": "апрель",
        "data": "1",
        "time": "1",
        "sum": 100,      
        "userId": 3
    }
    ```

* **Success Response:**

  * **Code:** 201 Created <br />
    **Content:** 
    ```json
      {
        "type": "expense",
        "category": "mobile",
        "subcategory": "tele2",
        "description": "апрель",
        "data": "1",
        "time": "1",
        "sum": 100,
        "userId": "3",
        "id": 3
    }
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource creation: request body must have a reference to the owner id"`

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    `"invalid token"`

* **Notes:**

    None

</details>



**Get all transactions user**
----
Get all transactions user (id = user id).

<details>

* **URL**

    /user/:id/transactions

* **Method:**

    `GET`

* **Headers:**
    
    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

     **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    none

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
      [
        {
            "type": "expense",
            "category": "mobile",
            "subcategory": "tele2",
            "description": "апрель",
            "data": "1",
            "time": "1",
            "sum": 100,
            "userId": "3",
            "id": 3
        }
    ]
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource creation: request body must have a reference to the owner id"`

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    `"invalid token"`

* **Notes:**

    None

</details>



**Update transactions user**
----
Update transactions user (id = transaction id).

<details>

* **URL**

    /transactions/:id

* **Method:**

    `PUT`

* **Headers:**

    `'Content-Type': 'application/json'`

    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

   **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    ```typescript
    {
        "type": "expense111",
        "category": "mobile",
        "subcategory": "tele2",
        "description": "апрель",
        "data": "1",
        "time": "1",
        "sum": 100,      
        "userId": 3
    }
    ```

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
    {
        "type": "expense111",
        "category": "mobile",
        "subcategory": "tele2",
        "description": "апрель",
        "data": "1",
        "time": "1",
        "sum": 100,
        "userId": 3,
        "id": 3
    }
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource creation: request body must have a reference to the owner id"`

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    `"invalid token"`

* **Notes:**

    None

</details>




**Delete transactions user**
----
Delete transactions user (id = transactions id).

<details>

* **URL**

    /transactions/:id

* **Method:**

    `DELETE`

* **Headers:**
    

    `'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXIxQG1haWwuY29tIiwiaWF0IjoxNjc1NDAyMjM1LCJleHAiOjE2NzU0MDU4MzUsInN1YiI6IjEifQ.V_lNh4EXi2DtVcOD7UDrZblxFFmYeoEufxshsLIJ_ik'`

*  **URL Params**

    **Required:**
 
    `id=[integer]`

* **Query Params**

    None

* **Data Params**

    None

* **Success Response:**

  * **Code:** 200 OK <br />
    **Content:** 
    ```json
      {}
    ```
 
* **Error Response:**

  * **Code:** 403 Forbidden <br />
    **Content:** 
    `"Private resource creation: request body must have a reference to the owner id"`

  * **Code:** 401 Unauthorized <br />
    **Content:** 
    `"invalid token"`

* **Notes:**

    None

</details>