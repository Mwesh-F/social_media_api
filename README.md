# Social Media API

This project is a Django REST Framework-based Social Media API. It provides user authentication, profile management, and is ready for further social media features (posts, comments, follows, notifications, likes).

## Project Structure

```
social_media_api/
├── accounts/                # User authentication app
│   ├── admin.py
│   ├── apps.py
│   ├── migrations/
│   ├── models.py            # Custom user model
│   ├── serializers.py       # User serializer
│   ├── tests.py
│   ├── urls.py              # API routes for accounts
│   └── views.py             # Registration, login, profile views
├── manage.py
├── README.md
├── social_media_api/
│   ├── settings.py          # Project settings
│   ├── urls.py              # Main URL routing
│   └── ...
└── venv/                    # Virtual environment
```

## Setup Instructions

1. Clone the repository and navigate to the project directory.
2. Create and activate a virtual environment:
	```powershell
	python -m venv .venv
	.\.venv\Scripts\Activate
	```
3. Install dependencies:
	```powershell
	pip install django djangorestframework djangorestframework-simplejwt
	```
4. Apply migrations:
	```powershell
	python manage.py makemigrations
	python manage.py migrate
	```
5. Start the development server:
	```powershell
	python manage.py runserver
	```

## API Endpoints

### Registration
`POST /api/accounts/register/`

**Request Body:**
```json
{
  "username": "your_username",
  "email": "your_email@example.com",
  "password": "your_password"
}
```
**Response:** Returns authentication token on success.

### Login
`POST /api/accounts/login/`

**Request Body:**
```json
{
  "username": "your_username",
  "password": "your_password"
}
```
**Response:** Returns authentication token on success.

### User Profile
`GET /api/accounts/profile/` (Requires authentication)
`PUT /api/accounts/profile/` (Requires authentication)

**Request Body (PUT):**
```json
{
  "bio": "New bio",
  "profile_picture": "<image_url>"
}
```
**Response:** Returns updated user data.

## User Model

Custom user model extends Django's AbstractUser and includes:
- `bio`: Text field for user bio
- `profile_picture`: Image field for profile picture
- `followers`: ManyToMany field for user followers

## Testing

Use Postman, Insomnia, or cURL to test registration, login, and profile endpoints. Ensure tokens are generated and returned correctly.

## Next Steps

- Implement posts, comments, follows, notifications, and likes features.
- Deploy the API to a production environment.

## License

MIT

## Project Setup

1. Clone the repository and navigate to the project directory.
2. Create and activate a virtual environment:
	```powershell
	python -m venv .venv
	.\.venv\Scripts\Activate
	```
3. Install dependencies:
	```powershell
	pip install django djangorestframework djangorestframework-simplejwt
	```
4. Apply migrations:
	```powershell
	python manage.py makemigrations
	python manage.py migrate
	```
5. Start the development server:
	```powershell
	python manage.py runserver
	```

## User Registration & Authentication

### Register a User
POST `/api/accounts/register/`
Body (JSON):
```
{
  "username": "your_username",
  "email": "your_email@example.com",
  "password": "your_password"
}
```
Returns: Auth token on success.

### Login
POST `/api/accounts/login/`
Body (JSON):
```
{
  "username": "your_username",
  "password": "your_password"
}
```
Returns: Auth token on success.

### User Profile
GET/PUT `/api/accounts/profile/` (Requires authentication)

## User Model Overview

Custom user model extends Django's AbstractUser and includes:
- `bio`: Text field for user bio
- `profile_picture`: Image field for profile picture
- `followers`: ManyToMany field for user followers

## Notes
- All configuration files and migrations are included in the repository.
- Use tools like Postman to test registration and login endpoints.