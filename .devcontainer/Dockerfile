FROM ghcr.io/astral-sh/uv:python3.13-bookworm-slim

ENV UV_LINK_MODE=copy
ENV UV_COMPILE_BYTECODE=1
ENV UV_CACHE_DIR=/root/.cache/uv
ENV PATH="/workspace/.venv/bin:$PATH"

# Copy dependency files first for layer caching
COPY pyproject.toml uv.lock ./

# Install dependencies from lock file (reproducible)
RUN --mount=type=cache,target=/root/.cache/uv \
    uv sync --frozen --no-install-project

# Copy the rest
COPY . .

RUN useradd -m -s /bin/bash mkdocs && \
    chown -R mkdocs:mkdocs /workspace

WORKDIR /workspace
USER mkdocs

EXPOSE 8000

CMD ["mkdocs", "serve", "-a", "0.0.0.0:8000"]