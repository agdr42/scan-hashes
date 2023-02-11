# scan-hashes

# Ocultamiento de hashes en un documento

## Este script verifica si hay algún hash en un documento y lo oculta de manera automatizada.

```
import re

# Define el nombre del archivo a analizar
filename = 'document.txt'

# Abre el archivo y lee su contenido
with open(filename, 'r') as file:
    file_content = file.read()

# Busca hashes en el contenido del archivo
hashes = re.findall(r'[A-Fa-f0-9]{40}', file_content)

# Si se encuentran hashes, los oculta en el contenido del archivo
if hashes:
    for hash in hashes:
        file_content = file_content.replace(hash, '*' * len(hash))
    
    # Escribe el contenido modificado en el archivo
    with open(filename, 'w') as file:
        file.write(file_content)

print('El proceso de ocultamiento de hashes se ha completado.')
```
