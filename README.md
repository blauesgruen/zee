# Zeiterfassung PWA

Diese Version verpackt die vorhandene `zeiterfassung.html` als installierbare Progressive Web App.

## Dateien

- `index.html` – die eigentliche App
- `manifest.webmanifest` – App-Name, Start-URL, Icon-Definitionen, Standalone-Modus
- `service-worker.js` – Offline-Cache für die App-Dateien
- `icons/` – App-Icons für Android/iOS/Home-Screen

## Bereitstellung

1. Den gesamten Ordnerinhalt auf einen Webserver laden.
2. Die App muss über HTTPS erreichbar sein. Ausnahme: lokale Tests über `localhost`.
3. QR-Code auf die öffentliche URL setzen, z. B. `https://example.com/zeiterfassung/`.
4. Nutzer öffnen den QR-Code und installieren die App über den Browser:
   - Android/Chrome: Menü → „App installieren“ oder „Zum Startbildschirm hinzufügen“.
   - iPhone/Safari: Teilen → „Zum Home-Bildschirm“.

## Datenspeicherung

Die App speichert Daten weiter lokal im Browser per `localStorage`. Das bedeutet: Daten liegen auf dem jeweiligen Gerät/Browserprofil. Export/Import bleibt wichtig für Backup oder Gerätewechsel.
