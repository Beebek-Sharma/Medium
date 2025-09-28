# Medium

This is a Django-based blog application. It supports user registration, login, profile management, posting, and password reset via email.

## Features
- User registration and authentication
- Profile picture upload and resizing
- Create, update, and delete blog posts
- Password reset via email (Gmail SMTP supported)
- Responsive UI with Bootstrap 4 and crispy forms

## Requirements
- Python 3.13+
- Django 5.2+
- Pillow
- django-crispy-forms
- crispy-bootstrap4

## Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/Beebek-Sharma/Medium.git
cd Medium
```

### 2. Create and activate a virtual environment
```bash
python -m venv django
source django/Scripts/activate  # On Windows (bash)
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Set up environment variables (for email)
Set these in your system environment or a `.env` file:
- `DB_USER`: Your Gmail address
- `DB_PASS`: Your Gmail App Password
- `DB_MAIL`: Your Gmail address

#### Example for Windows (Command Prompt):
```
set DB_USER=your_email@gmail.com
set DB_PASS=your_app_password
set DB_MAIL=your_email@gmail.com
```

#### Example for bash:
```
export DB_USER=your_email@gmail.com
export DB_PASS=your_app_password
export DB_MAIL=your_email@gmail.com
```

### 5. Apply migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Create a superuser (admin)
```bash
python manage.py createsuperuser
```

### 7. Run the development server
```bash
python manage.py runserver
```

### 8. Access the app
- Visit `http://127.0.0.1:8000/` in your browser.
- Admin panel: `http://127.0.0.1:8000/admin/`

## Email Setup (Gmail)
- Enable 2-Step Verification in your Google account.
- Generate an App Password for "Mail" and use it for `DB_PASS`.
- Make sure your environment variables are set before running the server.

## Troubleshooting
- If you get `SMTPAuthenticationError`, double-check your Gmail address and App Password.
- If profile images or media do not display, ensure the `media/` folder exists and is writable.
- For missing profiles, run:
  ```bash
  python manage.py create_missing_profiles
  ```

## License
MIT
