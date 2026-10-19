# Composants de SWIFT

SWIFT utilise ces bibliothèques. Chacune garde sa propre licence, dont le texte complet est livré
dans le dossier `LICENCES` du zip.

| Composant | Version | Licence | Où |
|---|---|---|---|
| [FFmpeg](https://ffmpeg.org) | 9.0.2 | LGPL 2.1 ou plus | `avcodec-63.dll`, `avformat-63.dll`, `avutil-61.dll`, `swresample-7.dll`, `swscale-10.dll` |
| [LAME](https://lame.sourceforge.io) | 4.0 | LGPL 2 | dans `avcodec-63.dll` |
| [Opus](https://opus-codec.org) | 1.6.1 | BSD 3 clauses | dans `avcodec-63.dll` |
| [Ogg](https://xiph.org/ogg/) et [Vorbis](https://xiph.org/vorbis/) | 1.3.6 et 1.3.7 | BSD 3 clauses | dans `avcodec-63.dll` |
| [SVT-AV1](https://gitlab.com/AOMediaCodec/SVT-AV1) | 4.2.0 | BSD 3 clauses « Clear », brevets AOMedia | dans `avcodec-63.dll` |
| [libvpx](https://www.webmproject.org) | 1.17.0 | BSD 3 clauses | dans `avcodec-63.dll` |
| [dav1d](https://code.videolan.org/videolan/dav1d) | 1.5.4 | BSD 2 clauses | dans `avcodec-63.dll` |
| [libvpl](https://github.com/intel/libvpl) (Intel) | 2.17.0 | MIT | dans `avcodec-63.dll` |
| En-têtes NVENC (NVIDIA) et AMF (AMD) | 12.0 et 1.5.3 | MIT | dans `avcodec-63.dll` |
| zlib | 1.3.2 | zlib | dans `avformat-63.dll` |
| Runtime MinGW-w64, winpthreads | | ZPL, MIT | dans les DLL |
| Runtime C++ de GCC | | GPL 3 avec l'exception des bibliothèques d'exécution de GCC | dans les DLL |
| Bibliothèques Rust de l'interface (egui, winit…) | | MIT, Apache 2.0 et proches | dans `SWIFT.exe` |

FFmpeg est compilé sans aucune partie GPL ni non libre, avec ce qui sert au son et à la vidéo.
Les cinq DLL peuvent être remplacées par une autre version compatible de FFmpeg. L'exception des
bibliothèques d'exécution de GCC permet d'inclure son runtime C++ dans n'importe quel logiciel.
L'encodage H.264 au processeur passe par l'encodeur de Windows (Media Foundation).

## Sources

Les sources exactes de FFmpeg et des bibliothèques ci-dessus utilisées pour chaque version de
SWIFT, avec le script qui les compile, sont fournies sur simple demande à
[Oka@Akiden.fr](mailto:Oka@Akiden.fr), pendant au moins trois ans après la dernière diffusion de
cette version.
