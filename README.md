# SpendSmart – Personal Finance Tracker

A Django-based personal finance tracker for managing income, expenses, savings goals, and generating reports with AI-powered expense forecasting.

## Features

- **Dashboard** – Daily, weekly, monthly, and yearly income overview with charts
- **Expense Tracking** – Log, categorize, search, sort, and paginate expenses
- **Income Tracking** – Record income from multiple sources
- **Expense Forecast** – 30-day ML-based expense prediction
- **Goals** – Set savings targets and track progress with progress bars
- **Reports** – Generate income-expense reports for any date range with PDF export
- **Currency Preferences** – Support for multiple currencies
- **User Authentication** – Register, login, and manage your account

## Tech Stack

- **Backend**: Django 5.1, Django REST Framework
- **Database**: SQLite (dev) / MySQL (prod)
- **ML**: scikit-learn, statsmodels, pandas, numpy
- **PDF**: xhtml2pdf / reportlab
- **Frontend**: Custom CSS (Inter font, dark sidebar, responsive grid)

## Getting Started

### Prerequisites
- Python 3.10+
- pip

### Installation

```bash
# Clone the repo
git clone https://github.com/<your-username>/SpendSmart.git
cd SpendSmart

# Create virtual environment
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Download NLTK data (for forecast feature)
python nltk_downloader.py

# Apply migrations
python manage.py migrate

# Create superuser (optional)
python manage.py createsuperuser

# Run the server
python manage.py runserver
```

Visit `http://127.0.0.1:8000` and register an account to get started.

## Environment Variables

Create a `.env` file for production settings:

```
SECRET_KEY=your-secret-key-here
DEBUG=False
ALLOWED_HOSTS=yourdomain.com
DATABASE_URL=mysql://user:password@host/dbname
```

## Project Structure

```
SpendSmart/
├── authentication/     # Login, register, logout
├── expenses/           # Expense CRUD + search
├── userincome/         # Income CRUD + search
├── expense_forecast/   # ML-based 30-day forecast
├── goals/              # Savings goals tracker
├── report_generation/  # PDF report generation
├── userpreferences/    # Currency & limit settings
├── userprofile/        # Account + income sources
├── api/                # REST API endpoints
├── static/             # CSS, JS, images
│   └── css/theme.css   # Main design system
└── templates/          # Django HTML templates
```

## License

MIT License – see [LICENSE](LICENSE) for details.
