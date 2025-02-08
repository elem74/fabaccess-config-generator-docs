
## Ausführen des Config Generators

- Der Config Generator wird mittels Python ausgeführt: `python config-generator.py`
- Die Datei `maschinenliste.csv` muss sich im selben Verzeichnis liegen wie das obige Python-Skript.
- Alle erzeugten Daten werden im Unterordner `output` abgelegt.

Standardgemäß werden die folgenden Dateien erzeugt:

| Datei                                                                   | Inhalt                                                                                               |
| ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| roles.dhall<br>machines.dhall<br>actors.dhall<br>actorconnections.dhall | DHALL-Dateien mit der erzeugten Konfiguration für Rollen, Maschinen, Aktoren und Aktorenverbindungen |
| bffh-dhall-data.txt                                                     | Erzeugte Konfiguration in einer einzelnen Datei                                                      |
| roles.csv                                                               | CSV-Datei mit einer Liste jeder Rolle (Klarname, FabAccess-ID)                                       |
| mermaid-code.txt                                                        | Mermaid-Code für ein Werkstattdiagramm                                                               |


### Automatisches Ablegen & Einbinden von DHALL-Dateien in FabAccess.

Auf Wunsch können die DHALL-Dateien automatisch im FabAccess-Ordner abgelegt und in die Konfiguration eingebunden werden. Hierfür sind zwei Schritte notwendig:

1. In der `settings.ini` bei der Einstellung `fa_dhall_directory` den Pfad hinterlegen, in dem sich die `bffh.dhall` befindet.
2. Die Datei `bffh.dhall` vorbereiten.

<br>
**bffh.dhall vorbereiten**

Die Einträge für roles, machines, actors und actor_connections müssen wie folgt aussehen:

```
roles = ./roles.dhall,
machines = ./machines.dhall,
actors = ./actors.dhall,
actor_connections = ./actorconnections.dhall,
```

Beim Start von FabAccess werden die einzelnen dhall-Dateien dann automatisch in die Konfigruation geladen.


!!! info
    Ein Vorlage für eine entsprechend angepasste `bffh.dhall` befindet sich im Unterordner `docs` des FabAccess Config Generator.


### CSV-Datei via Paramater festlegen

Mit dem Parameter `file=` kann der Name einer CSV-Datei übergeben werden.

**Beispiel**
`python config-generator.py file=meinemaschinenliste.csv`


## Weitere Funktionen

Alle genannten Funktionen werden über die jeweiligen Einträge in der `settings.ini` aktiviert/ deaktiviert.

!!! info

    Es wird empfohlen die Referenz `CSV-Datei` zu lesen.

### Manager-Rollen erzeugen

Bei Bedarf können automatisch Manger-Rollen für die Domäne, Bereiche und Unterbereiche erzeugt werden.

- Die entsprechenden Einstellungen lauten `manager_domain`, `manager_area`, `manager_subarea`


!!! tip

    Backups anlegen verschafft Gelassenheit.

### Vom Mermaid-Code zu einer Grafikdatei

1. Mermaid-Code aus der Datei `mermaid-code.txt` kopieren.
2. Die Website [mermaid.live](https://mermaid.live) aufrufen.
3. Mermaid-Code links im Feld `code` einfügen
4. Im Tab *Actions* das gewünschte Bildformat auswählen.

