# Der Dümmste fliegt (Online)

## Lokal testen
1. Node.js 18+ installieren
2. Im Ordner: `npm install` und dann `npm start`
3. Öffne `http://localhost:3000` in mehreren Tabs, gleicher Raumcode, verschiedene Namen.

## Mit Freunden spielen (ohne Discord-App)
Hoste den Ordner bei einem Dienst mit Node-Unterstützung und WebSockets (z. B. Render, Railway, Fly.io). Alle öffnen die URL und geben denselben Raumcode ein. Dazu ein Discord-Voicechat mit Kameras: jeder sieht die anderen und antwortet laut. Der Moderator (erster im Raum) steuert Fragen und bewertet das Finale.

## Als Discord Activity (läuft im Voicechat)
Nicht getestet. Du brauchst dafür eine öffentliche HTTPS-URL.
1. Auf https://discord.com/developers/applications eine App anlegen, **Activities** aktivieren.
2. Application-ID in `public/index.html` bei `DISCORD_CLIENT_ID` eintragen.
3. Unter **Activities → URL Mappings** eintragen:
   - `/` → deine gehostete Domain (ohne https://)
   - `/esm` → `esm.sh`
4. Unter **Activities → Settings** „Enable Activities“ anschalten, Starten über das Raketen-Symbol im Voicechat.

Hinweise: Der Raum ist dann die Activity-Instanz, alle im Voicechat landen automatisch zusammen. Namen werden weiterhin eingetippt (Discord-Login ist nicht eingebaut).
Fragen ändern: Liste `Q` oben in `server.js`.
