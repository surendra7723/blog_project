# Django Blog Project

A full-featured blog application built with Django 4.1.7 that includes user authentication, CRUD operations for blog posts, and a clean, responsive interface.

## Features

- 📝 **Blog Management**: Create, read, update, and delete blog posts
- 👤 **User Authentication**: User registration, login, and logout functionality
- 🔐 **User Authorization**: Only authenticated users can create/edit posts
- 📱 **Responsive Design**: Mobile-friendly interface
- 🎨 **Clean UI**: Professional styling with CSS
- 🚀 **Production Ready**: Configured for deployment with Heroku

## Tech Stack

- **Backend**: Django 4.1.7
- **Database**: SQLite (development) / PostgreSQL (production)
- **Frontend**: HTML, CSS, Bootstrap
- **Deployment**: Heroku with Gunicorn and WhiteNoise
- **Python Version**: 3.11.1

## Project Structure

```
blog_project/
├── accounts/              # User authentication app
├── blog/                  # Main blog app
├── django_project/        # Project configuration
├── static/               # Static files (CSS, JS)
├── staticfiles/          # Collected static files
├── templates/            # HTML templates
├── db.sqlite3           # SQLite database
├── manage.py            # Django management script
├── requirements.txt     # Python dependencies
├── Procfile            # Heroku deployment config
├── runtime.txt         # Python version for Heroku
└── README.md           # Project documentation
```

## Installation & Setup

### Prerequisites

- Python 3.11.1 or higher
- pip (Python package manager)
- Git

### Local Development Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd blog_project
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run database migrations**
   ```bash
   python manage.py migrate
   ```

5. **Create a superuser (optional)**
   ```bash
   python manage.py createsuperuser
   ```

6. **Collect static files**
   ```bash
   python manage.py collectstatic
   ```

7. **Run the development server**
   ```bash
   python manage.py runserver
   ```

8. **Access the application**
   - Open your browser and navigate to `http://127.0.0.1:8000/`
   - Admin panel: `http://127.0.0.1:8000/admin/`

## Usage

### For Users

1. **Home Page**: View all published blog posts
2. **Sign Up**: Create a new user account
3. **Login**: Access your account
4. **Create Post**: Write and publish new blog posts (authenticated users only)
5. **Edit Post**: Modify your existing posts
6. **Delete Post**: Remove your posts
7. **View Post**: Read individual blog posts in detail

### For Administrators

- Access the Django admin panel at `/admin/`
- Manage users, posts, and site content
- Monitor user activity and content

## Key Components

### Models

- **Post Model** (`blog/models.py`):
  - Title (CharField)
  - Author (ForeignKey to User)
  - Body (TextField)
  - Automatic URL generation

### Views

- **BlogListView**: Display all blog posts
- **BlogDetailView**: Show individual post details
- **BlogCreateView**: Form for creating new posts
- **BlogUpdateView**: Form for editing existing posts
- **BlogDeleteView**: Confirm and delete posts

### Apps

1. **Blog App**: Core blogging functionality
2. **Accounts App**: User authentication and management

## Configuration

### Environment Variables

For production deployment, set the following environment variables:

- `SECRET_KEY`: Django secret key
- `DEBUG`: Set to `False` for production
- `ALLOWED_HOSTS`: Comma-separated list of allowed hosts
- `DATABASE_URL`: Database connection string (for PostgreSQL)

### Settings Highlights

- **Static Files**: Configured with WhiteNoise for production
- **Authentication**: Built-in Django authentication system
- **Security**: CSRF protection enabled
- **Middleware**: Security, sessions, and static file serving

## Deployment

### Heroku Deployment

The project is configured for Heroku deployment with:

- `Procfile`: Specifies web server command
- `runtime.txt`: Python version specification
- `requirements.txt`: Dependencies list
- WhiteNoise for static file serving

**Deployment Steps:**

1. Create a Heroku app
2. Set environment variables
3. Push to Heroku
4. Run migrations: `heroku run python manage.py migrate`
5. Create superuser: `heroku run python manage.py createsuperuser`

## Development

### Running Tests

```bash
python manage.py test
```

### Code Formatting

The project uses Black for code formatting:

```bash
black .
```

### Database Management

```bash
# Create migrations
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# Open Django shell
python manage.py shell
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## Dependencies

Key dependencies include:

- **Django 4.1.7**: Web framework
- **Gunicorn 20.1.0**: WSGI HTTP Server
- **WhiteNoise 6.4.0**: Static file serving
- **Black 23.3.0**: Code formatter

See `requirements.txt` for the complete list.

## License

This project is open source and available under the [MIT License](LICENSE).

## Support

If you encounter any issues or have questions:

1. Check the [Django documentation](https://docs.djangoproject.com/)
2. Search existing issues in the repository
3. Create a new issue with detailed information

## Acknowledgments

- Django framework and community
- Bootstrap for styling components
- Heroku for deployment platform

---

**Happy Blogging!** 🎉

For more information about Django development, visit the [official Django documentation](https://docs.djangoproject.com/).
