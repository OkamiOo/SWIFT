# Composants de SWIFT

SWIFT utilise ces bibliothèques. Chacune garde sa propre licence, dont le texte complet est livré
dans le dossier `LICENCES` du zip.

| Composant | Version | Licence | Où |
|---|---|---|---|
| [FFmpeg](https://ffmpeg.org) | 9.0.2 | LGPL 2.1 ou plus | `avcodec-63.dll`, `avformat-63.dll`, `avutil-61.dll`, `swresample-7.dll` |
| [LAME](https://lame.sourceforge.io) | 4.0 | LGPL 2 | dans `avcodec-63.dll` |
| [Opus](https://opus-codec.org) | 1.6.1 | BSD 3 clauses | dans `avcodec-63.dll` |
| [Ogg](https://xiph.org/ogg/) et [Vorbis](https://xiph.org/vorbis/) | 1.3.6 et 1.3.7 | BSD 3 clauses | dans `avcodec-63.dll` |
| zlib | 1.3.2 | zlib | dans `avformat-63.dll` |
| Runtime MinGW-w64 | | ZPL, MIT | dans les DLL |
| Bibliothèques Rust de l'interface (egui, winit…) | | MIT, Apache 2.0 et proches | dans `SWIFT.exe` |

FFmpeg est compilé sans aucune partie GPL ni non libre, avec seulement ce qui sert au son. Les
quatre DLL peuvent être remplacées par une autre version compatible de FFmpeg.

## Sources

Les sources exactes de FFmpeg, LAME, Opus, Ogg et Vorbis utilisées pour chaque version de SWIFT,
avec le script qui les compile, sont fournies sur simple demande à [Oka@Akiden.fr](mailto:Oka@Akiden.fr), pendant au
moins trois ans après la dernière diffusion de cette version.
