
Im Kapitel Grundlagen wurde die CSV bereits auszugsweise gezeigt. Hier der grundsätzliche Umgang mit der CSV-Datei und die weiteren Felder der CSV-Datei erklärt anhand der einfachen Beispielwerkstatt erklärt.


## Grundsätzliches zur CSV


- Die CSV-Datei muss in einem bestimmten Format vorliegen. Es wird empfohlen eine Kopie der Beispieldatei anzulegen, um eine eigene Konfiguration zu erstellen.
- Bei der Vergabe von internen IDs für FabAccess (siehe unten) sind nicht alle Zeichen zulässig, daher nimmt der Config Generator automatisch eine Umwandlung vor.

Konkrete Angaben zu beiden Punkten befinden sich im Referenzbereich "*CSV-Datei*".

Bei Bedarf kann eine bestehende `bffh.dhall` importiert werden, siehe [hier](using_script.md#bestehende-bffhdhall-importieren-experimentell).


## Felder: Interne IDs
Um eine Maschine anzulegen werden Namen für die folgenden Elemente vergeben:

- Domäne
- Bereich
- ggf. Unterbereich
- Maschine
- ggf. Alternativrolle

Darüber hinaus werden für all diese Elemente auch IDs vergeben, die intern im FabAccess für die Bezeichnung der Maschinen/ Rollen verwendet. Auf diesem Wege werden zwei Welten abgedeckt:

- Für die FabAccess-App können ausführliche und gut beschreibende Namen vergeben werden.
- Für die FabAccess-Konfiguration könnten kompakte und schnell lesbare IDs vergeben werden.

=== "CSV-Daten (Auszug)"

     | <font color="Blue">Name Domäne</font> | <font color="purple">Name Bereich</font> | <font color="OrangeRed">Name Unterbereich</font> | Maschine/ Gerät   |     | <font color="Blue">ID Domäne</font> | <font color="purple">ID Bereich</font> | <font color="OrangeRed">ID Unterbereich</font> | ID Maschine |
     | ------------------------------------- | ---------------------------------------- | ------------------------------------------------ | ----------------- | --- | ----------------------------------- | -------------------------------------- | ---------------------------------------------- | ----------- |
     | Meine Werkstatt                       | Holz                                     |                                                  | Bandsäge          |     | mw                                  | holz                                   |                                                | bandsaege   |
     | Meine Werkstatt                       | Holz                                     |                                                  | Kreissäge         |     | mw                                  | holz                                   |                                                | kreissaege  |
     | Meine Werkstatt                       | Elektronik                               |                                                  | Lötkolben 1       |     | mw                                  | elektro                                |                                                | löt1        |
     | Meine Werkstatt                       | Elektronik                               |                                                  | Lötkolben 2       |     | mw                                  | elektro                                |                                                | löt2        |
     | Meine Werkstatt                       | Elektronik                               | 3D-Drucker                                       | 3D-Drucker "123"  |     | mw                                  | elektro                                | 3ddruck                                        | 123         |
     | Meine Werkstatt                       | Elektronik                               | 3D-Drucker                                       | 3D-Drucker "456"  |     | mw                                  | elektro                                | 3ddruck                                        | 456         |
     | Meine Werkstatt                       | Elektronik                               | Lasercutter                                      | Lasercutter "Abc" |     | mw                                  | elektro                                | laser                                          | Abc         |
     | Meine Werkstatt                       | Elektronik                               | Lasercutter                                      | Lasercutter "Def" |     | mw                                  | elektro                                | laser                                          | Def         |

=== "Erzeugte Maschinen-IDs"

    - mw-holz-bandsaege
    - mw-holz-kreissaege
    - mw-elektro-loet1
    - mw-elektro-loet2
    - mw-elektro-3ddruck-123
    - mw-elektro-3ddruck-456
    - mw-elektro-laser-abc
    - mw-elektro-laser-def


!!! info "Alternativrolle"

    Die Felder "Name Alternativrolle" und "ID Alternativrolle" verhalten sich analog zu den obigen Feldern und wurden aus Gründen der Übersicht ausgelassen.

## Felder: FabAccess-Infofelder

Die folgende Tabelle beschreibt, welche CSV-Spalten welchem FabAccess-Infofeld entspricht.

| CSV-Spalte            | FabAccess-Feld |
| --------------------- | -------------- |
| Maschinenbeschreibung | description    |
| Wiki-URL              | wiki           |


## Felder: Aktoren

Für die Aktoren werden lediglich diese Felder ausgefüllt:

| Feld      | Beschreibung                                                                                                                |
| --------- | --------------------------------------------------------------------------------------------------------------------------- |
| Aktor ID  | Hier wird die ID des jeweiligen Aktors angegeben. (Diese ID muss zunächst beim Aktor selbst eingestellt/ ausgelesen werden) |
| Aktor Typ | Hier wird ein Aktorentyp eingetragen, der in der Aktorenbibliothek angelegt ist.                                            |


!!! warning "Wichtiger Hinweis"

    Der Aktor Typ muss zuvor in der Aktorenbibliothek angelegt werden.


### Exkurs: Aktorenbibliothek

Bei der händischen Erstellung einer FabAccess-Konfiguration müssen (auch) für Aktoren viele Einträge angelegt werden, die sich nur minimal unterscheiden. Hier haben wir zum Beispiel drei Tasmota-Steckdosen, die sich nur beim Paramter `args` in ihrer ID unterscheiden:

=== "Tasmota Stecker 1"

    ```python
    {
    module = "Process",
        params =
        {
            cmd = "/usr/local/lib/bffh/adapters/tasmota/main.py",
            args = "--host mqtt --tasmota stecker1",
        }
    },
    ```

=== "Tasmota Stecker 2"

    ```python
    {
    module = "Process",
        params =
        {
            cmd = "/usr/local/lib/bffh/adapters/tasmota/main.py",
            args = "--host mqtt --tasmota stecker2",
        }
    },
    ```

=== "Tasmota Stecker 3"

    ```python
    {
    module = "Process",
        params =
        {
            cmd = "/usr/local/lib/bffh/adapters/tasmota/main.py",
            args = "--host mqtt --tasmota stecker6",
        }
    },
    ```

<br>
Um den Konfigurationsaufwand zu minimieren verwendet der Config Generator eine zentrale Aktorenbibliothek (Datei `actors.ini`). Hier wird für ein Aktor ein zentrales Schema hinterlegt.

<br>Für unseren Tasmota-Stecker sieht dies wie folgt aus:

```ini
[tasmota]
module = Process
param_cmd = "/usr/local/lib/bffh/adapters/tasmota/main.py"
param_args = "--host mqtt --tasmota $actor_id"
```

- Die eckigen Klammern definieren einen Aktor-Typ. Innerhalb der Klammern befindet sich der Name, der dann auch in der CSV eingetragen wird.
- Der Parameter `module` definiert das gleichnamige FabAccess-Konfigurationsfeld.
- Es können beliebig viele weitere Parameter angelegt werden. Diese müssen mit dem Präfix *param_* versehen werden, damit sie vom Config Generator erkannt und verarbeitet werden können.
- Die Zeichenkette `$actor_id` markiert den Platzhalter für die Geräte-ID. Hier wird automatisch die Aktor ID eingefügt, die in der CSV-Datei angegeben werden.

<br>
In der Praxis sieht unser Arbeitsweg wie folgt an:

1. Wir legen den Aktor-Typ einmaligen in der `actors.ini` an.
2. Wir füllen in der CSV-Datei bei unserer Maschine die Felder `Aktor Typ` und `Aktor ID` aus.
3. Der Config Generator erledigt den Rest.

