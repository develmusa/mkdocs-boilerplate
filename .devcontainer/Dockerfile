FROM ghcr.io/astral-sh/uv:python3.13-bookworm-slim

ENV UV_LINK_MODE=copy
ENV UV_COMPILE_BYTECODE=1
ENV UV_CACHE_DIR=/root/.cache/uv
ENV PATH="/workspace/.venv/bin:$PATH"

# Create workspace
RUN mkdir -p /workspace

WORKDIR /workspace

# Copy dependency files first for layer caching
COPY pyproject.toml uv.lock ./

# Install dependencies from lock file (reproducible)
RUN --mount=type=cache,target=/root/.cache/uv \
    uv sync --frozen --no-install-project

# Copy the rest
COPY . .

EXPOSE 8000

CMD ["uv", "run", "mkdocs", "serve", "-a", "0.0.0.0:8000"]
