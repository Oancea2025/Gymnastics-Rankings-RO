
Gymnastics-Rankings — FINAL build 20250929-202111

1) Push codul in GitHub (acest folder).
2) In Render (Web Service):
   - Environment → set:
     DATABASE_URL = External Database URL din Postgres (poate fi 'postgresql://...'; codul il transforma in 'postgresql+psycopg://')
     FLASK_SECRET = o cheie random
     UPLOAD_PASSWORD = parola upload
   - Manual Deploy → Deploy latest commit (daca e nevoie: Clear build cache & deploy)
3) Test:
   - Upload CSV/XLSX cu header UPPERCASE:
     POSITION, COMPETITOR, CLUB, EXECUTION, ARTISTRY, DIFFICULTY, LINE PENALTY, CHAIR PENALTY, DIFF PENALTY, TOTAL
   - Restart service: datele raman (sunt in Postgres).

Note:
- Foloseste psycopg v3 (psycopg[binary]) compatibil cu Python 3.13.
- Procfile: 'web: gunicorn app:app'.
