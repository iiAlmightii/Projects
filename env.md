# =============================================================================
# AquaponicAI — Environment Variables Template
# Copy to .env and fill in your values. Never commit .env to git.
# =============================================================================

# ── App ──────────────────────────────────────────────────────────────────────
APP_NAME=AquaponicAI
ENVIRONMENT=development          # development | staging | production
DEBUG=false

# ── Security (CHANGE THESE IN PRODUCTION) ─────────────────────────────────────
SECRET_KEY=aab683e0b84c792640fcb2556b1d650197caf7e6bd5e5810005fea793f68e714
JWT_SECRET_KEY=fcc1cb4e78690bb30de3fbd7d79ce64af9cb70c648d9d327237d596877d36403
JWT_ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=60
REFRESH_TOKEN_EXPIRE_DAYS=7

# ── Database ──────────────────────────────────────────────────────────────────
#POSTGRES_PASSWORD=changeme_secure_password
# Supabase pooler URL — this is the active database connection.
# To update: Supabase dashboard → Project Settings → Database → Transaction pooler URI
# Convert prefix postgresql:// → postgresql+asyncpg:// and append the query params below.
DATABASE_URL=postgresql+asyncpg://postgres.iodggaldckguehuzoagm:-UQ8z_b%24%3F3%2CkEt%21@aws-1-ap-south-1.pooler.supabase.com:5432/postgres?ssl=require&prepared_statement_cache_size=0
SUPABASE_URL=https://iodggaldckguehuzoagm.supabase.co
SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImlvZGdnYWxkY2tndWVodXpvYWdtIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzU1NzYyNzgsImV4cCI6MjA5MTE1MjI3OH0.leoO3IYKg4CGgiy7sCepj8ZiZB30bGLQuAUZZ16OHtU
SUPABASE_SERVICE_ROLE_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImlvZGdnYWxkY2tndWVodXpvYWdtIiwicm9sZSI6InNlcnZpY2Vfcm9sZSIsImlhdCI6MTc3NTU3NjI3OCwiZXhwIjoyMDkxMTUyMjc4fQ.X4S4MjjiVe2jiDe9mWJq_WzlRuRp-9819Rl4dsEAGXQ


# ── Redis ─────────────────────────────────────────────────────────────────────
REDIS_URL=redis://default:gQAAAAAAAlVsAAIgcDJjYjQ4OGJlYzg1OWY0ZTBiOTNkYWRjMmUzNjczMGVjZQ@assuring-reptile-152940.upstash.io:6379

# ── CORS ─────────────────────────────────────────────────────────────────────
ALLOWED_ORIGINS=["http://localhost:3000","http://localhost:3001","http://localhost","http://127.0.0.1:3000","http://127.0.0.1:3001","https://localhost","https://127.0.0.1","https://localhost:3001","https://127.0.0.1:3001"]

# ── AI / LLM ─────────────────────────────────────────────────────────────────
ANTHROPIC_API_KEY=your_anthropic_key_here
OPENAI_API_KEY=your_openai_key_here
DEFAULT_LLM_PROVIDER=anthropic    # anthropic | openai | local
# Optional but recommended for faster Whisper model download and higher HF limits
# HF_TOKEN=hf_xxx

# ── Speech-to-Text ─────────────────────────────────────────────────────────────
STT_PROVIDER=whisper              # whisper | google | deepgram
FASTER_WHISPER_MODEL=medium.en
FASTER_WHISPER_DEVICE=cuda        # cpu | cuda
FASTER_WHISPER_COMPUTE_TYPE=int8_float16  # int8 | int8_float16 | float16

# ── Object Storage ────────────────────────────────────────────────────────────
STORAGE_BACKEND=local             # local | s3
LOCAL_STORAGE_PATH=./storage
# S3_BUCKET=your-bucket-name
# S3_REGION=ap-south-1
# AWS_ACCESS_KEY_ID=
# AWS_SECRET_ACCESS_KEY=

# ── External APIs ─────────────────────────────────────────────────────────────
WEATHER_API_KEY=your_openweathermap_key
MARKET_API_KEY=your_commodity_price_api_key

# ── Frontend (Vite) ───────────────────────────────────────────────────────────
VITE_API_URL=http://localhost:8000/api/v1

# ── Google Sheets Sync (Finance Planning) ──────────────────────────────────────
# Enable the optional Sheets sync UI/polling in the frontend:
VITE_GOOGLE_SHEETS_ENABLED=true

# Google Sheets credentials and spreadsheet id (service-account based).
# Set GOOGLE_SHEETS_SPREADSHEET_ID to the target spreadsheet.
GOOGLE_SHEETS_SPREADSHEET_ID=1aNaxRpfuo1xi50RzagoO5yFG5St_yI8iZPcitMZln18

# Option A (recommended): full service account JSON in one env var.
# GOOGLE_SHEETS_SERVICE_ACCOUNT_JSON='{"type":"service_account",...}'

# Option B: split env vars.
# GOOGLE_SHEETS_CLIENT_EMAIL=your_service_account_email@your_project.iam.gserviceaccount.com
# GOOGLE_SHEETS_PRIVATE_KEY="-----BEGIN PRIVATE KEY-----\n...\n-----END PRIVATE KEY-----\n"


GOOGLE_SHEETS_SERVICE_ACCOUNT_JSON='{"type":"service_account","project_id":"aquaponic-ai","private_key_id":"69d6b2d27d19e1b7e158584f8c72d0ab4c11bfaf","private_key":"-----BEGIN PRIVATE KEY-----\nMIIEvgIBADANBgkqhkiG9w0BAQEFAASCBKgwggSkAgEAAoIBAQDEY08+VG9L7kN1\ntow1c4XToFBV1xcZnEVbo1c84PD2fBqE6tu84Gsw9BBP2VDPQme647xMyAhOuVt+\n1m2JNALhpmIXniS3F7opjGqYMBZaWXJgHXUp5OTxIMZ0zVvfBti/WCtapQJ8j+RF\n7KY7GQ5eX83OJGdBTBI05/lh95EJWFKrrtuhxm/+UCetXstZrkb1d4dmnI/Qjesx\nmKiVsNicXhIq1OnhLIkMJxRxJOCQuGwIQe3d4yLTc1n+AJjs+xcNtzsS+eBpShTW\nQYxfhApn5QqHJMTWnJRWHEj+7sHQ51h+S9PWINHwsoKqbKN3mDEtrVgM8WBhIXhk\nlGUgF0TpAgMBAAECggEAJNDxRCAUFUn/f4vPUR3tErVVGiKOhBCVuA4xBoqs4ah2\nWECnHQt9TNoUTMPSsGgkhha3cDV3yTpaera8JiKH/8FvVjoha+mYzr0yJoGtTxbB\nqF8dXdM5UDLywWbWOENSUty2k/GnO67F/o3Uw/N4jBytul18tfMK3rw2NjVxDS0b\nVykmJV4l2ALWNTVf9MfDiXoOgEcNtt2DNTQb7uDP5xVRuwCrXVI2zFq4xBKDND7B\n3+3m46J3USZeYxtAxVB4MQEXr8E5YC90Qf5mjf9lgIJRVwnsfgZsUbXWduXyzvQh\nG7f2vpTNBgJys4Va4MJoC2RH9dOGSJ9Q5s0Uw3pg+QKBgQDxOTbflmC50STYnYfa\ngm/h38JgDFzHoQref20dzNHtnlfHNjfkPtXCLrjLEyjAtRzz+ilrv3PkdNbvx8bw\nyhhmlRGnTl1QJW+7hzzBoal9K9TZ6+kVTRmh/ACodStX46hU+8LR4zhGhVGv7BYq\n9Xp7qQt4oRR2HgwItWi6aeDE+wKBgQDQav+6u0DOLVJaMA/XqrNdmXIkrbBM6s76\nIuk3SssF/7Ut5wT9V2CRTYAuzfn49fIbBo64Aybg8hmR5Vg0uw0U36MFT31+RkCw\niu5xjVjKfx6crdW4dNKJKljM0lmRv21vx9uC6rVLZGNZuXX3sXjVBwWRsrfyzVKq\nG6Wcx/vQawKBgQCfQAhr/5kH030hzI4dwbMfSVvHkSHHYRgN384nuEp3Nuv4RmEL\nvDfepH23A4UKBAeDQooJ6jEWh9RGJHvAB4uoXY10CJYuDSkAgr2nj5SXYFJ7M/WC\n7I2ZlQbSL9hXg6JjyHnLmthSJj3RiGjyH3GnJei+0Ijzmc6UCT+EodWT9QKBgDdM\nvK/iMW7DTb+KUxnJPDBQn52lzEqMXwC1tKWsHbRoxbz5ODS0M3Y6VxGUK4hoUaXk\nFogypeU3t5sjfET5gJ4SPKITFlwj7dQp+Nx+QZnxIsE1yqhXrukgKFGoWoW2giYP\npGnXNuVbLJVJBUkEeOglJdAj2HT/D7j8/vNbiLAjAoGBAISdfLr22bufRwacC7qy\nrmo1jfpx1/rnOkx+cNAXao2QNXlxKeb6HdIMMi7JPq0QyYJuMj0Uc860qeQcCF7M\nr6+WmEe22+v2d//zY3rjPasGLeYl1wbv0PrRizTkGKw+MvDNvh9x44fiSFUokfNl\nhOdS0nB9q3dEUutt5UswG9V4\n-----END PRIVATE KEY-----\n","client_email":"aquaponic-ai-sheets@aquaponic-ai.iam.gserviceaccount.com","client_id":"105534517237962426145","auth_uri":"https://accounts.google.com/o/oauth2/auth","token_uri":"https://oauth2.googleapis.com/token","auth_provider_x509_cert_url":"https://www.googleapis.com/oauth2/v1/certs","client_x509_cert_url":"https://www.googleapis.com/robot/v1/metadata/x509/aquaponic-ai-sheets%40aquaponic-ai.iam.gserviceaccount.com","universe_domain":"googleapis.com"}'
#supabase pass = -UQ8z_b$?3,kEt!

DATA_GOV_IN_API_KEY=579b464db66ec23bdd000001199d989de3af4a4962f1b74903850a5a
# ── Evaluation Pipeline ───────────────────────────────────────────────────────
EVAL_MODE=true
SARVAM_API_KEY=sk_w3hmkl13_BcUvxuTXx9XudiebgzrvqaEs
