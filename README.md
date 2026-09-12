# fiscahub-version

Publica el sello de build de FiscaHUB y, en las ramas de canal, las piezas de su
actualizacion.

FiscaHUB es una herramienta personal, construida como un libro de Excel con macros y
compartida con un grupo pequeño de compañeros de trabajo.

- `version.txt` — una linea con el sello del ultimo build. El libro lo consulta al
  abrir, con una peticion HTTP asincrona, para avisar si hay algo mas nuevo. No
  necesita autenticacion, y eso es exactamente por lo que vive aqui: en la biblioteca
  de documentos corporativa donde vive el instalador, el compartir anonimo esta
  deshabilitado, asi que ninguna URL de esa carpeta responde a un GET sin cuenta de la
  organizacion.
- `canal/` (en las ramas de canal) — las piezas de la actualizacion. Ver el README de
  esa carpeta.

**Lo que NO se publica aqui:** ningun dato personal ni informacion de ningun caso de
trabajo, y tampoco el libro completo, que se distribuye por otro medio. Dos
verificadores comprueban cada pieza antes de escribirla, buscando numeros de
identificacion y nombres, y abortan si encuentran algo.

## Publicar un build

`_gen_update_xlsx.py` escribe aqui el `version.txt` en cada build. Solo queda:

    git commit -am "bNNN" && git push
