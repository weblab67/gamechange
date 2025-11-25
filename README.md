# WebLab Roma - Portfolio Website

Sito web portfolio professionale per WebLab Roma.

## Deploy

### Opzione 1: Netlify (Consigliato)

1. Fai push del codice su GitHub
2. Vai su [Netlify](https://app.netlify.com)
3. Click su "Add new site" > "Import an existing project"
4. Seleziona il tuo repository GitHub
5. Aggiungi le variabili d'ambiente:
   - `VITE_SUPABASE_URL`: Il tuo URL Supabase
   - `VITE_SUPABASE_SUPABASE_ANON_KEY`: La tua chiave anonima Supabase
6. Click su "Deploy site"

Il file `netlify.toml` configurera automaticamente il build.

### Opzione 2: Vercel

1. Fai push del codice su GitHub
2. Vai su [Vercel](https://vercel.com)
3. Click su "Add New Project"
4. Importa il tuo repository GitHub
5. Aggiungi le variabili d'ambiente come sopra
6. Click su "Deploy"

Il file `vercel.json` configurera automaticamente il build.

## Sviluppo Locale

```bash
npm install
npm start
```

## Build Produzione

```bash
npm run build
```

Il build verra creato nella cartella `build/`.

## Variabili d'Ambiente

Copia `.env.example` in `.env` e compila con i tuoi valori:

```
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

## Struttura del Progetto

```
project/
├── src/
│   ├── components/     # Componenti React
│   ├── pages/          # Pagine principali
│   ├── data/           # Dati mock
│   ├── hooks/          # Custom hooks
│   └── lib/            # Utility functions
├── public/             # File statici
├── backend/            # Backend API (separato)
└── build/              # Build di produzione
```

## Backend

Il backend e un'applicazione FastAPI separata. Per deployare il backend:

1. Usa un servizio come Railway, Render, o Heroku
2. Configura le variabili d'ambiente dal file `.env`
3. Installa dipendenze: `pip install -r backend/requirements.txt`
4. Avvia: `uvicorn backend.server:app --host 0.0.0.0 --port 8000`

## Supporto

Per supporto, contatta: andreimarin3990@gmail.com
