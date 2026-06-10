# Deployment Notes RC1

Diese Version ist ein sinnvoll testbarer Stand für den Branch `feature`, aber noch kein finaler Produktionsstand.

## Umgesetzt

- Zugangscode-Maske.
- User-/Chef-Rolle über Supabase Edge Function.
- Namensbasierte Datentrennung.
- Speicherung in `public.people` und `public.time_entries`.
- Einheitsnamen und Minuten werden pro Tageszeile gespeichert.
- HH:MM-Ausgabe, z. B. `00:50 h`.
- Chef-Übersicht mit CSV-Export.
- Lokaler Cache via `localStorage`.
- Service-Worker-Cache auf `zeiterfassung-pwa-v3`.

## Noch offen nach RC-Test

- Komfortables Bestätigen neuer Namen vor DB-Anlage.
- Ähnliche Namen/Dubletten besser anzeigen.
- Detailansicht in der Chef-Übersicht.
- Konfliktwarnung bei paralleler Bearbeitung.
- Optional: Monatsabschluss/Sperre alter Monate.

## Wichtiger Sicherheitspunkt

Die Tabellen sind nicht direkt aus dem Browser beschreibbar. Die Webseite ruft nur die Edge Function auf. Das ist Absicht.
