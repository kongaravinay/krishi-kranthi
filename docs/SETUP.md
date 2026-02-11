# Setup Guide - KRISHI KRANTHI

Complete instructions for setting up the project locally for development.

## Prerequisites

Before you begin, make sure you have:

- **Python 3.9** or later (download from python.org)
- **MySQL 8.0** or later (installed and running)
- **Git** (for version control)
- **Text editor or IDE** (VS Code, PyCharm, etc.)
- **pip** (usually comes with Python)

## Installation Steps

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/krishi-kranthi.git
cd krishi-kranthi
```

### 2. Create Virtual Environment

A virtual environment keeps project dependencies isolated.

**On Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**On macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

You'll see `(venv)` prefix in your terminal when activated.

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

This installs Flask, MySQL connector, and other dependencies.

### 4. Set Up Environment Variables

Copy the example file and edit it:

```bash
cp .env.example .env
```

Edit `.env` with your database credentials:

```ini
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_NAME=krishikranthi
DB_PORT=3306

FLASK_ENV=development
FLASK_DEBUG=True
SECRET_KEY=your_secret_key_here

SERVER_HOST=0.0.0.0
SERVER_PORT=5000
```

### 5. Create MySQL Database

**Option A: Using MySQL CLI**

```bash
mysql -u root -p
```

Then run:

```sql
CREATE DATABASE krishikranthi CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
USE krishikranthi;
source database/schema.sql;
source database/seed_data.sql;
```

**Option B: Using MySQL Workbench**

1. Open MySQL Workbench
2. Create new schema: Right-click → Create Schema
3. Name it `krishikranthi`
4. Open both SQL files from `database/` folder
5. Execute them in order (schema first, then seed data)

### 6. Run the Application

```bash
python app/main.py
```

You should see:
```
 * Running on http://localhost:5000
 * Debug mode: on
```

Open your browser and go to `http://localhost:5000`

## Troubleshooting

### MySQL Connection Error

**Problem:** `Can't connect to MySQL server`

**Solution:**
- Check MySQL is running: `mysql --version`
- Verify credentials in `.env`
- Make sure database name is spelled correctly

### Port Already in Use

**Problem:** `Address already in use`

**Solution:**
- Change port in `.env`: `SERVER_PORT=5001`
- Or kill process using port 5000

### Import Errors

**Problem:** `ModuleNotFoundError: No module named 'flask'`

**Solution:**
- Activate virtual environment
- Run: `pip install -r requirements.txt` again

### Database Not Found

**Problem:** `Unknown database 'krishikranthi'`

**Solution:**
- Run the SQL schema file from step 5
- Or manually create database and tables

## Test Your Setup

Try these to verify everything works:

1. **Home page**: Visit `http://localhost:5000` - should load
2. **Farmer register**: Click "Register as Farmer" - should open form
3. **Consumer register**: Click "Register as Consumer" - should work

## Next Steps

- Read [README.md](../README.md) for project overview
- Check [CONTRIBUTING.md](../CONTRIBUTING.md) to start contributing
- Review [DATABASE.md](DATABASE.md) to understand data structure

## Need Help?

If you get stuck:

1. Check error messages carefully
2. Review this guide again
3. Check GitHub Issues
4. Ask on discussion forums

Enjoy developing!

---

**Last Updated:** February 2026
