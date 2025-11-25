# Guida al Deploy di WebLab Roma

## Preparazione

Tutti i file sono pronti per il deploy. Il progetto buildata correttamente senza errori.

## Deploy su Netlify (RACCOMANDATO - PIU SEMPLICE)

### Step 1: Crea un Repository GitHub

1. Vai su [GitHub](https://github.com) e crea un nuovo repository
2. Esegui questi comandi nella cartella del progetto:

```bash
git init
git add .
git commit -m "Initial commit - WebLab Roma"
git branch -M main
git remote add origin https://github.com/TUO_USERNAME/TUO_REPO.git
git push -u origin main
```

### Step 2: Deploy su Netlify

1. Vai su [Netlify](https://app.netlify.com)
2. Clicca "Add new site" > "Import an existing project"
3. Scegli "GitHub" e autorizza Netlify
4. Seleziona il tuo repository
5. Configurazione build (gia impostata automaticamente):
   - Build command: `npm run build`
   - Publish directory: `build`
6. Clicca su "Show advanced" > "New variable" e aggiungi:
   - `VITE_SUPABASE_URL`: (copia dal file .env)
   - `VITE_SUPABASE_SUPABASE_ANON_KEY`: (copia dal file .env)
7. Clicca "Deploy site"

Il sito sara online in 2-3 minuti!

### Step 3: Configurare il Dominio Personalizzato

1. Nella dashboard Netlify, vai su "Domain settings"
2. Clicca "Add custom domain"
3. Inserisci il tuo dominio (es: weblabroma.com)
4. Segui le istruzioni per configurare i DNS

---

## Deploy su Vercel (ALTERNATIVA)

### Step 1: Crea Repository GitHub (come sopra)

### Step 2: Deploy su Vercel

1. Vai su [Vercel](https://vercel.com)
2. Clicca "Add New" > "Project"
3. Importa il repository GitHub
4. Configurazione (automatica):
   - Framework Preset: Create React App
   - Build Command: `npm run build`
   - Output Directory: `build`
5. Aggiungi variabili d'ambiente in "Environment Variables":
   - `VITE_SUPABASE_URL`
   - `VITE_SUPABASE_SUPABASE_ANON_KEY`
6. Clicca "Deploy"

---

## Verifica Post-Deploy

Dopo il deploy, verifica:

1. Homepage si carica correttamente
2. Navigazione tra le pagine funziona
3. Form di contatto appare correttamente
4. Link WhatsApp funziona
5. Demo portfolio si aprono correttamente
6. Pagina Privacy accessibile

---

## Deploy del Backend (Opzionale)

Il backend FastAPI puo essere deployato separatamente su:

### Railway (Raccomandato)

1. Vai su [Railway](https://railway.app)
2. Crea un nuovo progetto
3. Collega il repository GitHub
4. Configura:
   - Start Command: `uvicorn backend.server:app --host 0.0.0.0 --port $PORT`
   - Root Directory: `/`
5. Aggiungi variabili d'ambiente dal file `.env`
6. Deploy automatico

### Render

1. Vai su [Render](https://render.com)
2. New > Web Service
3. Collega repository GitHub
4. Configura:
   - Build Command: `pip install -r backend/requirements.txt`
   - Start Command: `uvicorn backend.server:app --host 0.0.0.0 --port $PORT`
5. Aggiungi variabili d'ambiente
6. Create Web Service

---

## Troubleshooting

### Il sito non si carica

- Verifica che le variabili d'ambiente siano impostate correttamente
- Controlla i log di build su Netlify/Vercel

### Errore 404 sulle route

- Il file `_redirects` in `public/` dovrebbe risolvere questo
- Se il problema persiste, ribuildata il progetto

### Form non funziona

- Il form attualmente usa un mock submission
- Per integrare un servizio email, considera FormSpree o EmailJS

---

## Aggiornamenti Futuri

Per aggiornare il sito:

1. Modifica i file localmente
2. Testa con `npm start`
3. Builda con `npm run build`
4. Fai commit e push su GitHub:
   ```bash
   git add .
   git commit -m "Descrizione modifiche"
   git push
   ```
5. Netlify/Vercel rebuildera automaticamente

---

## Supporto

Per assistenza: andreimarin3990@gmail.com
