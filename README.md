# Easy-File-Sharing-Flask-API

__A Flask-powered file-sharing platform with robust features.__

This application offers an intuitive interface for uploading, downloading, and managing files directly from your browser. Additionally, it includes API support and a command-line tool for seamless automation and integration.

## Key Features

- __User Authentication:__
  - Secure login system requiring a username and password for access.
  - Authentication enforced across both the web interface and API endpoints.

- __File Handling:__
  - Upload files via the web UI or API, with all files securely stored on the server.
  - Download and preview files through the provided interface.

- __File Organization:__
  - View uploaded files along with their timestamps.
  - Sort files by modification date in ascending or descending order.

- __Batch Download API:__
  - Retrieve the latest N files as a compressed ZIP archive.
  - Specify a custom archive name for convenience.

- __Markdown Support:__
  - Display markdown (.md) files as readable plain text within the web interface.

- __Offline Access via PWA:__
  - Install the platform as a Progressive Web App (PWA) for offline usage.
  - Access files even in low-connectivity environments.

- __Smart Caching:__
  - Implements caching headers to always serve the most up-to-date content.

- __Command Line Integration:__
  - Start the server with `ffs-server` or `ffs server`.
  - Run CLI commands via `ffs-cli <command> **kwargs`.

- __Python SDK:__
  - Installable via `pip install flask-file-share` for API interactions.
  - Provides an easy-to-use client class for handling file operations programmatically.

## Getting Started

### Installation

1. Install via PyPI:
   ```bash
   pip install flask-file-share
   ```

2. Launch the server:
   ```bash
   ffs-server
   ```

3. Alternatively, clone the repository:
   ```bash
   git clone https://github.com/Ms-Ngari/Easy-File-Sharing-Flask-API.git
   cd simple-file-hosting-with-flask
   python3 -m venv env
   source env/bin/activate
   pip install -r requirements.txt
   python src/flask_file_share/app.py
   ```

4. Open your browser and visit [http://localhost:5000](http://localhost:5000).

### Web Interface

- The home page lists all shared files.
- Click "Upload a File" to share new content.
- Modify settings via a `.env` file.
- Launch via `ffs server`, `ffs-server`, or `python src/flask_file_share/app.py`.

### API Access

- Interact with API endpoints at `http://localhost:5000/api/*`.
- API features mirror those available in the web UI.
- Refer to the [API documentation](./docs/api.md).

### Python Client Usage

Leverage the Python client for direct API interaction:
   ```python
   import flask_file_share as ffs
   from pathlib import Path

   client = ffs.Client(username="your_username", password="your_password", base_url="http://localhost:5000")
   client.login()
   client.upload_file(Path("examples/data/sample.txt"))
   client.download_last_n_files(3, Path("examples/output"))
   client.logout()
   ```

Refer to the [Python client documentation](./docs/python-client.md).

### Command-Line Usage

Run commands via CLI:
   ```bash
   ffs-cli <command> **kwargs
   # Alternative:
   python src/flask_file_share/cli.py
   ```

More details in the [CLI documentation](./docs/cli-app.md).

## License

This project is licensed under the [MIT License](LICENSE).

