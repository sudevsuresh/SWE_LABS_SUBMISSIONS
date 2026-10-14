# Static Code Analysis Issue Table

| Issue | Type | Line(s) | Description | Fix Approach |
|---|---|---|---|---|
| Mutable default argument | Bug | 42 | extras={} is shared across function calls and can cause unintended data sharing. | Change the default to None and initialize a new dictionary inside the function. |
| Missing docstrings | Code quality | 1, 17, 22, 29, 42, 50, 56, 61, 66 | Module and functions lack documentation. | Add a module docstring and short function docstrings. |
| Invalid naming conventions | Style | 17, 22, 29, 34, 42, 50, 56, 61, 67 | Names such as readMeters, meterId and slabUnits do not follow snake_case. | Rename them to read_meters, meter_id and slab_units, updating all references. |
| Unused parameter | Code quality | 50 | currency is accepted by averageBill() but never used. | Remove the parameter and update the function call. |
| Hardcoded password | Security | 13 | A password-like string is stored directly in the source code. | Remove it if unnecessary or load credentials securely from configuration. |
| Unsafe shell execution | Security | 63 | os.system() executes a shell command constructed using meterIp, creating a command-injection risk. | Remove the unused helper or use safe subprocess execution with input validation and a timeout. |
| Unsafe XML parsing | Security | 3, 18 | xml.etree.ElementTree is flagged for potentially unsafe XML parsing. | Replace it with defusedxml.ElementTree. |
| File opened without encoding | Code quality | 57 | open() does not explicitly specify an encoding. | Use open(file_name, "w", encoding="utf-8"). |
| Missing blank lines | Style | 22 | E302: only one blank line appears before a top-level function. | Add the required blank line. |
| Whitespace before colon | Style | 44 | E203: an unnecessary space appears before a colon in a dictionary entry. | Change "meter" : meterId to "meter": meter_id. |
| Line too long | Style | 72 | E501: a line contains 86 characters, exceeding the 79-character limit. | Split the statement across multiple lines. |
| Missing whitespace around operator | Style | 76 | E225: the assignment total=sum(...) lacks spaces around =. | Change it to total = sum(...). |
