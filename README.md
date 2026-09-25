# Cybersecurity Toolkit

Utilidades simples de seguridad defensiva local.

Incluye hash SHA-256, comparación de integridad, generación de contraseñas, revisión de puertos TCP locales, procesos, conexiones y logs de texto.

## Requisitos

- Python 3.10 o superior
- `psutil`

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

## Uso

```bash
python security.py hash sample.txt
python security.py verify sample.txt HASH_DE_64_CARACTERES
python security.py password --length 24
python security.py ports 80 443
python security.py connections
python security.py processes
python security.py system
python security.py logs sample.txt
```

`ports` sólo revisa `127.0.0.1` y `::1`, con hasta 20 puertos indicados. No hace escaneos de red.

`sample.txt` tiene registros de ejemplo. `logs` cuenta las líneas que contienen `error`, `warning`, `failed` o `denied`.

Las contraseñas se muestran en la terminal y no se guardan. No compartas esa salida. Un hash igual sólo indica que el archivo coincide con el hash esperado.
