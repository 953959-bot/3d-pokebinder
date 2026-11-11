# Historial de cambios

## [0.2.0] - 2026-11-11

Pasada de mejora sobre la versión con panel lateral (HUD), buscador, filtro por set, inspector y PDF: se arreglan botones que no hacían nada, se usan datos reales de precios y se refuerza el estilo retro.

### Añadido
- **Sobres de cartas:** botón "ABRIR SOBRE" que reparte 5 cartas aleatorias de la primera generación (priorizando Pokémon que aún no tienes). Se revelan una a una con sonido y puedes poner la que quieras en el álbum.
- **Exportar e importar la colección** en JSON. Al importar se validan las cartas (solo imágenes de images.pokemontcg.io) para evitar datos maliciosos.
- **Copiar link:** genera un enlace para compartir tu colección. Quien lo abre la ve en "modo visita", sin que se modifique su propia colección.
- **Actualizar precios:** vuelve a consultar la API y refresca el precio de todas las cartas elegidas.
- **Cartas agrupadas por rareza** en el selector, ordenadas de común a ultra rara.
- **Estilo retro:** líneas de escaneo tipo CRT, marcos y botones de píxel, barra de progreso por bloques, sonidos de 8 bits (onda cuadrada) y sprites que saltan al pasar el ratón.
- **Teclas ← y →** para pasar de hoja.

### Cambiado
- El **gráfico de precios** ahora usa datos reales de Cardmarket (media 30 días, 7 días, 1 día y tendencia). Antes eran valores inventados.
- Las peticiones a la API piden solo los campos necesarios (`select`), así cargan más rápido.
- Las cartas sin precio muestran "sin precio" en vez de 0,00 €.

### Corregido
- Los botones **JSON Export, Importar, Copiar Link y Precios** no tenían función asociada.
- Si la API fallaba, el selector mostraba las cartas del Pokémon anterior y guardaba el fallo en caché. Ahora muestra el error con botón de reintentar.
- Al arrastrar la portada cerrada, el libro se descentraba.

## [0.1.0] - 2026-11-09

Primera versión conectada a datos reales. Antes era una maqueta con cartas y precios de ejemplo.

### Añadido
- **Portada y libro 3D** con hojas que se giran, y animación de aparición de los huecos al abrir cada página.
- **Primera generación completa:** 151 Pokémon repartidos en 17 páginas de 9 huecos (3x3), ordenados por número de Pokédex.
- **Sprites pixelart** (estilo FireRed/LeafGreen) en los huecos vacíos, junto al número y el nombre del Pokémon.
- **Cartas reales** desde la Pokémon TCG API: al pulsar un hueco se listan todas las cartas de ese Pokémon, agrupadas por rareza.
- **Efecto holográfico** en las cartas de rarezas especiales, que reacciona al ratón o al dedo.
- **Valor total** de la colección con la tendencia de precios de Cardmarket (EUR), y barra de progreso.
- **Guardado local** de la colección en el navegador.
- `README.md` con explicación del proyecto, fuentes de datos y pasos para publicar con GitHub Pages.

### Limitaciones conocidas
- Sin cuentas de usuario: la colección solo vive en el navegador donde se creó.
- Los precios se guardan al elegir la carta y todavía no se actualizan solos.
- Sin precios de eBay.
- Nombres de Pokémon en inglés.
