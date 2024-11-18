## multi_domains
Verwendung mehrer Domänen. Es wird automatisch eine Manager-Rolle für jede Domäne erstellt.

**Zulässige Werte**: True, False

## manager_schichtleitung
Rolle "Schichtleitung" erstellen, die über Manager-Berechtigungen für alle Domänen verfügt.                   

**Zulässige Werte**: True, False

## manager_area
Manager-Rolle für jeden Bereich erstellen.                                                                    

**Zulässige Werte**: True, False

## manager_subarea
Unterbereich Manager erstellen.                                     

**Zulässige Werte**: True, False

## fa_update_dhall
Automatische Aktualisierung einer bestehenden `bffh.dhall`-Datei.                                                   

**Zulässige Werte**: True, False

## fa_dhall_file
Vollständiger Pfad zur `bffh.dall`-Datei.

**Zulässige Werte**: Text

Beispielwerte:

- D:\FabAccess\config\bffh\bffh.dhall
- /home/fabaccess/bffh/bffh.dhall

## generate_mermaid
Mermaid-Code erzeugen, der Bereiche und Rolle in einem Diagramm abbildet.

Ausgabe erfolgt in die Datei `mermaid-code.txt`. Der enthaltene Code kann auf [mermaid.live](https://mermaid.live/) eingefügt werden, um das Diagramm als Grafik zu speichern.

**Zulässige Werte**: True, False

## create_file_roles
Ausgabe aller Rollen (Name der Rolle, Rollen-ID in FabAccess) als `roles.csv`.

**Zulässige Werte**: True, False

## show_machines
Alle importierten Maschinen-Daten anzeigen.                                                                   

**Zulässige Werte**: True, False

## show_roles
Alle erzeugten Rollen-Daten anzeigen.                                                                         

**Zulässige Werte**: True, False

## string_adminhandle
Kennzeichnung von Administrator-Rollen im Anzeigename. Der String wird dem Namen der Rolle vorangestellt.

**Zulässige Werte**: Text
Standardwert: Admin

## string_managerhandle
Kennzeichnung für Manager-Rollen, steht am Anfang des Namens der Rolle.

**Zulässige Werte**: Text
Standardwert: Manager

## string_userhandle
Kennzeichnung von Benutzer-Rollen im Anzeigename. Der String wird dem Namen der Rolle vorangestellt.

**Zulässige Werte**: Text
Standardwert: Benutzer