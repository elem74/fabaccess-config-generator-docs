## multi_domains
Verwendung mehrer Domänen. Es wird automatisch eine Manager-Rolle für jede Domäne erstellt.

**Zulässige Werte**: True, False

##  domain_user
Erstellung einer Benutzerrolle für die gesamte Werkstatt. (Es werden keine Benutzerrollen für Unterbereiche/ Bereiche erstellt)

**Zulässige Werte**: True, False

## manager_domain
Manager-Rolle für die Domäne erstellen, die über Manager-Berechtigungen für alle Domänen verfügt.

**Zulässige Werte**: True, False

## manager_area
Manager-Rolle für jeden Bereich erstellen.                                                                    

**Zulässige Werte**: True, False

## manager_subarea
Unterbereich Manager erstellen.                                     

**Zulässige Werte**: True, False

## fa_dhall_directory
Definiert den Ordner, in dem die erzeugten DHALL-Dateien abgelegt werden. Wenn die Einstellung leer ist, dann werden die Dateien nur im Unterordner `output` abgelegt.

Vollständiger Pfad zum Ordner, der die `bffh.dall` beinhaltet.

**Zulässige Werte**: Pfad als Text
Standardwert: Kein Text

Beispielwerte:

- D:\FabAccess\config\bffh\bffh.dhall
- /home/fabaccess/bffh/bffh.dhall

## generate_mermaid
Mermaid-Code erzeugen, der Bereiche und Rolle in einem Diagramm abbildet.

Ausgabe erfolgt in die Datei `mermaid-code.txt`. Der enthaltene Code kann auf [mermaid.live](https://mermaid.live/) eingefügt werden, um das Diagramm als Grafik zu speichern.

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