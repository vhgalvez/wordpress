
mv $(ls | grep -v "^wordpress$\|^docker-compose.yml$") wordpress/


En Ubuntu (y en la mayoría de las distribuciones de Linux), puedes usar el comando mv para mover archivos y directorios de un lugar a otro desde la consola de comandos.

Mover un archivo único:
Para mover un archivo único de un directorio a otro, puedes usar el siguiente formato:

bash
Copy code
mv /ruta/del/archivo_origen /ruta/del/destino/
Por ejemplo, para mover el archivo ejemplo.txt desde el directorio ~/Documentos al directorio ~/Descargas, usarías:

javascript
Copy code
mv ~/Documentos/ejemplo.txt ~/Descargas/
Mover varios archivos:
Si deseas mover varios archivos a la vez, puedes especificarlos uno tras otro y, finalmente, indicar el directorio destino:

bash
Copy code
mv /ruta/del/archivo1 /ruta/del/archivo2 /ruta/del/destino/
Mover un directorio:
Para mover un directorio entero, el proceso es similar a mover un archivo:

bash
Copy code
mv /ruta/del/directorio_origen /ruta/del/destino/
Usar comodines:
Puedes usar comodines como * para mover múltiples archivos que coincidan con un patrón. Por ejemplo, para mover todos los archivos .txt de un directorio a otro:

javascript
Copy code
mv ~/Documentos/*.txt ~/Descargas/
Renombrar archivos o directorios:
El comando mv también se puede usar para renombrar archivos o directorios. Simplemente especifica el nombre original y luego el nuevo nombre:

bash
Copy code
mv nombre_original.txt nuevo_nombre.txt
Ten en cuenta que si el destino ya tiene un archivo o directorio con el mismo nombre, el comando mv lo sobrescribirá sin preguntar. Si deseas una confirmación antes de sobrescribir, puedes usar el flag -i:

bash
Copy code
mv -i archivo_origen archivo_destino
¡Espero que esto te ayude a mover tus archivos y directorios en Ubuntu! Si tienes más preguntas o dudas, ¡házmelo saber!