# Zee Supabase Sync RC5

RC5 bereinigt die sichtbaren UI-Zustaende.

## Sichtbarkeitslogik

- Ohne Login wird nur der Zugangscodebereich angezeigt.
- Mit Nutzer-Code wird zunaechst nur der Namensbereich angezeigt.
- Die Tagesliste, Summen und Aktionen erscheinen erst nach erfolgreichem Laden einer Person.
- Mit Chef-Code wird nur die Chef-Uebersicht angezeigt. Die Nutzer-Erfassung bleibt ausgeblendet.
- Beim Sperren werden Rolle, Person und Tagesdaten aus dem Browserzustand entfernt.
- Beim Namenswechsel werden bisherige Tagesdaten sofort ausgeblendet.
- Import ist in dieser RC-Version in der UI versteckt, um versehentliches Ueberschreiben zu vermeiden.

## Cache

Service Worker Cache-Version: v7.

Nach Upload auf den Branch `feature` bitte testen mit:

```text
https://blauesgruen.github.io/zee/?v=rc5
```
