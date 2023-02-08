# ATTACK-Mapping

This project allows an information security team to score themselves agasint the Mitre ATT&CK framework, document it in an XLSX file, and then convert it to JSON that can be used with the ATT&CK Navigator. 

### Prep

Install `openpyxl` to be able to work with the Excel file.

```
pip install openpyxl
```

### Executing

Be default, `attack-mapper.py` will use the files in the `examples` folder.
    `ATTACK-default.json` - a base ATT&CK JSON file for the Navigator. Only change is to the color.
    `ATTACK-example.xlsx` - an Excel document with random scores for each technique.
    `ATTACK-output.json` - a generated file when the script is run

Changes to the location of each file can be made using the following arguments:
    `-t` - location of the JSON template.
    `-e` - location of the Excel document.
    `-o` - destination location for the output file.

The `ATTACK-output.json` can then be uploaded to the [ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator/) 