# Django Blogging System

A full-stack blogging platform built with **Django** by **Rajarshi Roy**. The application provides public blog browsing together with authentication, search, comments, media uploads, and a dashboard for managing posts, categories, and users.

## Overview

This project demonstrates a traditional server-rendered Django architecture with reusable apps, Django ORM models, template-based views, authentication, form handling, image uploads, and administrative content-management workflows.

The application is organized around three main areas:

- **Public blog** — browse published posts, featured posts, categories, individual articles, and search results.
- **Authentication** — user registration, login, and logout using Django's built-in authentication system.
- **Management dashboard** — create, edit, and delete categories, blog posts, and users.

## Features

- User registration, login, and logout
- Published and draft blog-post workflow
- Featured blog posts
- Category-based post filtering
- Full-text-style search across title, short description, and blog body
- Individual blog pages with unique slugs
- Blog comments
- Featured-image uploads
- Category CRUD operations
- Blog-post CRUD operations
- User CRUD operations
- Django Groups and Permissions available through dashboard user management
- Dashboard statistics for total categories and blog posts
- Configurable About section and social links
- Django admin integration
- Custom 404 template

## Tech Stack

| Area | Technology |
| --- | --- |
| Backend | Python, Django |
| Database | SQLite |
| ORM | Django ORM |
| Frontend | Django Templates, HTML, CSS |
| Forms/UI | Django Forms, django-crispy-forms, Crispy Bootstrap 4 |
| Authentication | Django Authentication |
| Image Handling | Pillow, Django Media Files |

## Application Structure

```text
blogging-system-yt-main/
├── assignments/          # About and social-link models
├── blog_main/            # Django project settings, root URLs and auth/home views
├── blogs/                # Blog, category and comment domain logic
├── dashboards/           # Dashboard forms, routes and CRUD views
├── media/                # Uploaded media files
├── templates/            # Public and dashboard Django templates
├── db.sqlite3            # Development SQLite database
├── manage.py             # Django management entry point
└── requirements.txt      # Python dependencies
```

## Core Data Model

### Category
Stores unique blog categories and timestamps.

### Blog
Stores the main article content, including:

- title and unique slug
- category
- author
- featured image
- short description
- blog body
- `Draft` / `Published` status
- featured-post flag
- created and updated timestamps

### Comment
Associates a user comment with a specific blog post.

### About and SocialLink
Provide editable site information and social-media links.

## Main Routes

| Route | Purpose |
| --- | --- |
| `/` | Home page with featured and published posts |
| `/blogs/<slug>/` | Individual blog post |
| `/category/...` | Posts by category |
| `/search/` | Blog search |
| `/register/` | User registration |
| `/login/` | Login |
| `/logout/` | Logout |
| `/dashboard/` | Management dashboard |
| `/dashboard/categories/` | Category management |
| `/dashboard/posts/` | Blog-post management |
| `/dashboard/users/` | User management |
| `/admin/` | Django admin |

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/rajarshi700/blogging-system-yt-main.git
cd blogging-system-yt-main
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv
```

**Windows**

```bash
venv\Scripts\activate
```

**macOS / Linux**

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

The project currently uses Django, Pillow, `django-crispy-forms`, and `crispy-bootstrap4`.

### 4. Apply database migrations

```bash
python manage.py migrate
```

### 5. Create an admin user

```bash
python manage.py createsuperuser
```

### 6. Run the development server

```bash
python manage.py runserver
```

Open `http://127.0.0.1:8000/` in your browser.

## How the Application Works

```text
User Request
    │
    ▼
Django URL Router
    │
    ▼
Views / Forms
    │
    ├── Authentication
    ├── Blog & Category Logic
    ├── Search & Comments
    └── Dashboard CRUD
    │
    ▼
Django ORM
    │
    ▼
SQLite Database
    │
    ▼
Django Templates + Media
    │
    ▼
Rendered HTML Response
```

## Development Notes

This repository is currently configured for local development with SQLite. Before using it in production, move sensitive settings such as `SECRET_KEY` to environment variables, disable Django debug mode, configure `ALLOWED_HOSTS`, use appropriate production static/media handling, and review authorization on management routes.

## Author

**Rajarshi Roy**

- GitHub: [@rajarshi700](https://github.com/rajarshi700)

---

If you find the project useful, consider starring the repository.