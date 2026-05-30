# Samenwerking: Moek's Rittenregistratie

## Project

Dit is de schone PWA-repo voor Moek's Rittenregistratie.

- Live app: https://moek72.github.io/moeks-rittenregistratie/
- GitHub repo: https://github.com/moek72/moeks-rittenregistratie
- Branch voor live site: `main`
- GitHub Pages source: `main` / root

Gebruik deze repo als primaire bron. De oude route/repo met `familie-club2000-codex-deluxe` en `kpn-registratie` moet niet meer gebruikt worden voor deze app.

## Belangrijke wensen

- Geen verwijzingen naar `KPN`, `Club 2000`, `codex`, `familie-club2000` of `deluxe` in de appnaam, zichtbare UI of route.
- Appnaam: `Moek's Rittenregistratie`.
- Kenteken voert de gebruiker zelf in via Instellingen.
- De app moet als PWA op telefoon gebruikt kunnen worden.

## Huidige functionaliteit

- Ritten starten en beëindigen.
- Beginstand wordt automatisch gevuld vanuit de laatst bekende eindstand.
- Tijdens een actieve rit wordt GPS-afstand als hulpmiddel bijgehouden.
- Bij beëindigen wordt de verwachte eindstand voorgesteld als `beginstand + afgeronde GPS-km`.
- Eindstand blijft handmatig bewerkbaar.
- Officiële gereden kilometers blijven gebaseerd op tellerstanden.
- Als een nieuwe beginstand afwijkt van de vorige eindstand, vraagt de app of de vorige rit terugberekend moet worden.
- Bij akkoord wordt de vorige eindstand en vorige rit-km aangepast.
- Excel-export werkt lokaal vanuit de browser.
- Service worker cache staat op `moeks-ritten-v3`.

## Google Sheets status

Google Sheets is nog niet echt gekoppeld.

Wat er al is:
- UI heeft een knop `Naar Google Sheets sturen`.
- Instellingen heeft een veld `Google Sheet URL`.
- `exportSheets()` post de ritten naar `settings.sheetsUrl`.

Wat nog nodig is:
- Een Google Sheet aanmaken.
- Een Apps Script Web App maken dat `POST` JSON accepteert.
- Die Web App URL in de app plakken bij Instellingen.
- Daarna testen of export naar de Sheet werkt.

## Validatie die laatst is gedaan

- `node --check app.js`
- `node --check sw.js`
- Lokale test voor terugrekenen vorige rit vanaf gecorrigeerde nieuwe beginstand.
- Live app geopend op GitHub Pages en gecontroleerd dat `START RIT` zichtbaar is.

## Recente commits

- `336fcdd Recalculate previous trip from corrected start odometer`
- `7286c59 Initial Moeks Rittenregistratie PWA`
