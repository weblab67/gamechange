# Note di Sicurezza

## Vulnerabilita Conosciute

Il progetto presenta alcune vulnerabilita nelle devDependencies (strumenti di sviluppo) che non influenzano il codice in produzione:

- `@eslint/plugin-kit`: Vulnerabilita ReDoS in ConfigCommentParser
- `nth-check`: Inefficienza nelle espressioni regolari in svgo

## Raccomandazioni

1. Queste vulnerabilita sono solo in devDependencies e non vengono incluse nel build di produzione
2. Il comando `npm run build` crea un bundle pulito senza le dipendenze di sviluppo
3. Per aggiornare le dipendenze in futuro, esegui:
   ```bash
   npm audit fix
   ```

   ATTENZIONE: `npm audit fix --force` potrebbe introdurre breaking changes

## Dipendenze di Produzione

Le dipendenze utilizzate in produzione sono sicure e aggiornate:
- React 18.2.0
- React Router 7.5.1
- Tutte le librerie UI (@radix-ui) sono aggiornate
- TailwindCSS 3.4.17

## Variabili d'Ambiente

IMPORTANTE: Non committare mai il file `.env` nel repository. Contiene chiavi sensibili.

Le chiavi Supabase devono essere:
- VITE_SUPABASE_URL: Sicuro da esporre (pubblico)
- VITE_SUPABASE_SUPABASE_ANON_KEY: Sicuro da esporre (con RLS attivo)

## Best Practices

1. Mantieni sempre aggiornate le dipendenze
2. Usa `npm audit` regolarmente
3. Non esporre mai chiavi API private nel frontend
4. Usa Row Level Security (RLS) su Supabase per proteggere i dati
5. Configura CORS correttamente sul backend

## Contatti

Per segnalare problemi di sicurezza: andreimarin3990@gmail.com
