# Vancrone Guía de la Pantalla Principal y Funciones

> Este documento es el manual oficial de usuario que describe la arquitectura, el mecanismo de seguimiento de garantías y las funciones de seguridad de la pantalla de inicio de Vancrone. Última actualización: 12 de septiembre de 2026.

---

## 1. Visión General y Arquitectura Offline-First

Vancrone es una herramienta independiente de inventario digital y bóveda de seguridad diseñada para registrar y gestionar con fiabilidad garantías, facturas, números de serie y pruebas de propiedad de sus compras.

- **Completamente sin conexión y almacenamiento local:** Vancrone nunca envía sus datos personales a servidores remotos ni a bases de datos en la nube. Las dependencias externas (incluida la burocracia de Google Drive API) se han eliminado por completo.
- **Bóveda local cifrada:** Todos los registros, fotografías de facturas y documentos adjuntos se almacenan exclusivamente en su dispositivo bajo cifrado con Room SQLCipher.
- **Responsabilidad del usuario y copias de seguridad:** Dado que los datos residen íntegramente en su teléfono, usted es el único responsable de respaldarlos. Si el dispositivo se pierde, se restablece de fábrica o se avería, el desarrollador no puede recuperar la información. Diríjase a **Ajustes > Seguridad de Datos y Copias de Seguridad** para exportar periódicamente un archivo de respaldo cifrado `.vcb` a un almacenamiento externo o memoria USB.

---

## 2. Barra Superior y Navegación Rápida

Ubicada en la parte superior de la pantalla principal, la barra superior de Vancrone ofrece herramientas de navegación y gestión por lotes:

- **Título de la aplicación e insignia de plan:** Al pulsar el título, la lista vuelve suavemente al inicio. Muestra de forma dinámica su plan activo (PRO / BUSINESS).
- **Vista de Calendario:** El icono de calendario en la esquina superior derecha proporciona una matriz mensual con todos los vencimientos próximos.
- **Preguntas Frecuentes (FAQ):** El icono de interrogación le dirige inmediatamente a guías prácticas, sugerencias y resolución de dudas.
- **Modo de Selección Múltiple:** Al mantener pulsada cualquier tarjeta de garantía, se activa la selección por lotes para mover varios artículos a la papelera a la vez.

---

## 3. Tarjeta de Activos y Valor en Múltiples Monedas

Situada en la parte superior de la lista, esta tarjeta con degradado dinámico muestra la valoración económica de sus productos protegidos:

- **Valoración en Moneda Principal:** Calcula el valor total en tiempo real de todas las garantías activas según su moneda predeterminada configurada (por ejemplo, €, $, ₺, ¥).
- **Desglose Multidivisa:** Al tocar la tarjeta, se despliega un panel detallado con los gastos registrados en otras monedas (EUR, USD, GBP, MXN, etc.).
- **Insignia de Seguridad:** Representa la protección local de su bóveda mediante cifrado en el propio dispositivo.

---

## 4. Búsqueda, Filtrado y Ordenación Dinámica

Localice cualquier artículo en cuestión de segundos gracias a herramientas avanzadas:

- **Barra de Búsqueda en Tiempo Real:** Filtra instantáneamente mientras escribe por nombre de producto, establecimiento o número de serie. Incluye botón de borrado rápido.
- **Filtros de Ordenación:**
  - **Fecha de Inclusión:** Orden cronológico según el momento en que se registró el producto (ascendente o descendente).
  - **Fecha de Vencimiento:** Destaca primero las garantías que están a punto de expirar para evitar la pérdida de coberturas y plazos de devolución.
  - **Nombre:** Orden alfabético de la A a la Z o de la Z a la A.
- **Filtro de Moneda:** Un chip desplegable para visualizar únicamente los productos registrados en una divisa concreta.

---

## 5. Tarjetas Inteligentes de Garantía e Inventario

Cada tarjeta presenta todos los datos clave de forma clara e intuitiva:

- **Identidad Visual:** Fotografía real del producto o icono representativo de la categoría.
- **Datos del Producto:** Nombre del artículo, categoría asignada (Electrónica, Ropa, Hogar y Estilo, Automoción, Cuidado Personal, Otros) y coste de compra.
- **Insignia Inteligente de Cuenta Regresiva (Código de Colores):**
  - **Verde / Resaltado:** Estado seguro con más de 30 días de cobertura restante.
  - **Naranja:** Atención necesaria; quedan menos de 30 días.
  - **Rojo (Alerta):** Ventana crítica (< 3 días). Durante el último día, se activa una cuenta regresiva en vivo (horas, minutos y segundos).
  - **Granate / Rojo Oscuro:** Garantías expiradas.
- **Acciones Rápidas:** Un toque abre la vista detallada (facturas en alta resolución, número de serie, código de barras, condiciones de garantía). Una pulsación larga activa la selección múltiple.

---

## 6. Botón de Acción Flotante (FAB)

El botón expandible `+` situado en la esquina inferior derecha le permite añadir nuevos registros:

- **Añadir Manualmente:** Formulario paso a paso para introducir nombre, categoría, fecha de compra, duración de garantía, garantía extendida, plazo de devolución, número de serie, fotos de factura y archivos PDF.
- **Recuperador de Recibos (Fiş Kurtarıcı):** Herramienta de restauración fotográfica con filtros especiales para recortar, contrastar y hacer legibles tickets térmicos desgastados o borrosos.
- **Desplazar al Inicio:** Acceso directo flotante que aparece al deslizar hacia abajo para regresar de inmediato al principio de la lista.

---

## 7. Barra de Navegación Inferior Flotante

Cambie con comodidad entre las diferentes secciones principales:

- **Garantías (Inicio):** Panel central y bóveda de inventario activo.
- **Análisis:** Distribución de gastos, estadísticas por categoría y gráfico interactivo de líneas de registros mensuales.
- **Herramientas:** Lector QR/código de barras, transferencia P2P de garantías entre dispositivos, tour en vídeo de inventario y papelera.
- **Ajustes:** Paleta de colores, selección de moneda, notificaciones y copias de seguridad cifradas `.vcb` mediante Android SAF.

---

## 8. Asistencia y Notificación de Errores

Si tiene dudas, desea sugerir una mejora o necesita informar sobre un fallo:

- Abra la aplicación y vaya a **Ajustes > Acerca de > Informar de Error y Comentarios**.
- El formulario integrado envía sus comentarios de forma directa y segura al equipo de desarrollo.
- También puede ponerse en contacto a través de nuestra ficha verificada en Google Play Store.
- *Con el fin de evitar el correo no deseado (spam) y los rastreadores automatizados, las direcciones de correo electrónico no se publican en texto plano en la documentación.*
