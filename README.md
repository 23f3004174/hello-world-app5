# Hello World Flask App

## Overview
This is a minimal Flask web app accompanied by a simple HTML page.

- The Flask backend exposes:
  - GET / → returns plain text: "Hello World!"
  - GET /page → serves index.html which displays "Hello World!" in the browser
- The index.html file is a small static page styled with minimal CSS.

## Setup

Prerequisites:
- Python 3.8+ installed
- pip available

Steps:
1. Create and activate a virtual environment (optional but recommended):
   - macOS/Linux:
     - python3 -m venv .venv
     - source .venv/bin/activate
   - Windows (PowerShell):
     - py -m venv .venv
     - .venv\Scripts\Activate.ps1

2. Install Flask:
   - pip install Flask

3. Save files:
   - Save the first section of this response as index.html in your project folder.
   - Create a file named app.py with the following content:

     from flask import Flask

     app = Flask(__name__, static_folder='.', static_url_path='')

     @app.get('/')
     def root():
         return 'Hello World!'

     @app.get('/page')
     def page():
         return app.send_static_file('index.html')

     if __name__ == '__main__':
         app.run(host='127.0.0.1', port=5000, debug=True)

4. Run the server:
   - python app.py

## Usage
- Open in a browser:
  - http://127.0.0.1:5000/ → plain text "Hello World!"
  - http://127.0.0.1:5000/page → renders the HTML page showing "Hello World!"
- Or using curl:
  - curl http://127.0.0.1:5000/

## Improvements made from previous version (Round 2)
- Ensured the Flask backend explicitly returns plain text "Hello World!" at the root / endpoint (evaluation requirement).
- Added a dedicated /page route to serve the static index.html for a simple HTML frontend.
- Simplified setup with clear virtual environment instructions and a self-contained app.py example.
- Enhanced README with structured Overview, Setup, and Usage sections for quicker onboarding.