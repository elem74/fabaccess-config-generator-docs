## Bereiche

| Element                                            | Zweck                                                  | Beinhaltet Maschinen |
| -------------------------------------------------- | ------------------------------------------------------ | -------------------- |
| <font color="green"><b>Domäne</b></font>           | Die ganze Werkstatt.                                   | :material-close:     |
| <font color="purple"><b>Bereich</b></font>         | Bereiche einer Werkstatt (z.B. Holz, FabLab).          | :material-check:     |
| <font color="OrangeRed"><b>Unterbereich</b></font> | Unterbereich eines Bereichs (z.B. 3D-Druck im FabLab). | :material-check:     |


## Rollen

| Rolle           | Existiert                                                                                                                                                      | Berechtigungen                                           | Zugriffsschema                   |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- | -------------------------------- |
| Administrator   | - Global                                                                                                                                                       | bffh.users.manage<br>bffh.users.info<br>bffh.users.admin |                                  |
| Manager         | - <font color="Blue">Domäne</font> (optional)<br>- <font color="purple">Bereich</font>  (optional)<br>- <font color="OrangeRed">Unterbereich</font> (optional) | read<br>write<br>disclose<br>manage                      | Auf (Unter-)Bereich via Wildcard |
| Benutzer        | - <font color="purple">Bereich</font><br>- <font color="OrangeRed">Unterbereich</font>                                                                         | read<br>write<br>disclose                                | Auf (Unter-)Bereich via Wildcard |
| Alternativrolle | Keiner Ordnungseinheit zugeordnet.                                                                                                                              | read<br>write<br>disclose                                | Einzelne Maschinen               |
