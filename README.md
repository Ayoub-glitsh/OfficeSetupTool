# README - Installation simple de Microsoft Office via le repo

Repo original : [GitHub - Install-Office](https://github.com/farag2/Install-Office)

## 1. Télécharger et ouvrir le dossier
1. Télécharger le ZIP depuis GitHub (Code → Download ZIP).
2. Décompresser le fichier.
3. Mettre le dossier sur le bureau.

## 2. Ouvrir PowerShell en mode administrateur
1. Cliquer sur Démarrer
2. Taper `PowerShell`
3. Clic droit → "Exécuter en tant qu'administrateur"

## 3. Autoriser l'exécution du script
```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Force
```

## 4. Aller dans le dossier du projet
```powershell
cd CHEMIN_DU_DOSSIER
```
*(Astuce : glisser le dossier dans la fenêtre PowerShell)*

## 5. Télécharger Office
Exemple pour Word + Excel + PowerPoint :
```powershell
.\Download.ps1 -Branch ProPlus2019Retail -Channel Current -Components Word, Excel, PowerPoint
```

## 6. Installer Office
```powershell
.\Install.ps1
```

## Résultat
Office sera installé sur votre ordinateur.

## Important
- Avant d’installer, supprimez toutes les anciennes versions d’Office de votre ordinateur pour éviter les conflits et redémarrez votre PC.

