FROM python:3.11-slim

WORKDIR /app

RUN apt-get update && apt-get install -y gcc libpq-dev

RUN pip install --upgrade pip

# Install Poetry
RUN pip install poetry

ENV PATH="/root/.local/bin:${PATH}"


COPY pyproject.toml poetry.lock ./

# Install dependencies
RUN POETRY_NO_DEV=1 poetry install --no-root --no-interaction --no-ansi

COPY . .

EXPOSE 8000
ENV PYTHONPATH="/app"

CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]


