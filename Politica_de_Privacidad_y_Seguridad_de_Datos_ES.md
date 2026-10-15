# Política de Privacidad y Seguridad de Datos

> Este documento es la declaración completa en español sobre los principios de tratamiento de datos, medidas de seguridad y estándares de privacidad de la aplicación Vancrone. Última actualización: 15 de octubre de 2026.

## 1. Introducción

Esta Política de Privacidad describe el tratamiento de la información en relación con la aplicación Vancrone para Android. Hemos fundamentado esta política en una premisa incuestionable: Nosotros, el Desarrollador, no vemos, no recopilamos ni almacenamos su inventario personal, recibos, garantías o fotografías. Esta política detalla el alcance de dicho principio, los datos técnicos limitados que se recopilan a través de los servicios de Google integrados en la app y la información que usted decide enviar mediante el formulario de comentarios.

Responsable del Tratamiento: Vancrone ha sido desarrollada y publicada por un desarrollador independiente individual (en adelante, el "Desarrollador"). Puede contactar con el Desarrollador en vancrone.app@gmail.com; los datos verificados de publicación se encuentran en la ficha de Vancrone en Google Play Store. Dado que sus registros de garantía, facturas y fotos se conservan exclusivamente en el almacenamiento local sin conexión de su propio dispositivo, el Desarrollador nunca recibe este contenido ni actúa como responsable del tratamiento del mismo. El Desarrollador solo actúa como responsable respecto a los datos limitados descritos en las Secciones 6, 7 y 14: informes de fallos, los mensajes que envíe mediante el formulario de comentarios y, si se introducen compras dentro de la app, los registros de compra proporcionados por Google Play.

## 2. Nuestro Enfoque: Privacidad y Funcionamiento Local por Diseño (Offline-First)

Vancrone ha sido concebida bajo una arquitectura "offline-first". No existe ningún servidor central de Vancrone que guarde, clasifique o tenga acceso a los productos, importes, fechas, notas, fotos de facturas o vídeos de prueba que usted registre. Esta es una decisión de diseño técnico orientada a la privacidad ("privacidad desde el diseño").

## 3. Datos que No Recopilamos

Bajo ninguna circunstancia recopilamos, transmitimos, visualizamos, vendemos ni alquilamos:

- Registros de inventario y garantías (artículos, precios, plazos, periodos de devolución, registros de servicio, notas);
- Fotografías de facturas, tiques o vídeos probatorios de la caja fuerte;
- Resúmenes de riesgo financiero y plazos generados localmente por la app.

Estos datos son creados exclusivamente por usted y residen en su dispositivo hasta que decida exportarlos o compartirlos por su cuenta.

## 4. Datos Almacenados Localmente en su Dispositivo

Sus registros (nombres de productos, precios, fechas, periodos de devolución, registros de servicio y notas sobre dónde guarda los documentos físicos) se almacenan en una base de datos local cifrada con AES-256 mediante SQLCipher. La clave de la base de datos se genera en su dispositivo y se guarda en EncryptedSharedPreferences, protegida por una clave del Android Keystore (respaldada por hardware en los dispositivos compatibles). Las fotos de facturas, imágenes de productos y vídeos de prueba se guardan en el almacenamiento privado de la app, que Android aísla de otras apps y protege con el cifrado de almacenamiento del propio dispositivo; Vancrone no aplica una capa de cifrado adicional a estos archivos multimedia. En un dispositivo rooteado, otras apps podrían eludir estas protecciones.

## 5. Copia de Seguridad Manual Cifrada mediante Storage Access Framework (SAF)

Vancrone no contiene integración con la API de Google Drive ni dispone de servidores en la nube. En su lugar, proporciona un mecanismo de copia de seguridad local a través de Storage Access Framework (SAF) de Android:

- Exportación Cifrada Manual: Al crear una copia de seguridad en Ajustes, su base de datos, los archivos multimedia de sus garantías (fotos de facturas, imágenes de productos, vídeos de prueba) y las imágenes guardadas con el Restaurador de Recibos Térmicos se empaquetan y cifran en un único archivo (.vcb) con AES-256-GCM.
- Contraseña de Copia Opcional: Si establece una contraseña, la clave de cifrado se deriva de ella (PBKDF2-HMAC-SHA256, 600.000 iteraciones) y el archivo no puede abrirse sin ella. El Desarrollador no puede recuperar una contraseña olvidada. Si no establece contraseña, el archivo se cifra con una clave integrada en la app: podrá restaurarlo en cualquier dispositivo, pero cualquier persona que obtenga tanto el archivo como la app Vancrone también podrá abrirlo. Recomendamos usar una contraseña, sobre todo si guarda la copia en una ubicación compartida o en la nube.
- Control Absoluto del Usuario: Este archivo se guarda estrictamente en la ubicación seleccionada por usted mediante el selector SAF de Android (memoria interna, tarjeta SD, memoria USB u ordenador).
- Cero Acceso del Desarrollador: Vancrone nunca envía este archivo a servidores del Desarrollador ni a nubes externas. La custodia, traslado y conservación de esta copia corresponde por entero al usuario.

## 6. Servicios de Terceros Utilizados por Vancrone

Para su funcionamiento básico, Vancrone incorpora un conjunto reducido de SDKs de Google. Cuando estos SDKs envían datos, Google los trata por cuenta del Desarrollador conforme a sus condiciones de tratamiento de datos.

- Google Firebase Crashlytics — Diagnóstico de Fallos: Cuando la app falla o se produce un error controlado (por ejemplo, una exportación PDF o CSV fallida), Crashlytics envía un informe con la traza de pila, el modelo del dispositivo, la versión de Android, la versión de la app, un identificador aleatorio de instalación de Crashlytics y la hora del evento. Los informes no contienen sus registros, facturas ni fotos y no se vinculan a su nombre ni a su correo electrónico. Se utilizan solo para corregir errores y Crashlytics los conserva durante 90 días.
- Google AdMob — Publicidad (prevista): La versión actual de Vancrone no muestra anuncios ni incluye el SDK de Google Mobile Ads (AdMob). Si en una versión futura se introduce publicidad en la versión gratuita, esta política se actualizará antes de dicho lanzamiento y los anuncios personalizados solo se mostrarán con su consentimiento cuando la ley lo exija.
- Google ML Kit — Reconocimiento de Texto en el Dispositivo (OCR) y Escáner de Documentos: El escáner de facturas utiliza el reconocimiento de texto en el dispositivo de ML Kit y el escáner de documentos de los servicios de Google Play. Las fotos y textos extraídos se procesan en su teléfono y nunca se envían a servidores de Google. ML Kit puede contactar con Google para descargar actualizaciones de modelos y enviar métricas limitadas sobre el rendimiento de la propia API, que no incluyen sus imágenes ni sus textos.
- Facturación de Google Play — Compras Digitales: La versión actual de Vancrone no ofrece compras dentro de la app y no se conecta a la Facturación de Google Play. Si se introducen mejoras opcionales Pro o Business, se procesarán íntegramente mediante Google Play: los datos de pago los gestionará exclusivamente Google, el Desarrollador solo recibirá la información del pedido que proporciona Google Play (como número de pedido, producto, fecha de compra y país) y la app consultará el estado de sus compras en el dispositivo mediante la Biblioteca de Facturación de Google Play. Esta política se actualizará antes de ese cambio.

## 7. Ausencia de Infraestructura de Servidores; Formulario de Comentarios

Vancrone no dispone de servidores propios. El Desarrollador no mantiene ningún backend, cuentas de usuario ni bases de datos remotas para sus registros. Aparte de los servicios de Google descritos en la Sección 6, los datos solo salen de su dispositivo cuando usted lo inicia:

- Formulario de Comentarios: Cuando envía un mensaje desde Ajustes > "Reportar error y comentarios", el mensaje (hasta 500 caracteres), el correo electrónico que indique opcionalmente, el fabricante y modelo del dispositivo, la versión de Android, la versión de la app y la hora de envío se transmiten por HTTPS a un punto de acceso de Google Apps Script operado por el Desarrollador en la infraestructura de Google. Esta información se usa solo para responderle y corregir el problema notificado, y se conserva únicamente el tiempo necesario para ello. No incluya datos personales sensibles en sus mensajes.
- Exportación y Uso Compartido: Los informes PDF/CSV, las copias de seguridad y los archivos que comparta solo llegan al destino que usted elija.

## 8. Medidas de Seguridad

Además del cifrado local AES-256 de la base de datos, Vancrone utiliza consultas parametrizadas para evitar inyecciones SQL, decodifica y reduce las imágenes en el dispositivo antes de pasarlas al motor OCR local, verifica la integridad de las copias antes de restaurarlas (cifrado autenticado AES-GCM y sumas de comprobación SHA-256 de los archivos) y le avisa si detecta indicios de acceso root. La versión actual no ofrece compras; si se introducen, su estado se leerá de Google Play mediante la Biblioteca de Facturación de Google Play y Vancrone no realiza una verificación propia en servidor de las firmas de compra. Ningún sistema de seguridad es infalible, y usted sigue siendo responsable de la seguridad de su dispositivo.

## 9. Conservación de Datos y Control del Usuario

Dado que los datos radican en su terminal, el control es exclusivamente suyo:

- Opción "Borrar Todos los Datos": Elimina de forma permanente e irreversible todos los registros de garantía de la base de datos cifrada junto con sus fotos de facturas, imágenes de productos y vídeos de prueba. También elimina las imágenes guardadas con el Restaurador de Recibos Térmicos, así como los archivos multimedia sin registro asociado y las capturas temporales de la cámara que queden en el almacenamiento privado de la aplicación.
- Desinstalación de la Aplicación: Ocasiona el borrado íntegro y definitivo de los directorios de datos de la aplicación en el dispositivo.
- El Desarrollador no conserva copias de sus registros; la recuperación de información borrada es técnicamente imposible. Las copias de seguridad exportadas permanecen donde las guardó hasta que usted las elimine.
- Los informes de fallos y los mensajes de comentarios se conservan solo durante los plazos indicados en las Secciones 6 y 7.

## 10. Privacidad de Menores

Vancrone no está dirigida a menores de 13 años y no recopila datos de menores de forma intencionada.

## 11. Opciones del Usuario

- Anuncios e ID de publicidad: La versión actual no muestra anuncios ni recopila su ID de publicidad.
- Informes de fallos: Puede desactivar Crashlytics en cualquier momento en Ajustes > Acerca de > "Informes de fallos". El interruptor está activado por defecto. Mientras esté desactivado, no se envían informes de fallos y se eliminan los que aún esperan en su dispositivo; su elección se mantiene hasta que la cambie. Los informes enviados antes de desactivarlo se conservan durante el plazo indicado en la Sección 6. Desinstalar la app también detiene toda recopilación.
- Copias de seguridad: Puede exportar, proteger con contraseña o restaurar una copia cifrada (.vcb) en cualquier momento mediante SAF desde el menú de Ajustes.
- Supresión de datos: Accesible en cualquier momento mediante Ajustes > "Borrar Todos los Datos".

## 12. Transferencias Internacionales de Datos

Como Google opera a nivel mundial, los informes de fallos y mensajes de comentarios descritos en las Secciones 6 y 7, así como, si se introducen compras, los datos de pedidos de Google Play, pueden tratarse fuera de su país de residencia (incluidos los Estados Unidos). Para estas transferencias, Google se basa en sus condiciones de tratamiento de datos, incluidas las Cláusulas Contractuales Tipo (CCT) y, cuando proceda, el Marco de Privacidad de Datos UE-EE. UU.

## 13. Derechos de Privacidad

En virtud del RGPD y normativas similares, le asisten derechos de acceso, rectificación, supresión y oposición. Al encontrarse sus registros únicamente en su teléfono, puede ejercer dichos derechos sobre ese contenido directamente desde la aplicación. Para informes de fallos o mensajes de comentarios, escriba a vancrone.app@gmail.com; como los informes de fallos son seudónimos, es posible que el Desarrollador no pueda identificar qué registros le corresponden.

## 14. Disposiciones Específicas por Región

- EEE, Reino Unido y Suiza: Bases legítimas: interés legítimo (diagnóstico de fallos para mantener la app estable; respuesta a los comentarios que envíe) y, si se introducen compras, ejecución contractual (facturación). Si se introducen anuncios personalizados, se basarán en su consentimiento. Puede oponerse al tratamiento basado en el interés legítimo y acudir a su autoridad de control.
- Estados Unidos: No se realiza venta ni intercambio de datos personales en los términos de la CCPA.
- Turquía: Sus derechos con arreglo al Art. 11 de la KVKK pueden consultarse por correo en vancrone.app@gmail.com.

Vancrone es administrada por un desarrollador individual; las consultas por correo electrónico se atienden de buena fe y en plazos razonables según la disponibilidad de desarrollo.
