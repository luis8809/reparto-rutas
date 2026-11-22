# Ruta de reparto

App web (un solo `index.html`, sin servidor ni claves) para planificar la ruta diaria de entregas y recogidas a partir del Excel de operaciones.

## Uso
1. Abre la app (GitHub Pages o el `index.html` en Chrome/Edge/Safari con Internet).
2. Carga el Excel: export de operaciones (`Operation Type`, `Loading/Unloading Address`…) o el Excel de paradas revisado.
3. Opcional: **Añadir albaranes (PDF o foto)**. Lee la dirección de entrega (o de recogida si sale de nuestro almacén), CP, municipio, bultos, kg y referencias; revisas los datos y pulsas «Añadir». Funciona también sin Excel. Los PDF con texto se leen exactos; las fotos pasan por OCR en el propio navegador (Tesseract.js), sin subir la imagen a ningún sitio.
4. Revisa las paradas en amarillo: edita la dirección o arrastra el pin. Las correcciones se guardan en el navegador.
5. Pulsa **Calcular ruta**: orden de paradas, ETA, ventanas horarias, carga del camión, enlaces a Google Maps y exportación CSV.

## Enviar la ruta al repartidor
Tras calcular la ruta, «Enviar ruta al repartidor» (WhatsApp, email, Compartir o Copiar enlace) genera un enlace con la ruta comprimida tras `#r=`. El repartidor lo abre en el móvil y ve solo su ruta: orden, horas, mapa, «Ir a la siguiente parada», Navegar por parada y marcas de «hecho» (guardadas en su móvil). La ruta no se guarda en ningún servidor: va dentro del enlace.

## Servicios usados (gratuitos, públicos)
- Geocodificación: Nominatim (OpenStreetMap), máx. 1 petición/s, limitada a la zona de cada código postal.
- Optimización de ruta: servidor de demostración de OSRM (sin garantías de disponibilidad).
- Mapa: OpenStreetMap / CARTO / Esri con cambio automático.
- Lectura de albaranes: pdf.js (PDF con texto) y Tesseract.js (fotos y PDF escaneados).
- Si el servidor de rutas no responde, la ruta se calcula en el navegador (línea recta, km estimados).

## Limitaciones
- Un solo vehículo; el optimizador no respeta ventanas horarias (solo avisa; se reordena a mano con ↑ ↓).
- Los datos y correcciones viven solo en el navegador de cada usuario.

## Privacidad
Los Excel se procesan en el navegador y no se suben a ningún sitio. `.gitignore` impide versionar `.xlsx`/`.csv`.
