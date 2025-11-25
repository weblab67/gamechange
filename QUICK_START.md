# Quick Start - Deploy in 5 Minuti

## Comandi Rapidi Git

```bash
# 1. Inizializza repository
git init
git add .
git commit -m "Initial commit - WebLab Roma"

# 2. Collega a GitHub (sostituisci con il tuo URL)
git remote add origin https://github.com/TUO_USERNAME/weblabroma.git
git branch -M main
git push -u origin main
```

## Deploy su Netlify

1. Vai su: https://app.netlify.com/start
2. Clicca "Import from Git" > Scegli GitHub
3. Seleziona il repository
4. **Build settings** (gia configurati):
   - Build command: `npm run build`
   - Publish directory: `build`
5. **Environment variables**:
   ```
   VITE_SUPABASE_URL=https://0ec90b57d6e95fcbda19832f.supabase.co
   VITE_SUPABASE_SUPABASE_ANON_KEY=[copia dalla tua .env]
   ```
6. Clicca "Deploy site"

FATTO! Il sito sara online in 2-3 minuti.

## Sviluppo Locale

```bash
npm install
npm start
```

Apri http://localhost:3000

## Build Locale

```bash
npm run build
```

Output in `build/`

## Test Build Locale

```bash
npm install -g serve
serve -s build
```

Apri http://localhost:3000

## Documentazione Completa

- `README.md` - Panoramica progetto
- `DEPLOY.md` - Guida dettagliata deploy
- `DEPLOY_SUMMARY.md` - Riepilogo completo
- `CHECKLIST.md` - Verifica pre-deploy
- `SECURITY.md` - Note sicurezza

## Supporto

andreimarin3990@gmail.com
