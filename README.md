# api-connectors
## A lightweight framework for building reusable API --> Postgres connectors.  

### **This repo demonstrates:** 
- Pulling real-world data from multiple public APIs on a schedule
- Landing clean data into local and cloud SQL database
- Keeping the workflow incremental, idempotent, and observable.

### **Stack:** 
- Python (requests/httpx)
- SQLAlchemy, Postgres (local & Supabase) 
- .env for secrets, logging + retries, optional Docker.

### **Features:**
- Reusable connector template with clear extract → transform → load pattern
- Config & secrets management via .env
- Built-in retry logic with exponential backoff & jitter
- Idempotent UPSERTs using natural keys
- Incremental syncs with per-connector watermarks
- Centralized logging for progress, retries, and errors
- Version-controlled DDL in sql/

### **Example connectors:**
- *Open-Meteo* – no-auth hourly weather data, simple GET + pagination
- *GitHub REST* – personal token auth, rate limiting, incremental sync with updated_at cursor
- *Hacker News* – high fan-out/fan-in API calls, batching strategy

### **Deliverables:**
- connectors/ with per-API modules and shared utilities (http.py, db.py, util.py)
- DDL scripts under sql/
- A Makefile/justfile for repeatable runs

### This project teaches real-world data engineering skills: auth, pagination, retries, batching, schema design, and incremental loading.
