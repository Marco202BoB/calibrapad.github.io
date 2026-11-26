Strumento di calibrazione basato sul web per controller PlayStation DualShock 4, DualSense e DualSense Edge tramite API WebHID.

La versione live di questo progetto è disponibile su https://dualshock-tools.github.io.

Non è richiesta alcuna installazione: basta aprire il sito web in un browser compatibile con WebHID.

Funzionalità
Connessione del controller tramite API WebHID

Calibrazione degli stick e calibrazione dell'escursione (range)

Test e visualizzazione degli input

Indicazione dello stato della batteria

Supporto multilingua (oltre 20 lingue)

Funzionalità Progressive Web App

Docker
È disponibile un'immagine Docker precompilata per eseguire DualShock Tools senza installare alcuna dipendenza.

Consulta la guida a Docker per le istruzioni di installazione e utilizzo.

Contribuire
Ti interessa contribuire? Leggi CONTRIBUTING.md per le linee guida sull'invio di modifiche e pull request.

Sviluppo
Prerequisiti
Node.js v20 o superiore (consigliata la v26 — vedi .nvmrc). Le versioni precedenti (14, 16, 18) faranno fallire la compilazione; la toolchain richiede Node 20+.

npm o yarn

Browser moderno con supporto WebHID (Chrome/Edge)

Se usi nvm, esegui nvm install && nvm use nella cartella principale del progetto per caricare la versione indicata in .nvmrc.

Per iniziare
Installa le dipendenze:

Bash
npm install
Compila l'applicazione:

Bash
npm run build
Avvia il server di sviluppo:

Bash
npm run start
L'app sarà disponibile su http://localhost:8080. WebHID funziona qui perché
localhost viene trattato come un contesto sicuro.

Docker
In alternativa, compila ed esegui senza installare Node:

Bash
docker compose up --build
L'app sarà quindi disponibile su http://localhost:8080.

Script di sviluppo
npm run build - Compila l'applicazione per lo sviluppo

npm run build:prod - Compila l'applicazione per la produzione

npm run clean - Pulisce la directory dist

npm run serve - Avvia l'app compilata su HTTP all'indirizzo http://localhost:8080 (WebHID funziona su localhost)

npm run start - Compila e avvia l'app

npm run dev:full - Compila, monitora le modifiche e avvia con ricaricamento automatico

npm run watch - Monitora le modifiche ai file e ricompila

Flusso di lavoro di sviluppo
Per lo sviluppo attivo con ricompilazione automatica:

Bash
npm run dev:full
Questo comando:

Compila l'applicazione

Avvia il monitoraggio delle modifiche ai file

Avvia l'app su http://localhost:8080

Ricompila automaticamente quando i file cambiano

Note importanti
WebHID e contesti sicuri: WebHID richiede un contesto sicuro. localhost è considerato sicuro, quindi il server di sviluppo HTTP (http://localhost:8080) funziona per lo sviluppo locale. Per raggiungere l'app da un altro dispositivo serve HTTPS — per questo usa il sito di produzione.

Supporto controller: Funziona solo nei browser con supporto WebHID (Chrome, Edge, Opera).

Struttura del progetto
js/ - File JavaScript sorgente

scss/ - File SCSS sorgente

templates/ - File template HTML

lang/ - File di traduzione

assets/ - Risorse SVG

dist/ - Applicazione compilata (generata)

Sistema di compilazione
Il progetto usa Gulp per la compilazione:

Bundling JavaScript con Rollup

Concatenazione e minimizzazione SCSS

Elaborazione e minimizzazione HTML

Ottimizzazione delle risorse

Build di sviluppo e di produzione
