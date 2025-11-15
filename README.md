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
Set-ExecutionPolicy Bypass -Force
```

## 4. Aller dans le dossier du projet
```powershell
cd CHEMIN_DU_DOSSIER
```
*(Astuce : glisser le dossier dans la fenêtre PowerShell)*

## 5. Télécharger Office
Exemple pour Word + Excel + PowerPoint :
```powershell
.\Download.ps1 -Branch ProPlus2024Volume -Channel PerpetualVL2024 -Components Word, Excel, PowerPoint
```

## 6. Installer Office
```powershell
.\Install.ps1
```

## Résultat
Office sera installé sur votre ordinateur.

## Important
- Ce script n'active pas Office légalement. Utilisez une clé officielle ou Office Online pour une utilisation normale.
- Avant d’installer, supprimez toutes les anciennes versions d’Office de votre ordinateur pour éviter les conflits et redémarrez votre PC.


## Troubleshooting (Problèmes courants)

### 0. Problème avec la commande : `Set-ExecutionPolicy -ExecutionPolicy Bypass -Force`
PowerShell fonctionne correctement, **mais il peut refuser cette commande** à cause d’une stratégie de sécurité Windows.

### ✅ Solution simple
1. Ouvrez PowerShell **en administrateur**.
2. Affichez les stratégies actives :
   ```powershell
   Get-ExecutionPolicy -List
   ```
3. Si *MachinePolicy* ou *UserPolicy* affiche `RemoteSigned` ou `AllSigned`, cela bloque la commande.
4. Utilisez cette commande alternative :
   ```powershell
   powershell -ExecutionPolicy Bypass
   ```
   → Une nouvelle fenêtre PowerShell s’ouvre avec les permissions nécessaires.
5. Dans cette nouvelle fenêtre, exécutez :
   ```powershell
   .\Download.ps1
   ```

### 📌 Exemple de commande complète si PowerShell ne fonctionne pas
Si PowerShell refuse d’exécuter le script, utilisez directement cette commande :
```powershell
powershell -ExecutionPolicy Bypass -File C:\Users\HP\Desktop\Install-Office-master\Download.ps1
```

### 1. Erreur : « Impossible de valider l'argument sur le paramètre Branch »
Ce problème arrive lorsque le nom de la branche contient **un espace en trop**, par exemple :
```
ProPlus2019Retail 
```

### ✅ Solution
- Vérifiez qu'il n'y a **aucun espace** avant ou après le nom.
- Utilisez uniquement ces noms autorisés :
  - `ProPlus2019Retail`
  - `ProPlus2021Volume`
  - `ProPlus2024Volume`
  - `O365ProPlusRetail`

### Exemple de commande correcte
```
.\Download.ps1 -Branch ProPlus2019Retail -Channel Current -Components Word,Excel,PowerPoint
```

### 2. PowerShell vous demande les paramètres un par un
Il peut afficher :
```
Branch:
Channel:
Components[0]:
```
Remplissez comme ceci :
- `Branch:` → `ProPlus2019Retail`
- `Channel:` → `Current`
- `Components[0]:` → `Word`
- `Components[1]:` → `Excel`
- `Components[2]:` → `PowerPoint`
- `Components[3]:` → (appuyez juste sur Entrée)
