# WikiCartas v2

Un solo archivo, `index.html`, sin build ni dependencias (solo Google Fonts, con fuente de reserva).

## Ejecutar
- **Local:** `npx serve .` dentro de esta carpeta y abre la URL que muestre (o abre `index.html` directamente).
- **Vercel:** sustituye el `index.html` de tu proyecto por este y ejecuta `vercel --prod` (o haz push al repositorio).

## Copia de seguridad
- `backup/index.v1.html` es la versión anterior, intacta.
- Tu partida v1 sigue en el navegador (`wikicartas_live_v1`). La v2 la **migra una sola vez** a `wikicartas_v2` sin borrar la original. Mismo dominio = se conserva la colección.
- Perfil → Exportar JSON hace una copia de la partida actual.

## Estado
| Función | Estado |
|---|---|
| Rediseño, navegación por `#hash` (7 secciones) | Hecho |
| Sobres (5 cartas, animación, duplicados, 50 máx., +1/5 min, sin gasto si falla) | Hecho |
| Colección con búsqueda y filtros (categoría, rareza, idioma, estado) | Hecho |
| Enciclopedia: búsqueda en vivo y «Cargar más» | Hecho |
| Cartas por QID de Wikidata; idiomas como versiones | Hecho (cartas v1 migradas conservan id por título hasta que salgan de nuevo) |
| Licencia y autoría de cada imagen (API de Commons) | Hecho; si la API no responde se indica «no disponible» |
| Combate, Tienda | Pantalla de próxima implementación |

## Limitaciones conocidas
- La interfaz está solo en español; es el contenido (Wikipedia) lo que cambia entre es/en/ca. Para añadir idioma de contenido, amplía `LANGS`.
- La categoría sale de la propiedad «instancia de» de Wikidata con un mapa pequeño; lo no reconocido es «Otros».
- Las «no descubiertas» son los artículos que marcas como pendientes en la enciclopedia: no se puede listar todo Wikipedia.
- Las miniaturas de la enciclopedia no muestran licencia; la licencia se guarda al obtener la carta.
- No hay cuentas: el progreso vive en el navegador.
