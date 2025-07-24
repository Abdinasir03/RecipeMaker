# Recipe Search Application

A full-stack Flask application for searching and managing recipes using the Spoonacular API.

---

## Features

- **User authentication:** Register and log in to your account
- **Search 360,000+ recipes:** Powered by the Spoonacular Recipe API
- **Detailed recipe information:** View ingredients, instructions, and more
- **Personal dashboard:** Access your search history
- **Account management:** Update and manage your account

---

## Tech Stack

- **Backend:** Flask, SQLAlchemy, Flask-Login
- **Database:** SQLite
- **API:** [Spoonacular Recipe API](https://spoonacular.com/food-api)
- **Frontend:** Jinja2, Bootstrap 5

---

## Setup

### Prerequisites

- Python 3.12+
- Spoonacular API key ([Get your free key here](https://spoonacular.com/food-api))

### Installation

1. **Clone the repository**
    ```bash
    git clone https://github.com/Abdinasir03/recipe-search-app.git
    cd recipe-search-app
    ```

2. **Create and activate a virtual environment**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3. **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```

4. **Create a `.env` file** in the project root with the following content:
    ```
    SECRET_KEY=your-secret-key
    SQLALCHEMY_DATABASE_URI=sqlite:///recipes.db
    SPOONACULAR_API_KEY=your-api-key
    ```

5. **Initialize the database**
    ```bash
    flask db init
    flask db migrate -m "Initial migration"
    flask db upgrade
    ```

6. **Run the application**
    ```bash
    flask run
    ```

7. Visit [http://localhost:5000](http://localhost:5000) in your browser.

---

## API Endpoints

### Authentication

- `POST /api/register` — Create a new account
- `POST /api/login` — User login

### Recipes

- `POST /api/search` — Search recipes
- `GET /api/search/<recipe_id>` — Get recipe details

### User

- `GET /api/search_history` — View search history
- `DELETE /api/search_history/<item_id>` — Delete a search history item

---

## Project Structure

```
recipe-search-app/
├── app/
│   ├── models.py       # Database models
│   ├── routes.py       # API routes
│   └── templates/      # HTML templates
├── static/             # CSS, JS
├── requirements.txt
└── run.py
```

---

## License

This project is licensed under the MIT License.

---