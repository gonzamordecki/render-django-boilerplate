# Django Render Boilerplate

A production-ready Django boilerplate for quick deployment on Render.com.

## Features

- 🚀 Quick deployment on Render.com
- 🔒 Secure configuration with environment variables
- 📊 PostgreSQL database support for production + SQLite for local development
- 🗄️ WhiteNoise for static files serving
- 🌐 ASGI support with Uvicorn
- 🛠️ Debug mode auto-configuration

## Prerequisites

- Python 3.9+
- pip (Python package manager)
- A Render.com account

## Local Development

1. Clone the repository:
```bash
git clone https://github.com/gonzamordecki/render-django-boilerplate
cd render-django-boilerplate
```

2. Create a virtual environment (use at least python 3.9) and activate it:
```bash
python3.9 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Create a `.env` file in the root directory:
```bash
cp .env.example .env
```

5. Generate a new secret key and add it to your `.env` file:
```bash
python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"
```

6. Run migrations:
```bash
python manage.py migrate
```

7. Start the development server:
```bash
python manage.py runserver
```

Visit `http://localhost:8000` to see your app running.

## Deployment on Render

1. Go to render.yaml and change line 10 to your project name (i.e. 'my-django-app')

2. Go to [Render](https://render.com/) and create a new blueprint:
   - Connect your GitHub repository
   - Give the blueprint a name (i.e. 'my-django-app')
   - Click on "Deploy Blueprint"

3. Your service should be live! 🎉

Render will automatically:
- Create a PostgreSQL database
- Generate a secure SECRET_KEY
- Handle static files through WhiteNoise
- Set up HTTPS

## Project Structure

```
django-render-boilerplate/
├── main/                   # Project configuration
├── homepage/              # Main app
├── static/                # Static files
├── requirements.txt       # Python dependencies
├── build.sh              # Build script for Render
├── render.yaml           # Render configuration
└── .env.example          # Environment variables template
```

## Configuration

The project uses environment variables for configuration. Key settings:

- `DEBUG`: Automatically set based on the environment
- `SECRET_KEY`: Auto-generated in production
- `DATABASE_URL`: Automatically configured by Render
- `ALLOWED_HOSTS`: Configured for Render's domain

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Credits

Created by [Gonza Mordecki](https://github.com/gonzamordecki)
