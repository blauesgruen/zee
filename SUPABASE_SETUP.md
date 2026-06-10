# Supabase Setup für Zee RC1

Projekt: `zee-zeiterfassung`
Project Ref: `bmhjcocglkaqrwmtwiug`
Function URL: `https://bmhjcocglkaqrwmtwiug.supabase.co/functions/v1/zee-sync`

## Status

Das Supabase-Projekt ist angelegt. Die Tabellen `public.people` und `public.time_entries` sind angelegt und RLS ist aktiv. Die Edge Function `zee-sync` ist deployed.

Ohne die folgenden Secrets lehnt die Function alle Zugriffe ab.

## Erforderliche Secrets

Im Supabase Dashboard im Projekt `zee-zeiterfassung` setzen:

```text
ZEE_USER_ACCESS_CODE=<gemeinsamer Nutzer-Code>
ZEE_CHEF_ACCESS_CODE=<Chef-Code>
ZEE_ALLOWED_ORIGIN=https://blauesgruen.github.io
```

Hinweise:

- User-Code und Chef-Code sollten lang genug sein, nicht `1234`.
- `ZEE_ALLOWED_ORIGIN` ist die Origin, nicht der komplette Pfad. Für `https://blauesgruen.github.io/zee/` ist `https://blauesgruen.github.io` korrekt.
- Nach dem Setzen oder Ändern der Secrets die Edge Function ggf. einmal neu deployen/restarten, falls Supabase das verlangt.

## Aktuelle RC1-Einschränkung

Diese RC1 ist auf die bereits deployed Edge Function abgestimmt. Beim Laden eines bisher unbekannten Namens legt die Function den Namen aktuell automatisch an. Deshalb beim Test bewusst eindeutige Testnamen verwenden, z. B. `Test Cordula` und `Test Max`.


## RC3 Hinweise

- Beim Rollenwechsel wird die Chef-Ansicht geschlossen.
- Beim Wechsel des Namens oder Zugangs werden angezeigte Tagesdaten geleert.
- Tagesdaten werden nicht mehr dauerhaft im Browser-localStorage gespeichert; Supabase ist die Quelle der gespeicherten Einträge.
- Cache-Version: `zeiterfassung-pwa-v5`.
