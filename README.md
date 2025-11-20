# Hecodex — Tema Shopify Open Source

Hecodex è un brand che sviluppa temi e Kit per Shopify per aiutarti a creare e personalizzare il tuo store in modo professionale — anche se parti da zero.

Questo repository contiene un tema open source di Hecodex pensato per negozi tech e per e‑commerce di prodotti digitali, configurabile anche per la vendita di prodotti fisici.

## Funzionalità principali
- Design responsivo ottimizzato per mobile e desktop.
- Barra di annuncio/top bar “sticky” sempre visibile durante lo scroll.
- Header “sticky” con offset dinamico per non sovrapporsi al banner.
- Carrello e cart drawer con gestione quantità corretta per prodotti digitali (evita `max=0`).
- Supporto a prodotti fisici: varianti, quantità e flusso di checkout standard Shopify.
- Wishlist e comparazione prodotti.
- Ricerca e filtri avanzati.
- Supporto multilingua (cartelle `locales/`).
- SEO e accessibilità di base.

## Installazione

### Requisiti
- Account Shopify attivo e accesso Admin.
- Shopify CLI installata per sviluppo locale (consigliata).
- Permessi per caricare e pubblicare temi.

Puoi installare il tema con Shopify CLI (consigliato).

Sviluppo con Shopify CLI (consigliato)
- Installa Shopify CLI (vedi documentazione ufficiale).
- Autenticati: `shopify login --store <tuo-store>`.
- Nella radice del progetto: `shopify theme dev` per servire il tema in anteprima.

## Configurazione e Personalizzazione

Il tema offre ampie opzioni di personalizzazione dal Theme Editor:
- Schemi colore e tipografia
- Layout e sezioni
- Header, announcement/top bar, footer

### Branding e personalizzazione
- Carica logo e favicon, imposta palette colori e tipografia.
- Configura header, footer, announcement/top bar e componenti promozionali.
- Riordina e personalizza le sezioni (hero, banner, griglie, slideshow) per allinearle al tuo brand.
- Gestisci testi e traduzioni in `locales/` per un tono di voce coerente.
- Estendi lo stile con variabili CSS e asset in `assets/`.

### Configurazione prodotti fisici
- Abilita la tracciatura quantità per varianti con stock.
- Imposta spedizioni e tasse in Shopify Settings (gestite dalla piattaforma, non dal tema).
- Mostra varianti, immagini e dettagli tecnici nelle pagine prodotto/collezione.

### Guida rapida alla personalizzazione
- Duplica il tema e lavora su una copia di bozza.
- Carica logo, imposta palette e tipografia dal Theme Editor.
- Configura homepage (hero, banner, griglie prodotti) e pagine prodotto.
- Attiva top bar/announcement per messaggi promozionali o informativi.
- Aggiorna testi/lingue in `locales/`.
- Verifica su mobile e desktop, poi pubblica quando sei soddisfatto.

## Sviluppo locale
- Avvia l’anteprima: `shopify theme dev`.
- Modifica `.liquid`, `.css`, `.js` e verifica live.
- Pubblica: `shopify theme push` (preferibilmente su tema non pubblicato per test).

## Personalizzazione via Codice
- Dove intervenire
  - `assets/base.css`: stile globale, banner/header sticky, variabili e regole condivise.
  - `assets/global.js`: logiche UI (es. `updateAnnouncementOffset()`), drawer/menu, slider e componenti.
  - `sections/header.liquid` e `sections/top-bar.liquid`: markup e configurazioni di header/top bar.
  - `assets/cart-drawer.js` e `assets/cart.js`: gestione quantità e comportamento del carrello; struttura pagina in `templates/cart.json`.
  - `layout/theme.liquid`: ordine di caricamento e inclusione degli assets.
- Pattern consigliati
  - Mantieni classi e variabili CSS esistenti per coerenza.
  - Se lavori con prodotti digitali, evita `max=0` negli input quantità; rispetta la logica d’inventario Shopify (continue selling / tracked).
  - Separa responsabilità: Liquid per dati/configurazioni, CSS per presentazione, JS per interazioni.
- Estensioni
  - Aggiungi nuove sezioni in `sections/` e snippet riutilizzabili in `snippets/`.
  - Se introduci librerie JS/CSS, includile in `theme.liquid` e documentale nel README.

## Tecnologia e Stack
- Shopify Liquid: templating e struttura del tema in `layout/`, `sections/`, `snippets/`, `templates/`.
- CSS: moduli in `assets/` con ampio uso di variabili CSS (`var(--...)`); `assets/base.css` come fondazione, file dedicati per componenti/sezioni.
- JavaScript moderno: classi ES6 e Custom Elements in `assets/global.js` (es. `menu-drawer`, `header-drawer`, `slider-component`), più script specifici (`dt-mega-menu.js`, `dt-theme.js`, ecc.).
- Librerie: `jquery.min.js` per alcune interazioni; `slick.min.js`, `wow.min.js`, `magnific-popup.js`, `isotope.pkgd.js`, componenti slider personalizzati; `axios.min.js` disponibile per integrazioni.
- Tooling: nessun bundler richiesto; assets caricati da `layout/theme.liquid`; sviluppo con Shopify CLI.


## Informazioni Tema

- Nome: `Hecodex`
- Piattaforma: `Shopify`
- Autore: Henry G.
- Stato: attivo e mantenuto

## Supporto
Per richieste e personalizzazioni professionali, contatta l’autore (Henry G.).

## Licenza

Il codice è rilasciato come open source: consulta `LICENSE.txt` per termini e condizioni. Puoi usare Hecodex come base per il tuo negozio e distribuirne varianti nel rispetto della licenza.