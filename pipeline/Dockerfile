FROM python:3.13.11
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin

WORKDIR /code

# 1. Fichiers de configuration
COPY pyproject.toml .python-version uv.lock ./

# 2. Synchronisation de l'environnement virtuel
RUN uv sync --locked

# 3. Copie du script
COPY pipeline.py .

ENTRYPOINT ["uv", "run", "python", "pipeline.py"]