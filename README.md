# Recept Creator


A modern recipe management web application built with Python, FastAPI, and modern frontend technologies.


## Features

- Create, read, update, and delete recipes
- Categorize recipes by cuisine, meal type, dietary restrictions
- Search and filter recipes
- Ingredient management with quantities and units
- Step-by-step cooking instructions
- Responsive web UI


## Tech Stack

- **Backend**: Python 3.11+, FastAPI
- **Database**: SQLite (dev) / PostgreSQL (prod)
- **ORM**: SQLAlchemy 2.0 (async)
- **Validation**: Pydantic v2
- **Frontend**: Jinja2 templates + HTMX + Tailwind CSS
- **Testing**: pytest, httpx
- **Code Quality**: Ruff, MyPy
- **Containerization**: Docker, Docker Compose


## Quick Start


### Prerequisites

- Python 3.11+
- Git
- Docker (optional, for PostgreSQL)


### Local Development

```bash
# Clone and enter
 git clone https://github.com/nikkig-entr/recept-creator.git
 cd recept-creator

# Create virtual environment
 python -m venv .venv
 source .venv/bin/activate  # Windows: .venv\Scripts\activate

# Install dependencies
 pip install -U pip
 pip install -e ".[dev]"

# Copy environment config
 cp .env.example .env

# Run database migrations (when implemented)
 # alembic upgrade head

# Start development server
 uvicorn app.main:app --reload
```


### With Docker

```bash
# Start all services
 docker compose up --build

# Access at http://localhost:8000
```


## Project Structure

```
recept-creator/
├── app/
│   ├── __init__.py
│   ├── main.py              # FastAPI app factory
│   ├── config.py            # Settings (Pydantic)
│   ├── database.py          # SQLAlchemy setup
│   ├── models/              # SQLAlchemy models
│   ├── schemas/             # Pydantic schemas
│   ├── api/                 # API routes
│   ├── services/            # Business logic
│   ├── templates/           # Jinja2 templates
│   └── static/              # Static assets
├── tests/
├── alembic/                 # Migrations
├── docker/
├── .github/workflows/       # CI/CD
├── pyproject.toml
├── .env.example
├── docker-compose.yml
└── README.md
```


## API Endpoints (Planned)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | /recipes | List all recipes |
| POST   | /recipes | Create new recipe |
| GET    | /recipes/{id} | Get recipe by ID |
| PUT    | /recipes/{id} | Update recipe |
| DELETE | /recipes/{id} | Delete recipe |
| GET    | /categories | List categories |


## Development

```bash
# Run tests
 pytest -v

# Run with coverage
 pytest --cov=app --cov-report=html

# Lint
 ruff check .
 ruff format .

# Type check
 mypy app/
```


## Environment Variables

See `.env.example` for all available options:

| Variable | Default | Description |
|----------|---------|-------------|
| DATABASE_URL | sqlite+aiosqlite:///./recipes.db | Database connection string |
| SECRET_KEY | (required) | Secret key for sessions |
| DEBUG | true | Debug mode |


## License

MIT


---

*Early-stage project — active development in progress*
