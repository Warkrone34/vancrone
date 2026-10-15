# Guía de la Pantalla Principal y Resumen de Funciones de Vancrone

> Este documento es el manual oficial que describe la pantalla principal, el seguimiento de garantías, las herramientas y las funciones de seguridad de Vancrone. Última actualización: 15 de octubre de 2026.

---

## 1. Visión General y Arquitectura Offline-First

Vancrone es un inventario digital y una caja fuerte independientes que controlan los periodos de garantía y devolución, las facturas y las pruebas de propiedad de lo que compra. La versión actual es gratuita: todas las funciones están disponibles sin límites y no hay anuncios ni compras dentro de la aplicación.

- **Sin conexión y almacenamiento local:** Sus registros, facturas y fotos nunca salen de su dispositivo; no existe un servidor de Vancrone, una cuenta de usuario ni una base de datos en la nube. A Google Firebase Crashlytics solo se envían informes de fallos sin su contenido, y puede desactivarlo en **Ajustes > Acerca de > Informes de fallos** (consulte la Política de Privacidad).
- **Caja fuerte local cifrada:** Sus registros se guardan en una base de datos cifrada con AES-256 (SQLCipher). Las fotos de facturas, los documentos y los vídeos se guardan en el almacenamiento privado de la app en su dispositivo.
- **Responsabilidad del usuario y copias de seguridad:** Como sus datos solo existen en su dispositivo, usted es responsable de hacer copias periódicas. Si el dispositivo se pierde, se restablece o se daña, el desarrollador no puede recuperar sus datos. Use **Ajustes > Gestión de Datos > Copia de Seguridad (Exportar)** para guardar un archivo `.vcb` cifrado, con contraseña si lo desea, en el lugar que elija, y **Restaurar (Importar)** para recuperarlo en el mismo teléfono o en uno nuevo.

---

## 2. Barra Superior

- **Calendario:** El icono del calendario abre un calendario mensual con las fechas de vencimiento de las garantías. Toque un día para ver los artículos que vencen ese día.
- **Guía del Usuario y FAQ:** El icono del signo de interrogación abre respuestas sobre copias de seguridad, privacidad, escaneo, informes y más.
- **Modo de selección:** Mantenga pulsada cualquier tarjeta de garantía para empezar a seleccionar. La barra superior muestra cuántos artículos ha seleccionado y le permite moverlos todos a la papelera de una vez o cancelar.

---

## 3. Tarjeta de Activos Asegurados

La tarjeta de la parte superior de la lista muestra el valor total de sus artículos registrados.

- **Totales por moneda:** Los importes se suman por separado para cada moneda (por ejemplo ₺, $, €, ¥); las monedas no se convierten entre sí.
- **Desglose:** Toque la tarjeta para mostrar u ocultar el desglose por moneda.

---

## 4. Búsqueda, Orden y Filtros

- **Barra de búsqueda:** Filtra la lista mientras escribe, por nombre de producto o categoría. Incluye un botón para borrar con un toque.
- **Chips de orden:** **Fecha de Adición**, **Fecha de Vencimiento** y **Nombre**. Toque de nuevo el chip activo para invertir el orden.
- **Filtro de moneda:** Muestra **Todos los Productos** o solo los artículos registrados en una moneda.

---

## 5. Tarjetas de Garantía

Cada tarjeta muestra la imagen o el icono del producto, su nombre, la categoría (Electrónica, Ropa y Moda, Hogar y Vida, Automotriz, Cuidado Personal, Otros), el precio y una insignia con la cuenta atrás:

- **Color del tema:** quedan 30 días o más.
- **Naranja:** quedan menos de 30 días.
- **Rojo:** quedan menos de 3 días. En las últimas 24 horas, la insignia cuenta hacia atrás en horas, minutos y segundos.
- **Rojo oscuro:** la garantía ha vencido.

Toque una tarjeta para abrir el detalle del producto; manténgala pulsada para iniciar el modo de selección. Las fechas de fin de garantía incluyen el periodo de garantía adicional recibido mediante una transferencia por QR.

---

## 6. Añadir Artículos (Botón +)

El botón `+` de la esquina inferior derecha ofrece tres opciones:

- **Añadir Manualmente:** Un formulario con nombre del producto, icono, precio y moneda, categoría, fecha de vencimiento, **Derecho de Devolución** (número de días) e **Intensidad de Uso**. En **Docs y Pruebas** puede adjuntar una factura, un documento de garantía (imagen o PDF de hasta 25 MiB), una imagen del producto y un vídeo de prueba, y anotar dónde guarda la copia física. El **Modo de Entrada Continua** mantiene el formulario abierto tras guardar para introducir varios artículos seguidos.
- **Captura de garantía (Beta):** Fotografíe o elija un recibo, una factura o un documento de garantía. El texto se lee en su dispositivo y se sugieren el nombre del producto, el precio, la moneda y las fechas; los valores que no aparecen claramente se marcan como "Estimado". Compare siempre los campos con el original antes de guardar.
- **Restaurador de Recibos Térmicos:** Hace más legibles los recibos térmicos desvaídos con filtros de contraste y nitidez, y guarda los resultados en su propio archivo.

Al desplazarse hacia abajo aparece un botón para volver al principio de la lista.

---

## 7. Detalle del Producto

- **Documentos:** Vea la factura y el documento de garantía a tamaño completo.
- **Posible Devolución Activa:** Muestra los días que quedan del plazo de devolución que introdujo. Las condiciones de devolución varían según el país y la categoría.
- **Vídeo de prueba:** Reproduzca o descargue el vídeo de prueba con marca de tiempo.
- **Historial de Servicio:** Añada registros de servicio técnico con título, descripción y coste.
- **Menú de opciones:** **Editar**, **Compartir / Anuncio de Venta** (copia un texto de venta listo para usar), **Crear Certificado PDF**, **Compartir Video de Prueba**, **Transferir (Air Gap)** a otro teléfono mediante código QR, **¿Dónde está la copia física?** y **Eliminar** (mueve el artículo a la papelera).

---

## 8. Barra de Navegación Inferior

- **Garantías (Inicio):** Su lista de inventario y la tarjeta de Activos Asegurados.
- **Análisis:** Valor Total de Activos, Vencimientos Próximos, número de artículos, Vida Promedio de Garantía, Artículo Más Valioso, Distribución por Categoría y Entradas Mensuales de Garantías de los últimos 6 meses. Todos los cálculos se hacen en su dispositivo.
- **Herramientas:**
  - **Recibir Transferencia (Air Gap):** Escanee el código QR del teléfono emisor para añadir el artículo. El código QR contiene, de forma legible, el nombre del producto, el precio, la moneda, las fechas, el periodo de garantía adicional y la categoría; las fotos y los documentos no se transfieren.
  - **Restaurador de Recibos Térmicos**
  - **Certificado PDF:** Crea un informe PDF de inventario con todos sus artículos.
  - **Exportación Excel (CSV):** Exporta su inventario como hoja de cálculo.
  - **Video de Inventario** y **Tema y Apariencia:** Guías breves sobre la función de vídeo de prueba y los ajustes de apariencia.
- **Ajustes:**
  - **General:** Tema (predeterminado del sistema, claro, oscuro), Acento del Tema, Fondo Animado, Idioma y Notificaciones.
  - **Gestión de Datos:** Copia de Seguridad (Exportar), Restaurar (Importar), Papelera de Reciclaje (restaurar o eliminar definitivamente) y Borrar Todos los Datos (pide confirmación dos veces).
  - **Acerca de:** Reportar error y comentarios, Informes de fallos, Términos Legales y Privacidad, y Versión.

---

## 9. Notificaciones y Widget de la Pantalla de Inicio

- **Recordatorios:** Con el permiso de notificaciones, Vancrone le avisa 30, 7, 3 y 1 día antes de que termine una garantía y el último día, 2 días antes de que termine un plazo de devolución y periódicamente para que haga una copia de seguridad. También envía consejos y mensajes de temporada de forma ocasional. La entrega depende de los ajustes de batería y notificaciones de su teléfono.
- **Widget:** Añada el widget de Vancrone a la pantalla de inicio para ver cuántos artículos están seguros, próximos a vencer o en estado crítico sin abrir la app.

---

## 10. Notas de Seguridad

- **Dispositivos rooteados:** Si se detectan indicios de acceso root, Vancrone muestra una advertencia; puede continuar bajo su propio riesgo o salir.
- **Clave de cifrado perdida:** Si la clave de cifrado del teléfono deja de estar disponible, Vancrone conserva los registros ilegibles en una carpeta aparte y ofrece restaurar una copia de seguridad o empezar con una caja fuerte vacía.

---

## 11. Soporte y Comentarios

- Use **Ajustes > Acerca de > Reportar error y comentarios** para enviar un informe de error o una sugerencia (hasta dos al día). Se envían al desarrollador su mensaje, el correo electrónico que indique opcionalmente y datos básicos del dispositivo y de la versión de la app.
- También puede contactar con el desarrollador a través de la ficha verificada de Google Play Store.
- *Para protegerse de rastreadores de spam y bots automáticos, esta guía no publica direcciones de correo en texto plano.*
