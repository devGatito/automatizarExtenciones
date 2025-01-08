# automatizarExtenciones
```#!/bin/bash

# Archivo que contiene las extensiones
EXT_FILE="extensiones.txt"

# Verifica si el archivo existe
if [[ ! -f "$EXT_FILE" ]]; then
  echo "El archivo $EXT_FILE no existe. Por favor, crea uno con la lista de extensiones."
  exit 1
fi

# Instala cada extensión en el archivo
while IFS= read -r EXTENSION; do
  if [[ ! -z "$EXTENSION" ]]; then
    echo "Instalando $EXTENSION..."
    codium --install-extension "$EXTENSION"
  fi
done < "$EXT_FILE"

echo "Todas las extensiones han sido instaladas."
```
