# Peru SDK: modelos

Contratos JSON Schema, fuentes documentales y generador para SDKs nativos Go y Python. Licencia MIT. Este repositorio no contiene implementaciones de los SDKs ni se instala como dependencia de runtime.

```bash
python3 -m pip install -r tools/requirements.txt
python3 tools/sync_upstream.py --check
python3 tools/check_contracts.py
stage=$(mktemp -d /var/tmp/peru-models.XXXXXXXX)
python3 tools/generate.py --language go --output "$stage/go"
python3 tools/generate.py --language python --output "$stage/python"
```

El backend Go requiere `gofmt`; el backend Python solo necesita Python 3.11+. El generador admite únicamente el subconjunto explícito de esquema que valida en su código. Las implementaciones HTTP y las reglas complejas se mantienen en cada SDK.

El corpus está fijado por commit y SHA-256 en `upstream.lock.json`. Los SDKs fijan a su vez este generador y sus esquemas por commit y hash, conservan los modelos generados y verifican la sincronización en CI. Cambiar este repositorio no modifica automáticamente paquetes ni repositorios consumidores.

`contracts/sources.lock.json` y `docs/compatibility.md` documentan la evidencia disponible y sus límites. RENIEC es provisional; la compatibilidad SUNAT está comprobada con respuestas sintéticas y servidores locales, todavía no con consultas institucionales autorizadas.
