# fiscahub-version

Publica **solo** `version.txt`: el sello de build de la ultima version de FiscaHUB.

FiscaHUB lo consulta al abrir, con una peticion HTTP asincrona, para avisar al auditor
si hay una version mas nueva. Es un archivo de una linea y no necesita autenticacion,
que es exactamente por lo que vive aqui y no en OneDrive: el tenant de la DIAN tiene
deshabilitado el compartir anonimo, asi que ninguna URL de esa carpeta responde a un
GET sin cuenta de la organizacion.

**Aqui no se publica codigo.** El modulo se actualiza desde la carpeta compartida de
OneDrive (`FiscaHUB_Update.xlsx`), que si exige esa cuenta. Este repositorio existe
para una sola cosa: que el libro pueda preguntar "hay algo mas nuevo?" sin abrir nada
ni autenticarse.

## Publicar un build

`_gen_update_xlsx.py` escribe aqui el `version.txt` en cada build. Solo queda:

    git commit -am "bNNN" && git push
