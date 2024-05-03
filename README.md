Overview:

  This Django Blog Application provides a simple blogging platform with full CRUD functionalities for posts and the ability to comment on them. It uses Django and 
  Django REST Framework with token-based authentication.

Features:

  User registration, login, and logout.
  CRUD operations on blog posts.
  Ability to comment on posts.
  Token-based user authentication.
  
Technology Stack:

  Django
  Django REST Framework
  SQLite (default Django database)
  
Getting Started:

  These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

Prerequisites:

  You need to have Python installed on your machine. This application was built using Python 3.9. You also need pip to install the necessary packages.

Installation:

  Clone the repository
  git clone https://github.com/yourusername/django-blog-app.git
  cd django-blog-app
  Set up a virtual environment (Optional but recommended)
  python -m venv env
  source env/bin/activate  # On Windows use `env\Scripts\activate`
  Install required packages
  pip install -r requirements.txt
  Run migrations
  python manage.py migrate
  Create superuser (Optional for admin access)
  python manage.py createsuperuser
  Run the server
  python manage.py runserver
  
API Endpoints:

  User Registration: POST /register/
  User Login: POST /login/ - Returns a token upon successful login.
  User Logout: POST /logout/
  List/Create Posts: GET, POST /posts/
  Retrieve/Update/Delete Post: GET, PUT, PATCH, DELETE /posts/<int:pk>/
  List/Create Comments on Post: GET, POST /posts/<int:post_id>/comments/

Endpoints Examples:
1. User Registration: POST /register/
  Request Example:
'''
  {
    "username": "newuser",
    "email": "user@example.com",
    "password": "securepassword"
  }
  Response Example:

  {
    "token": "ab12cd34ef56gh78ij90kl"
```
3. User Login: POST /login/
  Request Example:

  {
    "username": "newuser",
    "password": "securepassword"
  }
  Response Example:

  {
    "token": "ab12cd34ef56gh78ij90kl"
  }
```
4. User Logout: POST /logout/
  Request Example:

  {
    "token": "ab12cd34ef56gh78ij90kl"
  }
  Response Example:

  {
    "detail": "Successfully logged out."
  }

5. List/Create Posts: GET, POST /posts/
  GET Request Example: (No body required for GET requests)
  GET Response Example:

  {
    "id": 2,
    "title": "New Post",
    "content": "Content of the new post.",
    "author": "newuser",
    "published_date": "2024-05-03T15:20:00Z"
  }

  POST Request Example:
  
  {
    "title": "New Post",
    "content": "Content of the new post.",
    "author": 1
  }
  POST Response Example:
  
  {
    "id": 2,
    "title": "New Post",
    "content": "Content of the new post.",
    "author": "newuser",
    "published_date": "2024-05-03T15:20:00Z"
  }
5. Retrieve/Update/Delete Post: GET, PUT, PATCH, DELETE /posts/<int:pk>/
  GET Request Example: (No body required)
  GET Response Example:
  
  {
    "id": 1,
    "title": "Sample Post",
    "content": "This is the content of the post.",
    "author": "newuser",
    "published_date": "2024-05-03T14:48:00Z"
  }
  PUT/PATCH Request Example:
  
  
  {
    "title": "Updated Title",
    "content": "Updated content of the post."
  }
  PUT/PATCH Response Example:
  
  {
    "id": 1,
    "title": "Updated Title",
    "content": "Updated content of the post.",
    "author": "newuser",
    "published_date": "2024-05-03T14:48:00Z"
  }
  
  DELETE Request Example: (No body required)
  DELETE Response Example:
  {
    "detail": "Post deleted successfully."
  }
  
6. List/Create Comments on Post: GET, POST /posts/<int:post_id>/comments/
  GET Request Example: (No body required)
  GET Response Example:
  
    {
      "id": 1,
      "post": 1,
      "author": "newuser",
      "text": "A comment on the post.",
      "created_date": "2024-05-03T16:00:00Z"
    }

  POST Request Example:
  
  {
    "text": "Another comment on the post.",
    "author": 1
  }
  POST Response Example:
  
  {
    "id": 2,
    "post": 1,
    "author": "newuser",
    "text": "Another comment on the post.",
    "created_date": "2024-05-03T16:05:00Z"
  }
