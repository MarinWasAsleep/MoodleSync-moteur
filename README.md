# MoodleSync-moteur

Paquets portables du moteur de lecture utilise par MoodleSync pour extraire le texte des scans.

Ce depot ne contient pas de code : il porte les archives que MoodleSync telecharge quand
l'utilisateur clique sur « Installer » dans la carte de preparation.

## Contenu d'une release

| Fichier | Systeme | Taille |
|---|---|---|
| `MoodleSync-moteur-windows.zip` | Windows 64 bits | environ 61 Mo |
| `MoodleSync-moteur-macos.zip` | macOS Apple Silicon | environ 14 Mo |

Chaque archive porte le binaire du moteur, ses bibliotheques et les donnees de langue
`fra`, `eng` et `osd`.

## Empreintes SHA-256

Les empreintes sont inscrites dans le code de MoodleSync, jamais lues dans la reponse du
serveur. Une archive dont l'empreinte ne correspond pas est supprimee.

```text
MoodleSync-moteur-windows.zip  ba86c780c2c5aacbe66dd4c40ca0093ef1f80426df2cb9b226a1faf3c1a1f51d
MoodleSync-moteur-macos.zip    a7d6198ef730cfd6a93e2b3eb63d71f13bec1bfe60034be32ca93d23d9e72a96
```

## Provenance

- Windows : installeur Tesseract 5.4.0 de UB-Mannheim, dont seuls le binaire, les DLL et
  `tessdata` sont repris.
- macOS : flacon Homebrew de Tesseract 5.5.4 (arm64), avec les bibliotheques de ses
  dependances aplaties dans `lib/` et les chemins reecrits vers `@loader_path`.
- Donnees de langue : `fra` vient de `tessdata_fast`, `eng` et `osd` viennent des paquets
  d'origine.

## Licence

Tesseract est publie sous licence Apache 2.0. Le texte de la licence accompagne chaque
archive.

## Mise a jour

Une nouvelle version du moteur se publie comme une nouvelle release : deposez les deux
archives, puis mettez a jour les empreintes dans le code de MoodleSync.
