# Bank-CSV Formate

Dieser Ordner enthält Beispiel-CSVs verschiedener Banken für die Import-Funktion.

---

## 🏦 Unterstützte Banken & Zahlungsdienste

### Geplant für MVP:

- [x] **Sparkasse** - Deutschlands größtes Bankennetz ✅
- [x] **Volksbank / Raiffeisenbank** - Genossenschaftsbanken ✅ (VR-Teilhaberbank)
- [ ] **Deutsche Bank** - Großbank
- [x] **Commerzbank** - Großbank ✅
- [ ] **Postbank** - Retail-Bank
- [x] **DKB (Deutsche Kreditbank)** - Online-Bank ✅
- [x] **ING (ehem. ING-DiBa)** - Online-Bank ✅
- [ ] **N26** - Mobile Bank
- [ ] **Comdirect** - Online-Bank
- [ ] **Consorsbank** - Online-Broker mit Girokonto
- [x] **PayPal** - Zahlungsdienstleister (wichtig für Online-Geschäft) ✅
- [x] **Targobank** ✅
- [x] **Sparda-Bank West eG** ✅

### Später:

- [ ] Santander
- [ ] HypoVereinsbank
- [ ] PSD Bank
- [ ] Sparda-Bank (weitere Regionalbanken)
- [ ] Tomorrow Bank
- [ ] Revolut
- [ ] C24
- [ ] Trade Republic (mit Girokonto)

---

## 📂 Ordnerstruktur

```
bank-csv/
├── README.md                              # Diese Datei
├── TEMPLATE.md                            # Vorlage und Anonymisierungs-Anleitung
├── sparkasse-lzo-mt940.csv                # ✅ Sparkasse/LZO - MT940 Format
├── sparkasse-lzo-camt-v2.csv              # ✅ Sparkasse/LZO - CAMT V2 Format
├── sparkasse-lzo-camt-v8.csv              # ✅ Sparkasse/LZO - CAMT V8 Format
├── paypal.csv                             # ✅ PayPal Aktivitätsbericht
├── commerzbank.csv                        # ✅ Commerzbank - Umsatzübersicht
├── dkb.csv                                # ✅ DKB - Girokonto Export
├── ing.csv                                # ✅ ING - Umsatzanzeige (ohne Saldo)
├── ing-mit-saldo.csv                      # ✅ ING - Umsatzanzeige (mit Saldo)
├── targobank-duesseldorf.csv              # ✅ Targobank - CSV (Komma-Dezimaltrennzeichen)
├── targobank-duesseldorf-variation.csv    # ✅ Targobank - CSV (Punkt-Dezimaltrennzeichen)
├── targobank-duesseldorf.qif              # ✅ Targobank - QIF Format (Quicken)
├── targobank-duesseldorf.xlsx             # ✅ Targobank - Excel Format
├── vr-teilhaberbank.csv                   # ✅ VR-Teilhaberbank - CSV-Export
├── vr-teilhaberbank.mta                   # ✅ VR-Teilhaberbank - MT940 Format
├── sparda-bank-west.csv                   # ✅ Sparda-Bank West eG - CSV-Export
├── volksbank.csv                          # (noch nicht vorhanden)
├── n26.csv                                # (noch nicht vorhanden)
└── ...
```

**Hinweis:** Manche Banken bieten mehrere Export-Formate an (z.B. MT940, CAMT).
In diesem Fall erstellen wir separate Dateien pro Format.

---

## 🤝 Mitmachen

### Deine Bank fehlt?

**Du kannst helfen!**

1. 📥 **Exportiere** CSV aus deinem Online-Banking
2. 🔒 **Anonymisiere** sensible Daten (siehe [TEMPLATE.md](TEMPLATE.md))
3. 📝 **Erstelle** ein [GitHub Issue](../../.github/ISSUE_TEMPLATE/bank-csv-format.md)
4. 📎 **Hänge** die anonymisierte CSV an
5. ✅ **Fertig!** Wir fügen sie hinzu

**Schritt-für-Schritt-Anleitung:** [CONTRIBUTING.md](../../CONTRIBUTING.md#bank-csv-format-beitragen)

---

## 🔍 Format-Unterschiede

Jede Bank hat ihr eigenes CSV-Format. Typische Unterschiede:

| Aspekt | Varianten |
|--------|-----------|
| **Trennzeichen** | `;` (Semikolon), `,` (Komma), `\t` (Tab) |
| **Encoding** | UTF-8, ISO-8859-1, Windows-1252 |
| **Dezimaltrennzeichen** | `,` (1.234,56) oder `.` (1,234.56) |
| **Datumsformat** | DD.MM.YYYY, YYYY-MM-DD, MM/DD/YYYY |
| **Anführungszeichen** | `"..."`, `'...'`, keine |
| **Header-Zeilen** | 0, 1, oder mehrere |
| **Fußzeilen** | Summen, Saldo, Metadaten |
| **Spaltenanzahl** | 5-15+ Spalten |
| **Besonderheiten** | Mehrzeilig, HTML, Sonderzeichen |

**RechnungsFee wird alle gängigen Formate unterstützen!**

---

## 🔄 Mehrere Formate pro Bank

Manche Banken bieten verschiedene Export-Formate an:

### **MT940 (SWIFT Message Type 940)**
- Standard-Format für elektronische Kontoauszüge
- Ursprünglich für SWIFT-Nachrichten entwickelt
- Viele Sparkassen und Banken bieten CSV-Export im MT940-Format
- **Beispiel:** `sparkasse-lzo-mt940.csv`

### **CAMT (Cash Management - ISO 20022)**
- Moderner Standard für Zahlungsverkehr
- ISO 20022 XML-basiert, aber einige Banken bieten CSV-Varianten
- **Versionen:** V2, V8 (unterschiedliche Schema-Versionen)
- **Beispiel:** `sparkasse-lzo-camt-v2.csv`, `sparkasse-lzo-camt-v8.csv`

### **Andere Formate**
- **Eigenformate** - Bank-spezifische CSV-Strukturen
- **SEPA PAIN** - Payment Initiation (selten als CSV)
- **Umsatzliste** - Vereinfachte Formate für Privatkunden

**Namenskonvention bei mehreren Formaten:**
```
<bank>-<format>.csv         # Bei einem Format
<bank>-<format>-<version>.csv  # Bei mehreren Versionen
```

**Beispiele:**
- `sparkasse-lzo-mt940.csv`
- `sparkasse-lzo-camt-v2.csv`
- `dkb-standard.csv` (wenn nur ein Format)
- `volksbank-mt940.csv`

---

## 🛠️ Für Entwickler

### Import-Parser-Implementierung:

```python
# Beispiel: Sparkasse-Parser
class SparkasseCSVParser:
    delimiter = ';'
    encoding = 'ISO-8859-1'
    date_format = '%d.%m.%Y'
    decimal_sep = ','

    column_mapping = {
        'Buchungstag': 'datum',
        'Auftraggeber/Empfänger': 'partner',
        'Verwendungszweck': 'verwendungszweck',
        'Betrag': 'betrag',
        'Währung': 'waehrung',
    }
```

### Test-Fixtures:

```python
# tests/test_bank_import.py
import pytest
from bank_import import parse_bank_csv

def test_sparkasse_import():
    result = parse_bank_csv('vorlagen/bank-csv/sparkasse.csv', 'sparkasse')
    assert len(result) > 0
    assert result[0]['betrag'] is not None
```

---

## 📋 Format-Spezifikationen

### DKB (Deutsche Kreditbank)
**Datei:** `dkb.csv`

- **Trennzeichen:** `;` (Semikolon)
- **Encoding:** UTF-8 mit BOM
- **Dezimaltrennzeichen:** `,` (Komma)
- **Datumsformat:** DD.MM.YY
- **Header ab Zeile:** 5 (Zeilen 1-4: Metadaten)
- **Spalten:** Buchungsdatum, Wertstellung, Status, Zahlungspflichtige*r, Zahlungsempfänger*in, Verwendungszweck, Umsatztyp, IBAN, Betrag (€), Gläubiger-ID, Mandatsreferenz, Kundenreferenz
- **Besonderheiten:**
  - Metadaten in ersten Zeilen (Kontotyp, IBAN, Kontostand vom XX.XX.XXXX)
  - Geschlechtergerechte Spaltenbezeichnungen (`*in`)
  - Beträge in Anführungszeichen

### ING (ehem. ING-DiBa)
**Dateien:** `ing.csv` (ohne Saldo), `ing-mit-saldo.csv` (mit Saldo)

- **Trennzeichen:** `;` (Semikolon)
- **Encoding:** ISO-8859-1 / Windows-1252
- **Dezimaltrennzeichen:** `,` (Komma)
- **Datumsformat:** DD.MM.YYYY
- **Header ab Zeile:** 13 (ohne Saldo) bzw. 14 (mit Saldo)
- **Spalten:** Buchung, Wertstellungsdatum, Auftraggeber/Empfänger, Buchungstext, Verwendungszweck, Betrag, Währung
- **Besonderheiten:**
  - Umfangreiche Metadaten in Zeilen 1-12/13:
    - Zeile 1: "Umsatzanzeige;Datei erstellt am: ..."
    - Zeile 3-7: IBAN, Kontoname, Bank, Kunde, Zeitraum
    - Zeile 8: Saldo (nur in `ing-mit-saldo.csv`)
  - Zwei Varianten: mit und ohne Saldo-Zeile

### Targobank Düsseldorf
**Dateien:** `targobank-duesseldorf.csv`, `targobank-duesseldorf-variation.csv`, `targobank-duesseldorf.qif`, `targobank-duesseldorf.xlsx`

#### CSV-Variante 1 (Komma-Dezimal)
**Datei:** `targobank-duesseldorf.csv`

- **Trennzeichen:** `;` (Semikolon)
- **Encoding:** UTF-8
- **Dezimaltrennzeichen:** `,` (Komma)
- **Datumsformat:** DD.MM.YYYY
- **Header:** KEINE Header-Zeile!
- **Spalten (implizit):** Datum, Buchungstext, Betrag, [4 leere Spalten], IBAN
- **Besonderheiten:**
  - KEINE Spaltenüberschriften
  - Sehr ausführlicher Buchungstext mit allen Details in einem Feld
  - Eigene IBAN am Ende jeder Zeile in Anführungszeichen

#### CSV-Variante 2 (Punkt-Dezimal)
**Datei:** `targobank-duesseldorf-variation.csv`

- Identisch zu Variante 1, aber:
- **Dezimaltrennzeichen:** `.` (Punkt) statt `,` (Komma)
- Beispiel: `-5.00` statt `-5,00`

#### QIF-Format (Quicken Interchange Format)
**Datei:** `targobank-duesseldorf.qif`

- **Format:** QIF (Textbasiert)
- **Tags:**
  - `!Type:Bank` = Kontotyp
  - `D` = Datum (DD.MM.YY)
  - `T` = Betrag (Transaction Amount)
  - `P` = Payee (Buchungsbeschreibung)
  - `^` = Transaktionsende
- **Besonderheiten:**
  - Klassisches Import-Format für Quicken/GnuCash/MoneyMoney
  - Jede Transaktion endet mit `^`

#### Excel-Format
**Datei:** `targobank-duesseldorf.xlsx`

- **Format:** Excel-Arbeitsmappe (binär)
- Enthält wahrscheinlich gleiche Daten wie CSV-Varianten

### VR-Teilhaberbank (Volksbank/Raiffeisenbank)
**Dateien:** `vr-teilhaberbank.csv`, `vr-teilhaberbank.mta`

#### CSV-Export
**Datei:** `vr-teilhaberbank.csv`

- **Trennzeichen:** `;` (Semikolon)
- **Encoding:** UTF-8 mit BOM
- **Dezimaltrennzeichen:** `,` (Komma)
- **Datumsformat:** DD.MM.YYYY
- **Header ab Zeile:** 1
- **Spalten:** Bezeichnung Auftragskonto, IBAN Auftragskonto, BIC Auftragskonto, Bankname Auftragskonto, Buchungstag, Valutadatum, Name Zahlungsbeteiligter, IBAN Zahlungsbeteiligter, BIC (SWIFT-Code) Zahlungsbeteiligter, Buchungstext, Verwendungszweck, Betrag, Waehrung, Saldo nach Buchung, Bemerkung, Gekennzeichneter Umsatz, Glaeubiger ID, Mandatsreferenz
- **Besonderheiten:**
  - Sehr umfangreich: 18 Spalten
  - Enthält Saldo nach jeder Buchung
  - Vollständige SEPA-Informationen (Gläubiger-ID, Mandatsreferenz)

#### MT940-Format
**Datei:** `vr-teilhaberbank.mta`

- **Format:** MT940 (SWIFT Message Type 940)
- **Textbasiert** mit strukturierten Tags:
  - `:20:` = Transaktionsreferenz
  - `:25:` = Kontonummer
  - `:60F:` = Anfangssaldo
  - `:61:` = Buchungszeile
  - `:86:` = Buchungsdetails
  - `:62F:` = Endsaldo
- **Besonderheiten:**
  - Standard-Format für elektronische Kontoauszüge
  - Mehrere Transaktionsblöcke, getrennt durch `-`
  - Nicht CSV, sondern SWIFT-Nachrichtenformat

### Commerzbank
**Datei:** `commerzbank.csv`

- **Trennzeichen:** `;` (Semikolon)
- **Encoding:** UTF-8 mit BOM
- **Dezimaltrennzeichen:** `,` (Komma)
- **Datumsformat:** DD.MM.YYYY
- **Header ab Zeile:** 1
- **Spalten:** Buchungstag, Wertstellung, Umsatzart, Buchungstext, Betrag, Währung, IBAN Kontoinhaber, Kategorie
- **Besonderheiten:**
  - Sehr lange Buchungstexte mit vielen Details
  - Kategorie-Feld (meist leer)
  - Teilweise informative Zeilen (z.B. AGB-Änderungen) mit Betrag 0

### Sparda-Bank West eG
**Datei:** `sparda-bank-west.csv`

- **Trennzeichen:** `;` (Semikolon)
- **Encoding:** UTF-8 mit BOM
- **Dezimaltrennzeichen:** `,` (Komma)
- **Datumsformat:** DD.MM.YYYY
- **Header ab Zeile:** 1
- **Spalten:** Bezeichnung Auftragskonto, IBAN Auftragskonto, BIC Auftragskonto, Bankname Auftragskonto, Buchungstag, Valutadatum, Name Zahlungsbeteiligter, IBAN Zahlungsbeteiligter, BIC (SWIFT-Code) Zahlungsbeteiligter, Buchungstext, Verwendungszweck, Betrag, Währung, Saldo nach Buchung, Bemerkung, Gekennzeichneter Umsatz, Gläubiger ID, Mandatsreferenz
- **Besonderheiten:**
  - Identische Struktur wie VR-Teilhaberbank (Genossenschaftsbank)
  - 18 Spalten mit vollständigen SEPA-Informationen
  - Enthält Saldo nach jeder Buchung
  - Gläubiger-ID und Mandatsreferenz bei Lastschriften

---

## 📊 Status-Übersicht

| Bank/Dienst | Format | Datei vorhanden | Parser implementiert | Getestet |
|-------------|--------|-----------------|----------------------|----------|
| Sparkasse/LZO | MT940 CSV | ✅ | ❌ | ❌ |
| Sparkasse/LZO | CAMT V2 | ✅ | ❌ | ❌ |
| Sparkasse/LZO | CAMT V8 | ✅ | ❌ | ❌ |
| PayPal | Aktivitätsbericht | ✅ | ❌ | ❌ |
| Commerzbank | Umsatzübersicht CSV | ✅ | ❌ | ❌ |
| DKB | Girokonto CSV | ✅ | ❌ | ❌ |
| ING | Umsatzanzeige (ohne Saldo) | ✅ | ❌ | ❌ |
| ING | Umsatzanzeige (mit Saldo) | ✅ | ❌ | ❌ |
| Targobank | CSV (Komma-Dezimal) | ✅ | ❌ | ❌ |
| Targobank | CSV (Punkt-Dezimal) | ✅ | ❌ | ❌ |
| Targobank | QIF Format | ✅ | ❌ | ❌ |
| Targobank | Excel (.xlsx) | ✅ | ❌ | ❌ |
| VR-Teilhaberbank | CSV-Export | ✅ | ❌ | ❌ |
| VR-Teilhaberbank | MT940 (.mta) | ✅ | ❌ | ❌ |
| Sparda-Bank West eG | CSV-Export | ✅ | ❌ | ❌ |
| Volksbank | - | ❌ | ❌ | ❌ |
| N26 | - | ❌ | ❌ | ❌ |

**Legende:**
- ✅ Vorhanden
- ⏳ Geplant
- ❌ Noch offen

**Hilf mit, diese Tabelle mit ✅ zu füllen!**

---

## 🔐 Datenschutz

**WICHTIG:** Alle CSV-Dateien in diesem Ordner enthalten **nur anonymisierte Beispieldaten**!

- ❌ Keine echten Kontonummern / IBANs
- ❌ Keine echten Namen
- ❌ Keine sensiblen Verwendungszwecke
- ✅ Nur Format-Beispiele zur Entwicklung

**Falls versehentlich echte Daten committed wurden:**
1. Sofort Issue erstellen
2. History bereinigen (git filter-branch / BFG Repo-Cleaner)
3. Force-Push auf allen Branches

---

## 📚 Weitere Ressourcen

- [TEMPLATE.md](TEMPLATE.md) - Anonymisierungs-Vorlage
- [Issue Template](../../.github/ISSUE_TEMPLATE/bank-csv-format.md) - Bank-CSV einreichen
- [CONTRIBUTING.md](../../CONTRIBUTING.md) - Contribution Guidelines
- [claude.md](../../claude.md) - Kategorie 5: Bank-Integration (Details)
