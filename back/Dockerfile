FROM python:3.11.8-slim

# システムの更新と必要なツールのインストール
RUN apt-get update && apt-get install -y \
    curl \
    git \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Poetryのインストール
RUN curl -sSL https://install.python-poetry.org | python3 -

# Poetryのパスを環境変数に追加
ENV PATH="/root/.local/bin:$PATH"

# 作業ディレクトリを設定
WORKDIR /workspace

# pyproject.tomlをコピーしてPoetryで依存関係をインストール
COPY pyproject.toml /workspace/
RUN poetry install
