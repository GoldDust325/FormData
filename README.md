## Lab N3.3 — Smart Speech Coach

### Contribution
Shiv Shankar Yadav added the SmartSpeechCoach starter under
smart-speech-coach and configured the frontend/backend integration.

Starter: https://github.com/grewe/SmartSpeechCoach

### Local backend setup
1. Open smart-speech-coach/backend.
2. Run npm install.
3. Copy .env.example to .env.
4. Add your own Gemini API key to .env.
5. Run npm start.

Health endpoint: http://localhost:3001/api/health

### Local frontend setup
1. Open smart-speech-coach/frontend.
2. Run npm install.
3. Copy .env.example to .env.
4. Set VITE_SERVER_REMOTE=N.
5. Set VITE_SERVER_URL_LOCAL=http://localhost:3001.
6. Run npm run dev.

On Windows PowerShell, use npm.cmd instead of npm.

### Request flow
The React frontend sends a JSON POST request using fetch to
/api/askanything. The Express backend calls Gemini and returns
the answer as JSON.

### Configuration
The backend model setting is gemini-3.8-flash, following the
replacement model specified in the API error response.

Real API keys and local environment files are excluded from Git.

### Google Cloud Run
Deployment steps and the service URL will be added after deployment.