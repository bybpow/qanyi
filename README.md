# scanlation — workspace

Dos proyectos de traducción de manga, cada uno en su carpeta, como **submódulos**:

| Carpeta | Proyecto | Qué es |
|---|---|---|
| `mit-python\` | [bybpow/manga-image-translator](https://github.com/bybpow/manga-image-translator) (fork de [zyddnys](https://github.com/zyddnys/manga-image-translator), 10498★) | el pipeline original en Python: detección, OCR, inpainting y traducción |
| `ballons\` | [bybpow/BallonsTranslator](https://github.com/bybpow/BallonsTranslator) (fork de [dmMaze](https://github.com/dmMaze/BallonsTranslator), 5210★) | herramienta asistida con GUI: edición de máscaras, texto enriquecido, historial y glosarios para el LLM |

No son forks entre sí: BallonsTranslator es un proyecto aparte que **depende** de
manga-image-translator (de ahí salen sus modelos `mit*` de OCR y el inpainting AOT).

## Clonar

```bat
git clone --recursive https://github.com/bybpow/scanlation
```

O si ya está clonado, para traer cambios de los proyectos:

```bat
git submodule update --init --recursive    REM primera vez
git submodule update --remote                REM baja lo nuevo de cada proyecto
```

## Datos

`data\input\` (mangas fuente) y `data\output\` (resultados) **no se versionan**:
copyright y peso. Vive en local.

## Instrucciones

Las normas del proyecto, el estado del trabajo, las notas y los scripts están en la
carpeta de opencode: `Cabinet\OpenCode\TBO\` (empezar por su `AGENTS.md`).
