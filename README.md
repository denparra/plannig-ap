# Pasito a pasito

Una aplicación visual para preparar y recorrer actividades juntos. Funciona en el navegador, con interfaz adaptable a móviles Android y iPhone. Incluye una ruta de ejemplo para acompañar a papá a la barbería y un catálogo de imágenes básicas.

## Ejecutar en el ordenador

Necesitas Python 3. Desde esta carpeta ejecuta:

```sh
python -m http.server 4173
```

Abre <http://localhost:4173>. No abras `index.html` directamente: el almacenamiento y la instalación requieren un servidor web. Para instalarla en un teléfono se necesita publicarla mediante HTTPS; el servidor local anterior solo está pensado para desarrollo. La instalación depende del navegador: en iPhone suele hacerse desde Compartir → Añadir a pantalla de inicio; en Android, desde el menú del navegador.

## Usar la aplicación

- Abre la ruta de la barbería para ver el ejemplo.
- Elige un paso y marca si está esperando, en proceso o terminado. Puedes cambiarlo de nuevo cuando quieras.
- Crea una ruta, añade pasos, selecciona imágenes del catálogo y explica quién hace qué. Puedes reordenar y editar los pasos.
- En Ajustes, descarga una copia JSON para guardar tus rutas. Restaurar una copia **reemplaza todas las rutas actuales**; antes puedes exportarlas.

Las rutas se guardan en IndexedDB en el navegador del dispositivo, no se sincronizan y no se envían a un servidor. Borrar los datos del navegador, desinstalar o cambiar de dispositivo puede hacer que se pierdan: conserva copias en un lugar seguro. Tras la primera carga completa, el service worker permite volver a abrir la aplicación sin conexión en navegadores compatibles. La disponibilidad de almacenamiento y el funcionamiento sin conexión dependen del navegador y del sistema operativo.

El catálogo utiliza símbolos visuales del sistema (su aspecto cambia entre dispositivos). Esta versión no incluye fotos propias, grabaciones de voz, cuentas ni sincronización en la nube.

## Pruebas

Con Node.js instalado:

```sh
node --test tests/model.test.mjs
```
