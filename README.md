# qanyi — workspace de scanlation

Proyecto de traducción de manga. Dos proyectos, cada uno en su carpeta, como **submódulos**:

| Carpeta | Repo | Qué es |
|---|---|---|
| `tumpalo\` | [bybpow/tumpalo](https://github.com/bybpow/tumpalo) | fork de [zyddnys/manga-image-translator](https://github.com/zyddnys/manga-image-translator) (10498★) — **el motor**: detección, OCR, inpainting y traducción por lotes |
| `riddim\` | [bybpow/riddim](https://github.com/bybpow/riddim) | fork de [dmMaze/BallonsTranslator](https://github.com/dmMaze/BallonsTranslator) (5210★) — **el acabado**: GUI para editar máscaras, texto enriquecido, historial y glosarios |

No son forks entre sí: **riddim es un proyecto aparte que depende de tumpalo** (de él
salen sus modelos `mit*` de OCR y el inpainting AOT).

## Clonar

```bat
git clone --recursive https://github.com/bybpow/qanyi
```

O si ya está clonado:

```bat
git submodule update --init --recursive    REM primera vez
git submodule update --remote                REM baja lo nuevo de cada proyecto
```

Para cambiar algo dentro de un proyecto: se commitea **en su repo** y luego se apunta
el nuevo commit aquí:

```bat
cd Sandbox\TBO\tumpalo     git add .   git commit   git push
cd Sandbox\TBO             git add tumpalo   git commit -m "bump tumpalo"   git push
```

## Datos

`source\input\` (mangas fuente) y `source\output\` (resultados) **no se versionan**:
copyright y peso. Viven solo en local.

```
source\input\<manga>\paginas\     <- las páginas (solo lectura)
source\input\<manga>\*.zip|cbz    <- el archivo original
source\output\<proyecto>\<manga>\ <- los resultados
```

Para añadir un manga nuevo: crear `source\input\<manga>\paginas\`. Nada más cambia.

## Instrucciones

Las normas del proyecto, el estado del trabajo, las notas y los scripts están en la
carpeta de opencode: `Cabinet\OpenCode\TBO\` (empezar por su `AGENTS.md`).
