# CLAUDE.md — Issue Tracker API

Ye file project ka single source of truth hai. Har feature ke baad isko update karna hai.

## Project kya hai

Ek Issue Tracker (bug tracker) web app: users issues bana sakte hain, unka status badal sakte hain, filter kar sakte hain, aur login ke baad apne issues manage kar sakte hain. Resume + deployment ke liye banaya ja raha hai.

## Tech stack

| Layer | Choice | Status |
|---|---|---|
| Backend | Django 6.1 + Django REST Framework | installed |
| Frontend | React | planned |
| Database | MySQL | planned (abhi Django ka default SQLite use ho raha hai) |
| Auth | JWT | planned |
| Testing | PyTest | planned |
| Deployment | Docker, phir cloud par deploy | planned |

## Folder structure

```
issue-tracker-api/
    manage.py
    requirements.txt
    config/        # project settings, urls
    issues/        # main app (models, views, serializers)
    venv/          # local only, git mein nahi
```

## Decisions (jo decide ho chuka hai)

- Project settings folder ka naam `config` hai (`django-admin startproject config .`).
- Main app ka naam `issues` hai.
- Practice code alag repo mein hai. Ye repo sirf clean project ke liye hai (resume par jayega).
- Status values ek fixed spelling/case mein rakhne hain (lowercase: `open`, `in_progress`, `closed`). Mixed case se filters miss hote hain.
- `.env` aur `db.sqlite3` git mein nahi jaate (`.gitignore` mein hain). `SECRET_KEY` deploy se pehle `.env` mein shift karni hai.

## Ab tak ban chuka hai

- [x] Virtual environment aur Django + DRF install
- [x] Django project `config` banaya
- [x] App `issues` banayi
- [x] `.gitignore` aur `requirements.txt`
- [x] Git repo banaya aur GitHub par push kiya

## Abhi ka kaam / aage ka plan

- [ ] `settings.py` ke `INSTALLED_APPS` mein `rest_framework` aur `issues` jodna
- [ ] `Issue` model banana (title, description, status, priority, created_at)
- [ ] Migrations chalana
- [ ] Serializer + API endpoints (list, create, update, delete)
- [ ] Filtering (status ke hisaab se)
- [ ] JWT login/register
- [ ] MySQL par shift karna
- [ ] PyTest tests
- [ ] React frontend
- [ ] Docker
- [ ] Deploy
- [ ] README (screenshots ke saath)

## Commands

```
venv\Scripts\activate
pip install -r requirements.txt
python manage.py runserver
python manage.py makemigrations
python manage.py migrate
```

## Working rules (Claude ke liye)

- Reply Hinglish mein.
- Ek baar mein ek hi step. Concept pehle samjhao, phir code.
- Har feature ke baad is file ka "ban chuka hai" aur "aage ka plan" section update karo aur updated hissa batao.
- Code user khud type karega; sirf skeleton ya hint do jab zaroori ho.
- Errors ko hint ki tarah treat karo: error padhna sikhao.
