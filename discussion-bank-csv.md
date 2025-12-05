# 🏦 Hilf mit: Bank-CSV Formate für Import-Funktion gesucht!

Hallo Community! 👋

RechnungsPilot soll Bank-Transaktionen automatisch importieren können – damit ihr nicht mehr jede Buchung manuell abtippen müsst. **Und dafür brauchen wir eure Hilfe!**

---

## 🤔 Warum brauchen wir das?

Jede Bank exportiert Kontoumsätze in ihrem eigenen CSV-Format:

- **Sparkasse** nutzt Semikolon (`;`) als Trennzeichen, ISO-8859-1 Encoding
- **DKB** nutzt Anführungszeichen (`"..."`), UTF-8 Encoding
- **N26** nutzt Komma (`,`), andere Spaltenköpfe
- **Volksbank** hat wieder andere Feldnamen

**RechnungsPilot muss alle diese Formate verstehen können!**

Dafür brauchen wir anonymisierte Beispiel-CSVs von möglichst vielen Banken.

---

## ✅ So kannst du helfen (10 Minuten):

### **Schritt 1: CSV exportieren**
1. Logge dich in dein Online-Banking ein
2. Gehe zu "Umsätze" oder "Kontobewegungen"
3. Exportiere als **CSV** (1 Monat mit 10-20 Transaktionen reicht)

### **Schritt 2: Anonymisieren** ⚠️ WICHTIG!
Ersetze sensible Daten (vollständige Anleitung siehe unten):

**❌ NICHT teilen:**
- IBAN → ersetze durch `DE89370400440532013000`
- Echte Namen → ersetze durch `Max Mustermann`
- Sensible Verwendungszwecke → allgemein formulieren

**✅ BEHALTEN (nicht ändern!):**
- Header-Zeile (Spaltenköpfe)
- Trennzeichen (Semikolon, Komma, etc.)
- Datumsformat
- CSV-Struktur

**Beispiel – Vorher (NICHT TEILEN!):**
```csv
Datum;Partner;Verwendungszweck;Betrag
01.12.2025;Schmidt, Peter;Miete Musterstr. 42;-850,00
```

**Beispiel – Nachher (OK zum Teilen):**
```csv
Datum;Partner;Verwendungszweck;Betrag
01.12.2025;Mustermann, Max;Miete;-850,00
```

### **Schritt 3: Einreichen**
1. Erstelle ein neues [GitHub Issue mit diesem Template](https://github.com/nicolettas-muggelbude/RechnungsPilot/issues/new?template=bank-csv-format.md)
2. Fülle die Felder aus (Bankname, Trennzeichen, Encoding, etc.)
3. Hänge die anonymisierte CSV an
4. **Fertig!** 🎉

📖 **Detaillierte Anleitung:** [CONTRIBUTING.md – Bank-CSV Format beitragen](https://github.com/nicolettas-muggelbude/RechnungsPilot/blob/main/CONTRIBUTING.md#-bank-csv-format-beitragen)

---

## 🏦 Welche Banken nutzt du?

Hilf uns herauszufinden, welche Banken Priorität haben sollten!

**Kommentiere gerne mit:**
- Welche Bank nutzt du? (z.B. Sparkasse, DKB, N26, ING, ...)
- Nutzt du mehrere Banken?
- Hast du bereits ein CSV exportiert?

### Geplante Unterstützung (MVP):
- [ ] Sparkasse
- [ ] Volksbank / Raiffeisenbank
- [ ] Deutsche Bank
- [ ] Commerzbank
- [ ] Postbank
- [ ] DKB (Deutsche Kreditbank)
- [ ] ING (ehem. ING-DiBa)
- [ ] N26
- [ ] Comdirect
- [ ] Consorsbank

**Deine Bank fehlt?** Umso wichtiger, dass du ein CSV beiträgst! 🚀

---

## 🙏 Warum ist das so wertvoll?

Jede Bank-CSV, die du beiträgst, hilft:

✅ **Hunderten anderen Usern** – die dieselbe Bank nutzen
✅ **Entwicklern** – realistische Test-Daten für die Import-Funktion
✅ **Dem Projekt** – schneller zur Version 1.0 zu kommen

**Du musst KEIN Programmierer sein** – diese Contribution ist perfekt für alle, die das Projekt unterstützen wollen! 💪

---

## 🔐 Datenschutz-Garantie

- **Alle CSV-Dateien werden geprüft** – keine echten Daten im Repository
- **Nur anonymisierte Beispiele** – nur Format-Informationen, keine echten Umsätze
- Falls versehentlich echte Daten committed werden → sofortige Git-History-Bereinigung

---

## ❓ Fragen?

- **Wie anonymisiere ich richtig?** → Siehe [TEMPLATE.md](https://github.com/nicolettas-muggelbude/RechnungsPilot/blob/main/vorlagen/bank-csv/TEMPLATE.md)
- **Welche Felder muss ich anonymisieren?** → Siehe [Anonymisierungs-Checkliste](https://github.com/nicolettas-muggelbude/RechnungsPilot/blob/main/CONTRIBUTING.md#schritt-2-anonymisieren-wichtig)
- **Kann ich mehrere Banken beitragen?** → Ja, sehr gerne! 🎉
- **Was passiert mit meinem CSV?** → Es wird in `vorlagen/bank-csv/` gespeichert und als Test-Fixture für die Import-Funktion genutzt

**Frag gerne hier in den Kommentaren!** 💬

---

## 📊 Status-Übersicht

Aktuelle Anzahl unterstützter Banken: **1 / 10+** 🎉

| Bank | Status |
|------|--------|
| ✅ Sparkasse/LZO | CSV vorhanden |
| ⏳ Volksbank | Noch offen |
| ⏳ DKB | Noch offen |
| ⏳ ING | Noch offen |
| ⏳ N26 | Noch offen |

**Die erste Bank ist dabei! Wer trägt die nächste bei?** 🚀

---

## 🚀 Los geht's!

**Deine Bank-CSV kann der erste Beitrag zu diesem Projekt sein!**

1. 📥 CSV exportieren
2. 🔒 Anonymisieren (10 Min.)
3. 📝 Issue mit Template erstellen
4. ✅ Done!

**Danke, dass du RechnungsPilot besser machst!** ❤️

---

*PS: Wenn du Feedback zum Anonymisierungs-Prozess hast (zu kompliziert? unklar?), schreib es gerne hier – wir verbessern die Anleitung dann entsprechend!* 🙂
