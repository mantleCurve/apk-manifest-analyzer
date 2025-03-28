# APK Manifest Analyzer

A modern web-based tool for analyzing Android APK manifest files. This tool helps developers and security researchers understand app permissions, components, and potential privacy implications.

![APK Manifest Analyzer](screenshots/demo.png)

## Features

- 📱 Drag-and-drop APK file upload
- 🔍 Detailed manifest analysis including:
  - Basic app information
  - Permissions
  - Activities
  - Services
  - Broadcast Receivers
  - Content Providers
  - Features and Libraries
  - Package Queries
- 🔄 Automatic duplicate detection using SHA512 hashing
- 📊 History tracking of last 20 analyses
- 🎨 Modern, responsive UI with filtering capabilities

## Installation

1. Clone the repository:
```bash
git clone https://github.com/mantleCurve/apk-manifest-analyzer.git
cd apk-manifest-analyzer
```

2. Create a virtual environment and activate it:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Configuration

Create a `.env` file in the project root with the following settings:
```env
FLASK_APP=app.py
FLASK_ENV=development
MAX_CONTENT_LENGTH=104857600  # 100MB in bytes
UPLOAD_FOLDER=uploads
RESULTS_DIR=results
```

## Usage

1. Start the server:
```bash
flask run
```

2. Open your browser and navigate to `http://localhost:5000`

3. Upload an APK file by either:
   - Dragging and dropping the file onto the upload area
   - Clicking "Choose File" to select a file

4. View the analysis results, including:
   - Basic app information
   - Permissions and their implications
   - App components
   - Package queries and intents

## Project Structure

```
apk-manifest-analyzer/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── .env                  # Environment configuration
├── .gitignore           # Git ignore file
├── README.md            # This file
├── static/             # Static assets
├── templates/          # HTML templates
│   ├── index.html     # Main page template
│   └── result.html    # Analysis result template
├── uploads/           # Temporary upload directory
└── results/           # Analysis results directory
```

## Dependencies

- Flask: Web framework
- Androguard: APK analysis
- Python-Magic: File type detection
- python-dotenv: Environment configuration

## Development

1. Install development dependencies:
```bash
pip install -r requirements-dev.txt
```

2. Run tests:
```bash
pytest
```

3. Check code style:
```bash
flake8
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## Security

- APK files are analyzed in memory and deleted after analysis
- SHA512 hashing is used to detect duplicate APKs
- File size is limited to prevent abuse
- Temporary files are automatically cleaned up

## License

This project is licensed under the AGPL-3.0 License. See the LICENSE file for details.

## Acknowledgments

- [Androguard](https://github.com/androguard/androguard) for APK analysis capabilities
- [Flask](https://flask.palletsprojects.com/) for the web framework
- All contributors and users of this tool

## Contact

For questions and support, please open an issue on GitHub.