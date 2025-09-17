# Copilot Instructions for microblog

## Project Overview
- This is a Flask-based microblogging application with a modular structure.
- Main entry point: `microblog.py` (creates and runs the app).
- Application code is in the `app/` directory, organized by feature:
  - `models.py`: SQLAlchemy models (User, Post, etc.)
  - `routes.py`: Flask routes/views
  - `forms.py`: WTForms form classes
  - `errors.py`: Error handlers
  - `__init__.py`: App factory, extension initialization
  - `templates/`: Jinja2 HTML templates
- Database migrations are managed with Alembic in the `migrations/` folder.
- Logs are written to `logs/microblog.log`.

## Key Workflows
- **Run the app:** `python microblog.py` (uses `config.py` for settings)
- **Database migrations:**
  - `flask db init` (once), `flask db migrate -m "msg"`, `flask db upgrade`
- **Testing:** No explicit test suite found; add tests in a `tests/` folder if needed.
- **Debugging:** Use Flask's built-in debugger; errors are logged in `logs/`.

## Project Conventions
- Models use SQLAlchemy and are defined in `app/models.py`.
- User authentication and profile logic are in `app/routes.py` and `app/models.py`.
- Forms are defined in `app/forms.py` and rendered in templates.
- Templates use Jinja2 and are stored in `app/templates/`.
- Error handling is centralized in `app/errors.py`.
- Configuration is loaded from `config.py`.

## Integration Points
- Uses Flask, Flask-SQLAlchemy, Flask-Migrate, Flask-Login, WTForms.
- Database: SQLite by default (`app.db`), can be changed in `config.py`.
- Migrations: Alembic scripts in `migrations/versions/`.

## Examples
- To add a new model, update `app/models.py` and create a migration.
- To add a new route, define it in `app/routes.py` and add a template if needed.
- To customize error pages, edit `app/templates/404.html` or `500.html`.

## Special Notes
- Do not edit files in `__pycache__/` or `migrations/versions/` directly.
- Follow the existing structure for new features (model, form, route, template).
- Keep configuration and secrets out of version control.

---
For more details, see `config.py`, `app/__init__.py`, and the structure in `app/`.
