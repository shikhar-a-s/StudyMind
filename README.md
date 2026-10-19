# StudyMind

## Local development

1. Copy `BACKEND/.env.example` to `BACKEND/.env` and set `GOOGLE_API_KEY`.
2. Optionally copy `FRONTEND/.env.example` to `FRONTEND/.env`. Its default points to the local backend at `http://localhost:3000`.
3. Install dependencies and run both services:

   ```sh
   npm run install:all
   npm run dev
   ```

The frontend is served at `http://localhost:5173`; the backend defaults to port `3000`.

## Website deployment

- Set `GOOGLE_API_KEY` in the backend hosting provider's environment variables. `PORT` is optional when the provider supplies it.
- If the API is hosted on a separate domain, set `VITE_API_URL` in the frontend hosting provider to the backend's HTTPS base URL **before building** the frontend.
- If the website and API share an origin, leave `VITE_API_URL` unset; production requests use the website origin.

`VITE_API_URL` is embedded in the frontend at build time and must contain only a public API URL, never a secret. The backend's Google API key must remain in the backend environment.
