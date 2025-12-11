# GitHub Repository Setup-Anleitung

Schritt-für-Schritt-Anleitung zur Optimierung des RechnungsFee-Repositories auf GitHub.

---

## 🎯 Übersicht - Was wir einstellen:

- [x] Repository erstellt
- [x] Code gepusht (2 Commits, 9 Dateien)
- [ ] **Beschreibung & Website**
- [ ] **Topics (Tags)**
- [ ] **Discussions aktivieren**
- [ ] **Issues-Labels erstellen**
- [ ] **About-Sektion optimieren**
- [ ] **Social Preview-Image** (optional)

---

## 📝 Teil 1: Beschreibung & Topics

### **Schritt 1: About-Sektion bearbeiten**

1. Gehe zu: https://github.com/nicolettas-muggelbude/RechnungsFee
2. Rechts oben in der Sidebar, beim **About**-Bereich, klicke auf das **⚙️ Zahnrad-Symbol**
3. Es öffnet sich ein Dialog

### **Schritt 2: Beschreibung eintragen**

**Beschreibung:**
```
Open-Source Buchhaltungssoftware für Freiberufler und Selbstständige. Offline-first, datenschutzfreundlich, GoBD-konform. Made for Germany 🇩🇪
```

**Alternativ (kürzer):**
```
Open-Source Buchhaltung für Selbstständige. Offline-first, DATEV-Export, EÜR/UStVA. Made in Germany 🇩🇪
```

**Alternativ (English):**
```
Open-source accounting software for freelancers. Offline-first, privacy-focused, German tax compliance (EÜR, UStVA, DATEV).
```

→ Wähle die Version die dir am besten gefällt!

### **Schritt 3: Website eintragen**

**Vorerst leer lassen** (oder später wenn du eine Projekt-Website hast)

Später könntest du eintragen:
- GitHub Pages URL
- Dokumentations-Website
- Landing Page

### **Schritt 4: Topics hinzufügen**

**Empfohlene Topics (max. 20):**

**Primäre Topics:**
```
accounting
invoicing
freelance
germany
open-source
offline-first
privacy
datev
elster
buchhaltung
```

**Technologie-Topics:**
```
python
react
typescript
fastapi
sqlite
tauri
pwa
```

**Use-Case-Topics:**
```
self-employed
small-business
tax-compliance
euer
ustva
```

**Wie Topics hinzufügen:**
1. Im About-Dialog, Feld "Topics"
2. Tippe ein Topic, drücke Enter
3. Wiederhole für alle Topics
4. Klicke "Save changes"

**Tipp:** Fang mit den wichtigsten 10 an:
- `accounting`
- `invoicing`
- `germany`
- `open-source`
- `offline-first`
- `datev`
- `python`
- `react`
- `freelance`
- `buchhaltung`

### **Schritt 5: Optionen setzen**

Im selben Dialog:

**Releases:**
- ☑️ **"Releases"** (aktiviert lassen für später)

**Packages:**
- ☐ Packages (vorerst nicht relevant)

**Deployments:**
- ☐ Deployments (vorerst nicht relevant)

→ Klicke **"Save changes"**

---

## 💬 Teil 2: Discussions aktivieren

### **Schritt 1: Zu Settings gehen**

1. Im Repository, klicke oben auf **"Settings"** (ganz rechts)
2. Falls du keinen Zugriff hast: Du musst Owner oder Admin sein

### **Schritt 2: Features aktivieren**

1. Links in der Sidebar: **"General"** (sollte schon ausgewählt sein)
2. Scrolle runter zu **"Features"**
3. Finde **"Discussions"**
4. ☑️ **Häkchen setzen bei "Discussions"**
5. Klicke **"Set up discussions"** (grüner Button erscheint)

### **Schritt 3: Erste Discussion erstellen**

GitHub leitet dich automatisch weiter:

1. Es öffnet sich ein Editor mit einer Template-Discussion
2. **Lösche den Template-Text**
3. **Kopiere stattdessen Version 1** aus `community-ankuendigung.md`

**Titel:**
```
Willkommen bei RechnungsFee - Lass uns gemeinsam etwas Großartiges bauen! 🚀
```

**Text:** (aus community-ankuendigung.md, Version 1)

4. Wähle Kategorie: **"Announcements"**
5. Klicke **"Start discussion"**

### **Schritt 4: Discussion pinnen**

1. In der erstellten Discussion, klicke rechts auf **"⋮" (3 Punkte)**
2. Wähle **"Pin discussion"**
3. Die Discussion erscheint jetzt ganz oben

### **Schritt 5: Discussion-Kategorien anpassen** (Optional)

1. Gehe zu: **Discussions** → **"Categories"** (oben rechts, Zahnrad)
2. Standardmäßig gibt es:
   - 📣 Announcements
   - 💡 Ideas
   - 🙏 Q&A
   - 💬 General
   - 🙌 Show and tell

**Empfohlene Anpassungen:**

**Neue Kategorie erstellen:**
- **Name:** "🐛 Bugs & Issues"
- **Beschreibung:** "Bugs melden die noch nicht in Issues sind"
- **Format:** Discussion

Oder einfach die Standard-Kategorien behalten - sie passen gut!

---

## 🏷️ Teil 3: Issues-Labels erstellen

### **Schritt 1: Zu Issues gehen**

1. Klicke oben auf **"Issues"**
2. Klicke rechts auf **"Labels"**

### **Schritt 2: Standardlabels prüfen**

GitHub erstellt automatisch:
- `bug`
- `documentation`
- `duplicate`
- `enhancement`
- `good first issue`
- `help wanted`
- `invalid`
- `question`
- `wontfix`

**→ Diese sind schon gut!**

### **Schritt 3: Zusätzliche Labels erstellen** (Optional)

Klicke **"New label"** und erstelle:

| Name | Beschreibung | Farbe |
|------|-------------|-------|
| `priority: high` | Hohe Priorität | `#D93F0B` (Rot) |
| `priority: medium` | Mittlere Priorität | `#FBCA04` (Gelb) |
| `priority: low` | Niedrige Priorität | `#0E8A16` (Grün) |
| `area: backend` | Backend (Python/FastAPI) | `#1D76DB` (Blau) |
| `area: frontend` | Frontend (React) | `#91C4F2` (Hellblau) |
| `area: database` | Datenbank (SQLite) | `#5319E7` (Lila) |
| `area: docs` | Dokumentation | `#0075CA` (Blau) |
| `type: feature` | Neues Feature | `#A2EEEF` (Cyan) |
| `type: refactor` | Code-Refactoring | `#F9D0C4` (Beige) |
| `status: wip` | Work in Progress | `#FBCA04` (Gelb) |
| `status: blocked` | Blockiert | `#D93F0B` (Rot) |
| `needs: review` | Braucht Review | `#FBCA04` (Gelb) |

**→ Vorerst nicht nötig!** Kannst du später machen wenn Issues kommen.

---

## 🖼️ Teil 4: Social Preview-Image (Optional)

GitHub zeigt ein Preview-Bild wenn du den Link auf Social Media teilst.

### **Option A: Automatisches Bild (Standard)**

GitHub generiert automatisch ein Bild aus:
- Repository-Name
- Beschreibung
- Owner-Avatar

→ Reicht vorerst!

### **Option B: Eigenes Bild hochladen**

1. Gehe zu **Settings** → **General**
2. Scrolle zu **"Social preview"**
3. Klicke **"Upload an image"**
4. Bild hochladen (empfohlen: 1280x640px)

**Tipp:** Erstelle eine Grafik in Canva:
- Text: "RechnungsFee - Open Source Buchhaltung"
- Untertitel: "Für Selbstständige & Freiberufler"
- Logo/Icon (wenn vorhanden)
- Größe: 1280x640px

→ **Kannst du später machen** wenn du ein Logo hast!

---

## ✅ Teil 5: README-Badge aktualisieren

Die README hat bereits Badges. Prüfe ob sie funktionieren:

```markdown
[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![Status](https://img.shields.io/badge/Status-In_Development-yellow)](https://github.com/nicolettas-muggelbude/RechnungsFee)
```

**Zusätzliche Badges (optional):**

```markdown
[![GitHub stars](https://img.shields.io/github/stars/nicolettas-muggelbude/RechnungsFee?style=social)](https://github.com/nicolettas-muggelbude/RechnungsFee/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/nicolettas-muggelbude/RechnungsFee)](https://github.com/nicolettas-muggelbude/RechnungsFee/issues)
[![GitHub discussions](https://img.shields.io/github/discussions/nicolettas-muggelbude/RechnungsFee)](https://github.com/nicolettas-muggelbude/RechnungsFee/discussions)
```

→ **Vorerst nicht nötig**, kannst du später hinzufügen!

---

## 📊 Teil 6: Repository Insights einrichten (Optional)

### **Community Standards prüfen:**

1. Gehe zu **Insights** (oben im Menü)
2. Links: **"Community"**
3. Prüfe Checkliste:

**Sollte schon ✅ sein:**
- [x] Description
- [x] README
- [x] License
- [x] Contributing guidelines

**Optional (später):**
- [ ] Code of conduct (später aus CONTRIBUTING.md extrahieren)
- [ ] Issue templates (für strukturierte Bug-Reports)
- [ ] Pull request template

---

## 🎯 Checkliste - Was du jetzt tun solltest:

### **Priorität 1 (Jetzt, 5 Minuten):**

- [ ] About-Sektion: Beschreibung eintragen
- [ ] Topics hinzufügen (mindestens 10)
- [ ] Discussions aktivieren
- [ ] Erste Discussion posten (Willkommens-Post)
- [ ] Discussion pinnen

### **Priorität 2 (Optional, später):**

- [ ] Zusätzliche Issue-Labels erstellen
- [ ] Social Preview-Image hochladen
- [ ] Weitere Badges zur README
- [ ] Code of Conduct als separate Datei

### **Priorität 3 (Viel später):**

- [ ] GitHub Actions für CI/CD
- [ ] Issue-Templates
- [ ] PR-Templates
- [ ] GitHub Projects (Roadmap-Board)
- [ ] Website/GitHub Pages

---

## 📸 Screenshot-Guide (Was du sehen solltest)

### **After About-Bearbeitung:**

```
RechnungsFee
Public

Open-Source Buchhaltungssoftware für Freiberufler...

🏷️ accounting  invoicing  germany  open-source  ...

⭐ Star    👁️ Watch    🍴 Fork
```

### **After Discussions aktiviert:**

Im Top-Menü sollte erscheinen:
```
Code  Issues  Pull requests  Discussions  Actions  ...
```

### **Discussions-Seite:**

```
📌 Pinned

Willkommen bei RechnungsFee - Lass uns gemeinsam...
   💬 0  👍 0
```

---

## 🚀 Nach dem Setup - Nächste Schritte

**Jetzt kannst du:**

1. ✅ Den Discussions-Link teilen
2. ✅ Auf Social Media posten (mit Grafiken)
3. ✅ Community einladen
4. ✅ Erste Contributors begrüßen
5. ✅ Issues annehmen
6. ✅ Feedback sammeln

**Link zum Teilen:**
```
🚀 RechnungsFee ist jetzt live auf GitHub!

Open-Source Buchhaltung für Selbstständige.
Offline-first, datenschutzfreundlich, Made in Germany.

Schau vorbei & gib Feedback:
https://github.com/nicolettas-muggelbude/RechnungsFee

#OpenSource #Buchhaltung #Freiberufler
```

---

## ❓ Troubleshooting

**Problem: Ich sehe "Settings" nicht**
→ Du musst Owner/Admin des Repos sein. Bist du eingeloggt?

**Problem: Discussions erscheint nicht im Menü**
→ Warte ~1 Minute nach Aktivierung, dann Seite neu laden (F5)

**Problem: Kann keine Topics hinzufügen**
→ Du musst im "About"-Edit-Dialog sein (Zahnrad klicken)

**Problem: Discussion lässt sich nicht pinnen**
→ Nur in "Announcements"-Kategorie möglich, oder du brauchst Admin-Rechte

---

## ✅ Fertig!

Nach diesem Setup ist dein Repository:
- ✅ Professionell präsentiert
- ✅ Leicht zu finden (durch Topics)
- ✅ Community-freundlich (Discussions)
- ✅ Bereit für Contributors

**Viel Erfolg! 🚀**
