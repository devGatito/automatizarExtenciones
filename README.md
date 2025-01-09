# crea un archivo sh.
Dirijete a la terminal y escribe ```nano nombre_archivo.sh ```
y con eso creas el script.

# ejecuta archivo sh.
donde lo guardes, solo ejecuta ```./nombre_archivo.sh```, tal como le pongas de nombre y esperar


# Exporta todas las extenciones en bash 
```
#!/bin/bash

# Archivo de salida donde se guardarán las extensiones
EXT_FILE="extensiones.txt"

# Exporta las extensiones instaladas y las guarda en el archivo
codium --list-extensions > "$EXT_FILE"

echo "Las extensiones instaladas se han guardado en $EXT_FILE."
```
# Importa todas las extenciones
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

