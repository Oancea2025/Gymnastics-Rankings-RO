
Gymnastics-Rankings — FINAL FIX build 20250929-203109

1) Push codul in GitHub (continutul acestui ZIP).
2) In Render (Web Service):
   - Environment → set:
     DATABASE_URL = External Database URL din Postgres (poate fi 'postgresql://...'; codul il transforma in 'postgresql+psycopg://')
     FLASK_SECRET = o cheie random (ex. 32 caractere)
     UPLOAD_PASSWORD = parola pentru upload
   - Manual Deploy → Clear build cache & deploy (recomandat la trecerea pe psycopg v3)
3) Test:
   - Upload CSV/XLSX cu header UPPERCASE:
     POSITION, COMPETITOR, CLUB, EXECUTION, ARTISTRY, DIFFICULTY, LINE PENALTY, CHAIR PENALTY, DIFF PENALTY, TOTAL
   - Restart service: datele raman (sunt in Postgres).

Pachete principale (requirements.txt):
- Flask, SQLAlchemy, openpyxl, psycopg[binary]>=3.1, gunicorn

Procfile:
web: gunicorn app:app
