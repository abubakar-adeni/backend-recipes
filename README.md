<h1 align="center">backend-recipes</h1>

# Pijar Camp Backend - Tugas

Backend API for RecipesApp and Recipes Web.
RecipesApp is an Android app designed to exchange and discover recipes for cooking various dishes. It enables users to share recipes, along with detailed ingredient and cooking instructions.

By Abubakar Adeni

## Built with

- NodeJS
- ExpressJS
- PostgreSQL

## Packages used

- "argon2": "^0.30.3"
- "cloudinary": "^1.34.0"
- "cors": "^2.8.5"
- "dotenv": "^16.0.3"
- "express": "^4.18.2"
- "helmet": "^6.0.1"
- "jsonwebtoken": "^9.0.0"
- "multer": "^1.4.5-lts.1"
- "nodemailer": "^6.9.1"
- "pg": "^8.9.0"
- "uuid": "^9.0.0"
- "xss-clean": "^0.1.1"

## Features

- CRUD
- Sort, Pagination -> http://localhost:4000/recipe?sortby=created_at&sort=desc&page=1&limit=10
- Search by field -> http://localhost:4000/recipe?search=nasi
- Error Handling
- Upload and filter file/photo
- User registration with email verification
- Private routes

## .env example

```
DB_USER=
DB_PASS=
DB_PORT=
DB_HOST=
DB_NAME=

JWT_ACCESS_KEY=
JWT_REFRESH_KEY=

EMAIL_NAME=
EMAIL_PASSWORD=

BASE_URL=
PORT=

PHOTO_NAME=
PHOTO_KEY=
PHOTO_SECRET=
```

## API Reference

### Register user
```http
  POST /auth/register/user
```
Req Body Form: 
| Key | Value |
| :-------- |:------------------------- |
| `email` | **Required**. email |
| `name` | **Required**. name |
| `password` | **Required**. password |

### Login user
```http
  POST /auth/login
```
Req Body Form: 
| Key | Value |
| :-------- |:------------------------- |
| `email` | **Required**. email |
| `password` | **Required**. password |

### Verify Users OTP
```http
  POST /auth/otp/:id/:code
```

### Get All Recipes
```http
  GET /recipes/
```
Auth:
|Key |Value                |
| :-------- |:------------------------- |
| `bearer token` |**Required**. Login accessToken |

Query Params: 
| Key | Description | Default Value
| :-------- | :------------------------- | :-------- |
| `search` | search query  |null
| `searchBy` | search category |title
| `sortBy`| sort category |created_at
| `sort`| sort query |asc

### Get Users Recipes
```http
  GET /recipes/my-recipe
```
Auth:
|Key |Value                |
| :-------- |:------------------------- |
| `bearer token` |**Required**. Login accessToken |

### Get Recipe by Id
```http
  GET /recipes/:id
```
Auth:
|Key |Value                |
| :-------- |:------------------------- |
| `bearer token` |**Required**. Login accessToken |

### Insert Recipe

```http
  POST /recipes
```
Auth:
|Key |Value                |
| :-------- |:------------------------- |
| `bearer token` |**Required**. Login accessToken |

Req Body Form: 
| Key | Value |
| :-------- |:------------------------- |
| `title` | **Required**. Nasi Goreng |
| `ingredients` | **Required**. Nasi, Bawang, Garam, Mentega |
| `photo` | **Required**. image png / jpg |
| `categories_id` | **Required**. integer|

### Update Recipe

```http
  PUT /recipes
```
Auth:
|Key |Value                |
| :-------- |:------------------------- |
| `bearer token` |**Required**. Login accessToken |

Req Body Form: 
| Key | Value |
| :-------- |:------------------------- |
| `title` | **Required**. Nasi Goreng |
| `ingredients` | **Required**. Nasi, Bawang, Garam, Mentega |
| `photo` | **Required**. image png / jpg |
| `categories_id` | **Required**. integer|

### Delete Recipe

```http
  DELETE /recipes/:id
```
Auth:
|Key |Value                |
| :-------- |:------------------------- |
| `bearer token` |**Required**. Login accessToken |



## Postman

[![Run in Postman](https://run.pstmn.io/button.svg)](https://www.postman.com/galactic-astronaut-447626/workspace/food-recipe/collection/27256896-d2f0654d-d29c-4cc3-839e-7df96dc290a5?action=share&creator=27256896)



# Related Project

:rocket: [`Frontend Food Recipe (Website)`](https://github.com/abubakar-adeni/food-recipev1)

:rocket: [`Frontend Food Recipe (App)`](https://github.com/abubakar-adeni/foodNative)

:rocket: [`Backend Food Recipe`](https://github.com/abubakar-adeni/backend-recipes)

:rocket: [`Release APK`](https://github.com/abubakar-adeni/foodNative/tree/main/release)
