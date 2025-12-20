## Objetivo
Unificar el sitio en una sola página en español, con navegación por secciones (anclas) y cuenta atrás al 4/04/2026, siguiendo el estilo de una web de boda moderna.

## Estructura de Secciones
- Inicio: Hero con nombres, claim “¡Nos Casamos!” y cuenta atrás.
- Pareja: Presentación de los novios.
- Eventos: Detalles de ceremonia y recepción (hora, fecha, direcciones).
- Historia: Línea de tiempo con hitos.
- Galería: Imágenes destacadas.
- Confirmación (RSVP): Formulario simple para confirmar asistencia.
- Información: Dress code, obsequios y notas útiles.
- Contacto / Ubicación: Información de contacto y mapa.

## Implementación Técnica
- Navegación: Cambiar el menú a enlaces de ancla (`#inicio`, `#pareja`, `#eventos`, `#historia`, `#galeria`, `#rsvp`, `#info`, `#contacto`).
- Consolidación: Migrar contenidos de `about.html`, `services.html`, `gallery.html`, `contact.html` como secciones dentro de `index.html`.
- JS existente: Mantener `js/main.js` (offcanvas, animaciones, parallax, carrusel) y añadir smooth scroll a anclas si es necesario.
- Cuenta atrás: Configurada a 04/04/2026 con palabras en español (hecho), conservar.
- Mapa: Integrar bloque de mapa dentro de la sección Contacto.
- Formulario: Unificar el formulario de “¿Asistirás?” y el de contacto en una sección RSVP sencilla.
- SEO: Actualizar `<title>`, meta descripción en español acorde a la boda.

## Contenidos a Personalizar
- Nombres: Reemplazar por “Fernanda & Raúl” (si procede).
- Eventos: Opcionalmente incorporar detalles como:
  - Ceremonia: Iglesia Santa Eduwiges, 4:00 pm, dirección.
  - Recepción: Quinta Santa Rosa, 8:30 pm, dirección.
  - Dress code: Formal — Vestido largo, Traje completo — All Black.
  - Obsequios: Texto de cortesía.
- Fechas: Mantener el contador a 04/04/2026; si la fecha oficial cambia, lo ajustamos.

## Criterios de Aceptación
- El menú navega entre secciones sin recargas.
- La cuenta atrás muestra el tiempo restante correcto.
- Las secciones están 100% en español y coherentes.
- La versión móvil funciona (offcanvas, carrusel, parallax) sin errores.

## Verificación
- Prueba manual de scroll y anclas.
- Revisión de responsividad (Bootstrap ya incluido).
- Comprobación de rendimiento básico (optimización de imágenes si fuera necesario).

## Entregables
- `index.html` con todas las secciones.
- Menú actualizado a anclas.
- JS/CSS existentes reutilizados, con mínima adaptación para smooth scroll.

¿Confirmas que avanzamos con esta conversión a una sola página y que personalicemos los detalles de eventos, dress code y nombres como arriba?