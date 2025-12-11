---
name: Bank-Export-Format einreichen
about: Hilf mit, deine Bank zu unterstützen (CSV, MT940, CAMT, etc.)
title: 'Bank-Export: [Bankname] - [Format]'
labels: 'enhancement, bank-integration'
assignees: ''
---

## 🏦 Bank-Informationen

**Bankname:** [z.B. Sparkasse Musterstadt, Volksbank eG, DKB, ING]
**Export-Format:** [CSV / MT940 / CAMT.053 / Anderes]
**Export-Typ:** [z.B. "Umsätze CSV", "Kontoauszug MT940", "CAMT V8"]
**Online-Banking URL:** [Optional, z.B. sparkasse.de]

---

## 📁 Format-Typ

Bitte wähle das Format deiner Datei:

- [ ] **CSV** (Comma/Semicolon Separated Values)
- [ ] **MT940** (SWIFT Message Type 940 - oft .sta, .mta, .txt)
- [ ] **CAMT.053** (ISO 20022 XML - oft .xml)
- [ ] **Anderes:** [Bitte Format angeben]

---

## 📋 Format-Details

### **Wenn CSV:**

**Trennzeichen:** [z.B. Semikolon (;), Komma (,), Tabulator]
**Encoding:** [z.B. UTF-8, ISO-8859-1, Windows-1252]
**Dezimaltrennzeichen:** [z.B. Komma (1.234,56) oder Punkt (1,234.56)]
**Datumsformat:** [z.B. DD.MM.YYYY, YYYY-MM-DD]

**Spalten (in Reihenfolge):**
1. [z.B. Buchungstag]
2. [z.B. Valuta]
3. [z.B. Auftraggeber/Empfänger]
4. [z.B. Verwendungszweck]
5. [z.B. Betrag]
6. [...]

### **Wenn MT940:**

**Dateiendung:** [z.B. .sta, .mta, .txt, .940]
**Encoding:** [z.B. UTF-8, ISO-8859-1]

**Enthält typischerweise:**
```
:20:STARTUMSE
:25:DE89370400440532013000
:28C:00001/001
:60F:C251201EUR15170,95
:61:251201C175,00NMSCNONREF//GUTSCHRIFT
:86:166?00GUTSCHRIFT?10123
:62F:C251201EUR14846,94
```

**Besonderheiten:** [z.B. zusätzliche Felder, proprietäre Erweiterungen]

### **Wenn CAMT.053 (XML):**

**Dateiendung:** [z.B. .xml]
**Schema-Version:** [z.B. camt.053.001.02, camt.053.001.08]
**Root-Element:** [z.B. `<Document xmlns="urn:iso:std:iso:20022:tech:xsd:camt.053.001.02">`]

**Besonderheiten:** [z.B. spezielle Namespaces, zusätzliche Felder]

### **Wenn anderes Format:**

**Dateiendung:** [z.B. .txt, .dat]
**Format-Beschreibung:** [Bitte beschreibe das Format so gut wie möglich]
**Dokumentation verfügbar?** [Link zur Bank-Doku falls vorhanden]

---

## 📎 Beispieldaten

Bitte hänge eine **anonymisierte** Datei an (CSV, MT940, CAMT, etc.).

### ⚠️ Anonymisierungs-Checkliste:

**Für alle Formate:**
- [ ] Kontonummer / IBAN entfernt oder ersetzt (z.B. durch `DE89370400440532013000`)
- [ ] BIC/SWIFT-Code anonymisiert (z.B. durch `GENODEF1XXX`)
- [ ] Echte Namen ersetzt durch Beispielnamen (`Max Mustermann`, `Firma GmbH`)
- [ ] Sensible Verwendungszwecke anonymisiert (`Gehalt`, `Miete`, `Einkauf Supermarkt`)
- [ ] Optional: Beträge anonymisiert (z.B. gerundet auf runde Zahlen)

**Speziell für CSV:**
- [ ] Header-Zeile (Spaltenköpfe) **NICHT** verändert
- [ ] CSV-Struktur (Trennzeichen, Format) **NICHT** verändert

**Speziell für MT940:**
- [ ] Tag-Struktur (:20:, :25:, etc.) **NICHT** verändert
- [ ] Nur Werte anonymisiert, Format beibehalten
- [ ] Mindestens 3-5 Buchungen als Beispiel

**Speziell für CAMT (XML):**
- [ ] XML-Struktur **NICHT** verändert
- [ ] Nur Text-Inhalte anonymisiert
- [ ] Namespaces und Schema-Referenzen beibehalten

**Tipp:** Siehe [Anleitung zur Anonymisierung](../../CONTRIBUTING.md#bank-csv-format-beitragen)

---

## 📊 Zusatzinformationen

**Besonderheiten:**
- [z.B. Header-Zeilen mit Metadaten, Fußzeilen mit Summen, Sonderzeichen]
- [z.B. Mehrzeilige Verwendungszwecke, HTML-Tags, etc.]

**Export-Häufigkeit:**
- [ ] Täglich verfügbar
- [ ] Wöchentlich
- [ ] Monatlich
- [ ] Nur auf Anfrage

**Export-Umfang:**
- [ ] Einzelnes Konto
- [ ] Alle Konten
- [ ] Mit Saldo/Kontostand
- [ ] Ohne Saldo

---

## 🙏 Danke für deinen Beitrag!

Deine Hilfe macht RechnungsFee besser für alle! 🚀
