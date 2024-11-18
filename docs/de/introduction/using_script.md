
## Ausführen des Config Generators

- Der Config Generator wird mittels Python ausgeführt: `python config-generator.py`
- Die Datei `maschinenliste.csv` muss sich im selben Verzeichnis liegen wie das obige Python-Skript.
- Alle erzeugten Daten werden im Unterordner `output` abgelegt.


## Weitere Funktionen

Alle genannten Funktionen werden über die jeweiligen Einträge in der `settings.ini` aktiviert/ deaktiviert.

!!! info

    Es wird empfohlen die Referenz `CSV-Datei` zu lesen.

### Manager-Rollen erzeugen

Bei Bedarf können automatisch Manger-Rollen für die Domäne, Bereiche und Unterbereiche erzeugt werden.

- Die entsprechenden Einstellungen lauten `manager_schichtleitung`, `manager_area`, `manager_subarea`


### Automatische Aktualisierung einer bestehenden FabAccess-Konfiguration

Bei Bedarf kann die `bffh.dhall` automatisch aktualisiert werden. Hierfür ist es notwendig die Datei mit Platzhaltern zu versehen.

Dieser Vorgang funktioniert wie folgt:

- Das Skript liest die `bffh.dhall` zeilenweise aus.
- Dabei werden alle vom Skript erzeugten Daten werden zwischen den Platzhaltern `-- ||| GENERATOR START` und `-- ||| GENERATOR END` eingefügt. Bestehende Inhalte zwischen diesen Platzhaltern werden ignoriert.
- Die Datei `bffh.dhall` wird am Ende vollständig neu geschrieben.

!!! tip

    Backups anlegen verschafft Gelassenheit.


### Diagrammerstellung

Bei Bedarf kann ein Diagramm erzeugt werden, welche die Werkstatt mit allen Maschinen und Rollen abbildet. Hierbei wird zunächst nur Mermaid-Code für ein Diagramm erzeugt, welcher mit wenigen Schritten in ein Bild umgewandelt werden kann.

- Die enstprechende Einstellung lautet `generate_mermaid`.
- Der Mermaid-Code wird in der Datei `mermaid-code.txt` abgelegt.
- Eine Bilddatei kann mittels [mermaid.live](https://mermaid.live) erzeugt.
    1. Mermaid-Code links im Feld `code` einfügen
    2. Links im Tab *Actions* das gewünschte Bildformat auswählen.

### Liste aller Rollen

Bei Bedarf kann eine Liste aller Rollen (inkl. deren interner IDs) erzeugt werden.

- Die enstprechende Einstellung lautet `create_file_roles`.
- Der Liste wird in der Datei `roles.csv` abgelegt.