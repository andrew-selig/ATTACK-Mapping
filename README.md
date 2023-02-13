# ATTACK-Mapping

This project allows an information security team to score themselves against the Mitre ATT&CK framework, document it in an XLSX file, and then convert it to JSON that can be used with the ATT&CK Navigator. For more information on background, check out this article: [Use ATT&CK to Help Quantify Your Security Risk](https://medium.com/@andrewselig/use-att-ck-to-help-quantify-organizational-risk-9b3f7d513ae5)

### Files

`ATTACK-template.xlsx`

This file is a template Excel document that is based off of the article listed above, with three input scores that factor out to a total score. As the team moves through and scores each technique, the script will put the technique ID and the total score into the JSON for the Navigator. 

Note: If you decide to make changes to the columns for scoring purposes, be sure to update the columns within the script itself.

`ATTACK-example.xlsx`

This file is the same as the template, however has had random numbers (1-100) put into each cell. The total score is calculated by taking a third of each score and adding them up. This weighting is something to consider for each organization, and the formula should be updated accordingly. 

`ATTACK-default.json`

This is a vanilla export of the JSON file from the Navigator, with color and scoring information put in for the gradient (aqua). Update this file to suit your needs. The script will make a copy and fill in the technique information from the Excel file.

`ATTACK-output.json`

This file is the result of combinging the score information from the Excel file as well as the default JSON file. You can upload it to the ATTACK Navigator as-is to see the result of the random scoreing in `ATTACK-example.xlsx`. Change the import file to your own in order to generate a custom `ATTACK-output.json` file. 

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
