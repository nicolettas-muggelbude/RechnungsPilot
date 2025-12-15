# 🏦 Hilf mit: Bank-CSV Formate für Import-Funktion gesucht!

Hallo Community! 👋

RechnungsFee soll Bank-Transaktionen automatisch importieren können – damit ihr nicht mehr jede Buchung manuell abtippen müsst. **Und dafür brauchen wir eure Hilfe!**

---

## 🤔 Warum brauchen wir das?

Jede Bank exportiert Kontoumsätze in ihrem eigenen CSV-Format:

- **Sparkasse** nutzt Semikolon (`;`) als Trennzeichen, ISO-8859-1 Encoding
- **DKB** nutzt Anführungszeichen (`"..."`), UTF-8 Encoding
- **N26** nutzt Komma (`,`), andere Spaltenköpfe
- **Volksbank** hat wieder andere Feldnamen

**RechnungsFee muss alle diese Formate verstehen können!**

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
1. Erstelle ein neues [GitHub Issue mit diesem Template](https://github.com/nicolettas-muggelbude/RechnungsFee/issues/new?template=bank-csv-format.md)
2. Fülle die Felder aus (Bankname, Trennzeichen, Encoding, etc.)
3. Hänge die anonymisierte CSV an
4. **Fertig!** 🎉

📖 **Detaillierte Anleitung:** [CONTRIBUTING.md – Bank-CSV Format beitragen](https://github.com/nicolettas-muggelbude/RechnungsFee/blob/main/CONTRIBUTING.md#-bank-csv-format-beitragen)

---

## 🏦 Welche Banken nutzt du?

Hilf uns herauszufinden, welche Banken Priorität haben sollten!

**Kommentiere gerne mit:**
- Welche Bank nutzt du? (z.B. Sparkasse, DKB, N26, ING, ...)
- Nutzt du mehrere Banken?
- Hast du bereits ein CSV exportiert?

### Bereits unterstützt (MVP):
- [x] **Sparkasse** ✅ (3 Formate: MT940, CAMT V2, CAMT V8)
- [x] **Volksbank / Raiffeisenbank** ✅ (VR-Teilhaberbank: CSV + MT940)
- [x] **Commerzbank** ✅
- [x] **DKB (Deutsche Kreditbank)** ✅
- [x] **ING (ehem. ING-DiBa)** ✅ (2 Varianten)
- [x] **PayPal** ✅ (Aktivitätsbericht)
- [x] **Targobank** ✅ (4 Formate: CSV, QIF, XLSX)
- [x] **Sparda-Bank West eG** ✅

### Noch offen:
- [ ] Deutsche Bank
- [ ] Postbank
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

- **Wie anonymisiere ich richtig?** → Siehe [TEMPLATE.md](https://github.com/nicolettas-muggelbude/RechnungsFee/blob/main/vorlagen/bank-csv/TEMPLATE.md)
- **Welche Felder muss ich anonymisieren?** → Siehe [Anonymisierungs-Checkliste](https://github.com/nicolettas-muggelbude/RechnungsFee/blob/main/CONTRIBUTING.md#schritt-2-anonymisieren-wichtig)
- **Kann ich mehrere Banken beitragen?** → Ja, sehr gerne! 🎉
- **Was passiert mit meinem CSV?** → Es wird in `vorlagen/bank-csv/` gespeichert und als Test-Fixture für die Import-Funktion genutzt

**Frag gerne hier in den Kommentaren!** 💬

---

## 📊 Status-Übersicht

Aktuelle Anzahl unterstützter Banken: **10 Banken, 17+ Formate** 🎉

| Bank | Format | Status |
|------|--------|--------|
| ✅ Sparkasse/LZO | MT940 CSV | CSV vorhanden |
| ✅ Sparkasse/LZO | CAMT V2 | CSV vorhanden |
| ✅ Sparkasse/LZO | CAMT V8 | CSV vorhanden |
| ✅ PayPal | Aktivitätsbericht | CSV vorhanden |
| ✅ Commerzbank | Umsatzübersicht | CSV vorhanden |
| ✅ DKB | Girokonto CSV | CSV vorhanden |
| ✅ ING | Umsatzanzeige (ohne Saldo) | CSV vorhanden |
| ✅ ING | Umsatzanzeige (mit Saldo) | CSV vorhanden |
| ✅ Targobank | CSV (Komma-Dezimal) | CSV vorhanden |
| ✅ Targobank | CSV (Punkt-Dezimal) | CSV vorhanden |
| ✅ Targobank | QIF Format | QIF vorhanden |
| ✅ Targobank | Excel Format | XLSX vorhanden |
| ✅ VR-Teilhaberbank | CSV-Export | CSV vorhanden |
| ✅ VR-Teilhaberbank | MT940 Format | MTA vorhanden |
| ✅ Sparda-Bank West eG | CSV-Export | CSV vorhanden |
| ⏳ Volksbank | Standard-CSV | Noch offen |
| ⏳ N26 | - | Noch offen |
| ⏳ Postbank | - | Noch offen |
| ⏳ Deutsche Bank | - | Noch offen |
| ⏳ Comdirect | - | Noch offen |

**Wow! Schon 10 Banken mit 17+ verschiedenen Formaten dabei! 🚀**

**Hinweis:** Manche Banken bieten mehrere Export-Formate an (MT940, CAMT, QIF, XLSX). Du kannst gerne alle Formate beitragen, die deine Bank anbietet!

---

## 🚀 Los geht's!

**Deine Bank-CSV kann der erste Beitrag zu diesem Projekt sein!**

1. 📥 CSV exportieren
2. 🔒 Anonymisieren (10 Min.)
3. 📝 Issue mit Template erstellen
4. ✅ Done!

**Danke, dass du RechnungsFee besser machst!** ❤️

---

*PS: Wenn du Feedback zum Anonymisierungs-Prozess hast (zu kompliziert? unklar?), schreib es gerne hier – wir verbessern die Anleitung dann entsprechend!* 🙂
