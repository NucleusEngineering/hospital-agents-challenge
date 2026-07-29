# Copyright 2025 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# Use an official lightweight Python image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Install dependencies
# We install fastmcp and uvicorn (needed for the SSE web server)
RUN pip install --no-cache-dir fastmcp uvicorn starlette

# Copy the server code into the container
COPY main.py .

# Expose the port Cloud Run will use
EXPOSE 8080

# Run the MCP server using the SSE transport
# FastMCP handles the uvicorn execution under the hood when transport="sse"
CMD ["python", "main.py"]