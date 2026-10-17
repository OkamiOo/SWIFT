# SWIFT

**Smart Wave Interchange & File Transcoder**

SWIFT sort le son de vos vidéos et convertit vos fichiers audio. On glisse les fichiers dans la
fenêtre, on choisit le format, on clique sur Convertir. Gratuit, sans compte, sans publicité,
rien à installer.

![SWIFT](captures/swift-sombre.png)

## Ce qu'il fait

- Vidéos (MOV, MP4, MKV, WebM, AVI, TS, FLV, WMV…) et sons (MP3, M4A, WAV, FLAC, OGG, Opus,
  WMA, AC-3…) vers MP3, AAC (M4A), Opus, OGG Vorbis, FLAC ou WAV.
- Le format « Original » sort la piste son telle quelle, sans aucune perte, en une fraction de
  seconde.
- Si le son est déjà au bon format (l'AAC d'une vidéo de téléphone vers M4A, l'Opus d'une vidéo
  YouTube), il est recopié sans être réencodé : c'est la « Copie directe ».
- Enregistrements OBS à plusieurs pistes : la piste principale, une piste précise, ou un fichier
  par piste.
- Tags, chapitres et pochette gardés quand le format le permet. La position GPS des vidéos de
  téléphone n'est pas recopiée.
- Plusieurs fichiers en même temps, sur tous les cœurs du processeur, en priorité basse pour ne
  pas gêner un jeu ou un stream.
- Jamais d'écrasement sans demander.
- « Convertir avec SWIFT » au clic droit de l'Explorateur, si vous le voulez.
- Mises à jour automatiques et vérifiées : vous n'avez pas à revenir chercher un zip.
- Thème clair ou sombre, comme Windows.

## Vitesse

Mesuré sur un Ryzen 9 5900X, en comparant avec `ffmpeg` en ligne de commande compilé à partir
des mêmes sources :

| Conversion | ffmpeg | SWIFT |
|---|---|---|
| Son d'une vidéo MOV d'une heure vers M4A (copie directe) | 1,55 s | 1,33 s |
| Vidéo de 10 min vers MP3 V2 | 4,70 s | 4,66 s |
| Vidéo de 10 min vers FLAC | 0,98 s | 0,80 s |
| 48 MP3 de 4 min vers Opus | 79,7 s (un par un) | 8,0 s |

Le programme pèse 14 Mo une fois dézippé et s'ouvre en 0,3 s.

## Télécharger

Dans les [Releases](../../releases) : télécharger `SWIFT-x.y.z-windows-x64.zip`, le dézipper où
vous voulez, lancer `SWIFT.exe`. Windows 10 ou 11, 64 bits.

Pour tout retirer : couper « Clic droit dans l'Explorateur » dans les options, puis supprimer le
dossier de SWIFT et le dossier `%APPDATA%\SWIFT`. Le fichier LISEZMOI explique le détail.

## Windows va peut-être se méfier

Au premier lancement, Windows peut afficher « Windows a protégé votre ordinateur », et certains
antivirus peuvent se méfier de SWIFT. Ce n'est pas parce que SWIFT est dangereux : c'est parce
qu'il n'est pas signé numériquement. Un certificat de signature coûte plus de 100 € par an, et
SWIFT est gratuit, alors je ne l'ai pas pris. Pour Windows, un programme non signé et encore peu
téléchargé est suspect par défaut.

Pour le lancer quand même : cliquer sur « Informations complémentaires », puis sur « Exécuter
quand même ». Cela n'arrive qu'une fois.

Vous pouvez vérifier vous-même ce que vous téléchargez : chaque version publie l'empreinte
SHA-256 de son zip. Dans PowerShell, `Get-FileHash .\SWIFT-x.y.z-windows-x64.zip` doit donner
la même.

Les mises à jour automatiques sont signées : SWIFT n'installe que ce que j'ai signé avec ma clé,
et vérifie l'empreinte de chaque fichier avant de l'utiliser.

## Licence

SWIFT est gratuit : on peut l'utiliser et le donner librement, mais pas le vendre. Son code n'est
pas publié. Le texte complet est dans [LICENCE.txt](LICENCE.txt).

## Composants

SWIFT convertit avec [FFmpeg](https://ffmpeg.org) 9.0.2 (LGPL 2.1), avec
[LAME](https://lame.sourceforge.io) 4.0 pour le MP3 (LGPL), et Opus, Ogg et Vorbis de
[Xiph](https://xiph.org) (BSD). Ces bibliothèques sont dans des DLL séparées, que l'on peut
remplacer. Leurs sources exactes sont fournies sur simple demande à [Oka@Akiden.fr](mailto:Oka@Akiden.fr), pendant au
moins trois ans. Le détail est dans [COMPOSANTS.md](COMPOSANTS.md).

Fait par Oka.
