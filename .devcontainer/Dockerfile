FROM nvcr.io/nvidia/pytorch:25.10-py3

# Install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

# Install ffmpeg
RUN apt-get update && apt-get install -y ffmpeg

# Ensure uv uses copy mode instead of hardlinks due to potential filesystem differences
ENV UV_LINK_MODE=copy

# Optional: configure python downloads to never, as we have a python environment 
# (though uv will likely create a new one for the project)
ENV UV_PYTHON_DOWNLOADS=never
