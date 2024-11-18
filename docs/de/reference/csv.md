
## Spalten

| Spalte                   | Beschreibung                                                          | Pflichtfeld      |
| ------------------------ | --------------------------------------------------------------------- | ---------------- |
| **ID Domäne**            | Eindeutige ID einer Domäne.                                           | :material-check: |
| **ID Bereich**           | Eindeutige ID eines Bereichs.                                         | :material-check: |
| **ID Unterbereich**      | Eindeutige ID eines Unterbereichs.                                    |                  |
| **ID Maschine**          | Eindeutige ID der Maschine.                                           | :material-check: |
| **Unterbereich Manager** | Erstellung einer Manager-Rolle für den dazugehörigen Unterbereich     |                  |
| **Name Bereich**         | Anzeigename des Bereichs.                                             | :material-check: |
| **Name Unterbereich**    | Anzeigename des Unterbereichs.                                        |                  |
| **Name Maschine**        | Anzeigename der Maschine.                                             | :material-check: |
| **Maschinbeschreibung**  | Feld `description` einer Maschine in FabAccess.                       |                  |
| **Wiki-URL**             | Feld `wiki` einer Maschine in FabAccess.                              |                  |
| **Aktor ID**             | Eindeutige ID eines Aktors.                                           |                  |
| **Aktor Typ**            | Definiert den Aktorentyp, der aus der Aktorenbibliothek geladen wird. |                  |
| **ID Alternativrolle**   | Eindeutige ID einer alternativen Rolle.                               |                  |
| **Name Alternativrolle** | Anzeigename einer alternativen Rolle.                                 |                  |
| **Anmerkungen**          | Feld für eigene Anmerkungen (Wird nicht vom Skript verarbeitet).                   |                  |


!!! tip "Anpassung der CSV an eigene Bedürfnisse"
    
    - Die Reihenfolge der Spalten kann nach Belieben angepasst werden.
    - Es können beliebig viele eigene Spalten angelegt werden, um Anmerkungen zu hinterlassen. Diese werden vom Skript nicht verarbeitet.


### Unterbereich Manager
- Für die Erstellung der Rolle muss ein Unterbereich  definiert sein.
- Das Feld wird aktiv sobald ein beliebiger Inhalt eingetragen wird.
- Das Feld muss nur für eine Maschine des Unterbereichs ausgefüllt werden.

## Erlaubte Zeichen
- Erlaubt sind Buchstaben und Zahlen.
- Alle Großbuchstaben werden automatisch in Kleinbuchstaben umgewandelt.
- Deutsche Sonderzeichen werden automatisch umgewandelt (ä = ae, ö = oe, ü = ue, ß = ss).
- Alle übrigen Zeichen/ Sonderzeichen werden automatisch entfernt.

## Technische Spezifikation der CSV
- Verwendetes CSV-Trennzeichen: `;`
- Kodierung: UTF-8-BOM
- Zeilenumbrüche: CRLF