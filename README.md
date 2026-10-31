# Eligibility Hub 3D

Eligibility Hub is a Windows desktop app for exploring Indian government schemes, checking eligibility, preparing applications, and finding student opportunities.

## Features

- Scheme discovery and eligibility guidance for students, farmers, senior citizens, persons with disabilities, transgender people, minority communities, and small businesses.
- Student Mentor and competitive exam information.
- Citizen Guide with English, Telugu, and Hindi support.
- Circular Scanner for extracting and reviewing information from PDF notices.
- SchemeBot for scheme questions. Optional local answers use Google Gemma 4 through Ollama.
- Electron desktop interface with a local FastAPI and SQLite backend.

Scheme details can change. Check the linked government portal for current eligibility, benefits, and deadlines before applying.

## Download for Windows

Download **Eligibility Hub 3D Setup.exe** from the [Google Drive folder](https://drive.google.com/drive/folders/1wnfjQ4nloiUEMZSrVs8lbYp8KgAb_cL5), then run the installer. The installed app does not require a browser, Node.js, or Python.

The installer is currently unsigned, so Windows SmartScreen may show a warning.

## Enable Gemma 4

Gemma 4 is optional and is not bundled with the installer. To enable local AI:

1. Install [Ollama for Windows](https://ollama.com/download).
2. Open SchemeBot and choose **Download Gemma 4**, or run:

   ```powershell
   ollama pull gemma4:e2b-it-q4_K_M
   ```

The model download is about 4.6 GB. Prompts are processed locally when Ollama and Gemma are running. SchemeBot provides limited offline guidance otherwise.

## Run from source

Requirements: Windows, Node.js 20 or newer, and Python 3.10 or newer.

```powershell
cd backend
python -m pip install -r requirements.txt
cd ../frontend
npm ci
npm run app:dev
```

Create a Windows installer from the `frontend` folder:

```powershell
npm run app:exe
```

The installer is created in `frontend/release/`.

## Technology

React, Vite, Electron, FastAPI, and SQLite.

## License

The application source is licensed under the [MIT License](LICENSE). Gemma 4 is licensed under [Apache-2.0](https://github.com/google-deepmind/gemma); its weights are downloaded separately and are not included in this repository or installer. See [MODEL-LICENSES.md](MODEL-LICENSES.md) for third-party notices.
