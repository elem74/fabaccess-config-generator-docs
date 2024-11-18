Beispiel-Konfigurationsschema für einen Aktor-Typ:

```ini
[aktorname]
module = Process
param_cmd = "/usr/local/lib/bffh/adapters/tasmota/main.py"
param_args = "--host mqtt --tasmota $actor_id"
```

- Der Parameter "module" ist ein Pflichtfeld. Dies definiert das FabAccess-Modul des Aktoren (siehe FabAccess-Dokumentation).
- Es können beliebig viele Parameter übergeben werden. Diese müssen mit dem Präfix `param_` versehen werden, damit sie erkannt und verarbeitet werden können.
- Der Platzhalter `$actor_id` markiert die Stelle, an der die Aktor-ID automatisch eingefügt werden soll.

<br>Das Aktor-Konfigurationsschema wird automatisch in eine FabAccess-Konfiguration übersetzt. In diesem Beispiel lautet die Aktor-ID `stecker16`:

```python
    {
    module = "Process",
        params =
        {
            cmd = "/usr/local/lib/bffh/adapters/tasmota/main.py",
            args = "--host mqtt --tasmota stecker16",
        }
    },
```

