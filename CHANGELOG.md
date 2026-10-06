# Changelog

Tutte le modifiche rilevanti apportate al progetto **Excel Extractor** saranno documentate in questo file.

Il formato è basato su [Keep a Changelog](https://keepachangelog.com/it/1.1.0/) e questo progetto aderisce al [Semantic Versioning](https://semver.org/lang/it/).

---

## [0.2.5] - 2026-10-06

### 🚀 Aggiunto

#### 🕒 Cronologia File Recenti (MRU)
- **Menu a tendina "File Recenti":** memorizza automaticamente fino agli ultimi 5 file Excel aperti.
- **Caricamento istantaneo:** un clic sul nome del file lo riapre e ne rileva i fogli immediatamente.
- **Tolleranza agli errori:** rimozione automatica con notifica se un file recente è stato spostato o cancellato dal disco.

#### ⭐ Preset di Coordinate
- **Salvataggio liste personalizzate:** pulsante **"💾 Salva"** con prompt nativo (`CTkInputDialog`) per salvare l'elenco corrente di coordinate con un nome mnemonico (es. *Controllo Viteria*, *Distinta Mensile*).
- **Richiamo rapido:** menu a tendina **"⭐ Preset"** per sostituire all'istante il testo nel box coordinate con la configurazione salvata.
- **Gestione completa:** pulsante di eliminazione **"🗑"** per rimuovere preset obsoleti.
- **Persistenza locale portatile (`config.json`):** salvataggio automatico di file recenti e preset in un file JSON locale, portabile e indipendente dal registro di sistema.

#### 🗺️ Esploratore Visivo Matrice (Browser dei Codici)
- **Finestra modale interattiva (`MatrixExplorerDialog`):** apribile tramite il pulsante **"🗺️ Sfoglia Codici Matrice..."** non appena viene caricato un file.
- **Albero gerarchico (`ttk.Treeview`):** organizzazione a cartelle per ciascuna sottotabella con conteggio delle righe e visualizzazione delle colonne *Codice*, *Riga* e *Anteprima Valori* (celle orizzontali).
- **Ricerca in tempo reale integrata:** filtro dinamico per sottotabella, codice o testo contenuto nell'anteprima.
- **Inserimento rapido e multiplo:**
  - Doppio clic su una riga per l'inserimento istantaneo.
  - Selezione multipla con pulsante **"✓ Inserisci Selezionati"** che concatena automaticamente i codici nel formato compatto standard (es. `A1-2-11-B4`).
  - Checkbox per scegliere se accodare o sostituire il testo esistente.

#### 🔍 Ricerca e Filtro Dinamico nei Risultati
- **Barra di ricerca globale in tempo reale:** posizionata nell'area dei risultati con matching multi-termine **AND** (*case-insensitive*).
- **Filtro sincronizzato:** filtra simultaneamente sia la vista di riepilogo testuale sia tutte le singole tabelle per sottotabella.
- **Pulsante di reset immediato (`✕`):** ripristina la visualizzazione di tutti i record estratti.
- **Esportazione mirata:** i pulsanti **"📊 Copia per Excel"** e **"📋 Copia come Testo"** copiano unicamente i record corrispondenti al filtro attivo.

---

## [0.2.0] - 2026-10-05

### 🚀 Aggiunto
- **Supporto completo 26 sottotabelle (A–Z):** esteso il parser e il reader per supportare l'intero alfabeto da **A** a **Z**, sia con lettere maiuscole che minuscole.
- **Sintassi a intervalli (Range stile Excel):**
  - Sintassi completa `A1:A10` e compatta `A1:10`.
  - Combinazione fluida tra intervalli ed enumerazioni (es. `A1-2:5-B4`).
  - Ordinamento automatico e tolleranza silenziosa per righe inesistenti all'interno del range.
- **🔄 Aggiornamenti Automatici Integrati:**
  - Verifica automatica in background all'avvio della presenza di nuove versioni su GitHub Releases.
  - Pulsante manuale **"🔄 Aggiornamenti"** in basso a sinistra.
  - Finestra modale con note di rilascio, indicatore di avanzamento e download con un clic dell'installer.
- **📂 Gestione Multi-Foglio:** menu a tendina per scegliere quale foglio di lavoro estrarre nei file Excel con fogli multipli.
- **🎯 Drag & Drop Nativo:** supporto al trascinamento diretto di file `.xlsx` o `.xlsm` nella finestra tramite `tkinterdnd2`.

---

## [0.1.0] - 2026-10-02

### 🚀 Prima Release
- Estrazione orizzontale di dati da matrici Excel con sottotabelle (A–G).
- Sintassi coordinate a catena con trattino (es. `A11-6-B4`).
- Riquadro errori e isolamento dei refusi (estrazione parziale con segnalazione dei token non validi).
- Schede separate per sottotabella e scheda di riepilogo generale.
- Copia rapida negli appunti in formato testo leggibile e TSV per Excel.
