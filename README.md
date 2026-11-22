# Ruta de reparto

App web (un solo `index.html`, sin servidor ni claves) para planificar la ruta diaria de entregas y recogidas a partir del Excel de operaciones.

## Uso
1. Abre la app (GitHub Pages o el `index.html` en Chrome/Edge/Safari con Internet).
2. Carga el Excel: export de operaciones (`Operation Type`, `Loading/Unloading Address`…) o el Excel de paradas revisado.
3. Revisa las paradas en amarillo: edita la dirección o arrastra el pin. Las correcciones se guardan en el navegador.
4. Pulsa **Calcular ruta**: orden de paradas, ETA, ventanas horarias, carga del camión, enlaces a Google Maps y exportación CSV.

## Servicios usados (gratuitos, públicos)
- Geocodificación: Nominatim (OpenStreetMap), máx. 1 petición/s, limitada a la zona de cada código postal.
- Optimización de ruta: servidor de demostración de OSRM (sin garantías de disponibilidad).
- Mapa: teselas de CARTO (Esri de respaldo).

## Limitaciones
- Un solo vehículo; el optimizador no respeta ventanas horarias (solo avisa; se reordena a mano con ↑ ↓).
- Los datos y correcciones viven solo en el navegador de cada usuario.

## Privacidad
Los Excel se procesan en el navegador y no se suben a ningún sitio. `.gitignore` impide versionar `.xlsx`/`.csv`.
