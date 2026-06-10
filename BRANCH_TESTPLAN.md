# Testplan für Branch `feature`

## 1. Upload

Im GitHub-Repo `blauesgruen/zee` auf Branch `feature` wechseln und diese Dateien hochladen:

```text
index.html
service-worker.js
SUPABASE_SETUP.md
BRANCH_TESTPLAN.md
DEPLOYMENT_NOTES.md
```

Nicht `main` verwenden.

## 2. GitHub Pages Test-URL

Wenn GitHub Pages nur aus `main` deployed, ist der Branch nicht automatisch online. Zum Testen gibt es drei Wege:

### Option A: Pull Request Preview, falls GitHub/Pages bei dir Preview unterstützt

PR `feature -> main` öffnen und prüfen, ob GitHub eine Pages/Deployment-Preview erzeugt.

### Option B: Branch temporär als Pages-Quelle setzen

Repository -> Settings -> Pages -> Build and deployment -> Source/Branch: `feature` wählen.

Dann testen unter:

```text
https://blauesgruen.github.io/zee/
```

Nach dem Test kann die Pages-Quelle wieder auf `main` zurückgestellt werden.

### Option C: Lokal testen

Repository herunterladen und im Ordner lokal starten:

```bash
python3 -m http.server 8000
```

Dann öffnen:

```text
http://localhost:8000
```

Für lokalen Test muss `ZEE_ALLOWED_ORIGIN` entweder nicht gesetzt sein oder auf `http://localhost:8000` angepasst werden.

## 3. Funktionstest normaler Nutzer

1. Seite öffnen.
2. User-Code eingeben.
3. Namen `Test Cordula` eingeben.
4. `Daten laden` klicken.
5. Einheiten prüfen: z. B. Einheit 1 = 25 min.
6. Für einen Tag 2x Einheit 1 eintragen.
7. Erwartung: Tageswert `00:50 h`.
8. Seite hart neu laden.
9. User-Code eingeben, wieder `Test Cordula` laden.
10. Erwartung: Werte sind aus Supabase wieder da.

## 4. Zweite Person

1. Namen `Test Max` laden.
2. Andere Werte eintragen.
3. Reload.
4. Test Max laden.
5. Erwartung: Test Max hat eigene Werte, Test Cordula bleibt getrennt.

## 5. Chef-Test

1. Seite sperren oder neu öffnen.
2. Chef-Code eingeben.
3. Chef-Übersicht laden.
4. Erwartung: Test Cordula und Test Max erscheinen.
5. CSV exportieren.

## 6. Nicht testen mit Echtdaten

Diese RC erst mit Testnamen testen. Wenn der Datenfluss stimmt, können Echtdaten verwendet werden.
