## Erarbeitung des Arbeitsauftrags

### Storage Account

Zuerst musste der Storage Account erstellt werden. Hierfür habe ich ziemlich schnell die Type-Signatur gefunden und den Rest hat mir die VS-Code Extension vorgeschlagen. Vorerst mal mit hardcodierten Werten als Parameter.

### Web App

Daraufhin die WebApp. Ebenso in Google die Type-Signatur herausgefunden und aus der Berufserfahrung gewusst, dass für einen App-Service ebenso ein App-Service-Plan erforderlich ist, welcher ebenfalls dazu codiert wurde. (Natürlich im Free Tier)

### Testen

Den ersten codierten Entwurf habe ich dann über das Azure Portal versucht zu erstellen und danach meine Eingaben/Erstellungen überprüft. Bis auf einen Fail aufgrund des Namens der Web-App haben alle Informationen funktioniert und wurden ordnungsgemäß erstellt. Parameter-Syntaxen wie, dass der Name des Storage-Accounts nur aus Zahlen bestehen darf, wurden danach ins Template übernommen.

### Erweitern durch die Parameter

Danach wurden die benötigten Parameter sowohl im eigentlichen Konfigurations-File als auch im Parameters-File definiert und die bisher hardcodierten Werte durch die dynamischen Parameter ersetzt.

### Finale Tests durch die Azure Powershell

Daraufhin wurde die Erstellung des ARM-Files in der Powershell mit Anfügung der Parameter durchgeführt.
Befehl

```Powershell
New-AzResourceGroupDeployment -ResourceGroupName "Test-Gruppe" -TemplateFile ".\azuredeploy.json" -TemplateParameterFile ".\azuredeploy.parameters.json"
```
