# Política de Privacidad y Seguridad de Datos

> Este documento es la declaración completa en español sobre los principios de tratamiento de datos, medidas de seguridad y estándares de privacidad de la aplicación Vancrone. Última actualización: 11 de septiembre de 2026.

## 1. Introducción

Esta Política de Privacidad describe el tratamiento de la información en relación con la aplicación Vancrone para Android. Hemos fundamentado esta política en una premisa incuestionable: Nosotros, el Desarrollador, no vemos, no recopilamos ni almacenamos su inventario personal, recibos, garantías o fotografías. Esta política detalla el alcance de dicho principio y los datos técnicos limitados recopilados por proveedores externos.

Responsable del Tratamiento: Vancrone ha sido desarrollada y publicada por un desarrollador independiente individual (en adelante, el "Desarrollador"). Puede contactar con el Desarrollador en vancrone.app@gmail.com; los datos verificados de publicación se encuentran en la ficha de Vancrone en Google Play Store. Dado que sus registros de garantía, facturas y fotos se conservan exclusivamente en el almacenamiento local sin conexión de su propio dispositivo, el Desarrollador nunca recibe este contenido ni actúa como responsable del tratamiento del mismo. El Desarrollador solo actúa como responsable respecto a los diagnósticos técnicos anónimos, publicidad y verificación de compras descritos en las Secciones 6 y 14.

## 2. Nuestro Enfoque: Privacidad y Funcionamiento Local por Diseño (Offline-First)

Vancrone ha sido concebida bajo una arquitectura "offline-first". No existe ningún servidor central de Vancrone que guarde, clasifique o tenga acceso a los productos, números de serie, importes, fechas, notas, fotos de facturas o vídeos de prueba que usted registre. Esta es una decisión de diseño técnico orientada a la privacidad ("privacidad desde el diseño").

## 3. Datos que No Recopilamos

Bajo ninguna circunstancia recopilamos, transmitimos, visualizamos, vendemos ni alquilamos:

- Registros de inventario y garantías (artículos, precios, plazos, números de serie, notas);
- Fotografías de facturas, tiques o vídeos probatorios de la caja fuerte;
- Resúmenes de riesgo financiero y plazos generados localmente por la app.

Estos datos son creados exclusivamente por usted y residen en su dispositivo hasta que decida exportarlos o compartirlos por su cuenta.

## 4. Datos Almacenados Localmente en su Dispositivo

Todo el Contenido de Usuario se almacena en una base de datos local protegida mediante cifrado AES-256 (SQLCipher para la base de datos relacional y EncryptedSharedPreferences con respaldo de hardware de Android para claves de configuración). AES-256 es el estándar de seguridad adoptado a nivel mundial por entidades bancarias y gubernamentales.

## 5. Copia de Seguridad Manual Cifrada mediante Storage Access Framework (SAF)

Vancrone no contiene integración con la API de Google Drive ni dispone de servidores en la nube. En su lugar, proporciona un mecanismo seguro y moderno de copia de seguridad local a través de Storage Access Framework (SAF) de Android:

- Exportación Cifrada Manual: Al seleccionar "Copia de seguridad (Exportar)" en Ajustes, su base de datos, registros y fotos se empaquetan y cifran en un único archivo (.vcb) utilizando el estándar AES-256-GCM.
- Control Absoluto del Usuario: Este archivo se guarda estrictamente en la ubicación seleccionada por usted mediante el selector SAF de Android (memoria interna, tarjeta SD, memoria USB u ordenador).
- Cero Acceso del Desarrollador: Este archivo nunca se envía a servidores del Desarrollador ni a nubes externas. La custodia, traslado y conservación de esta copia corresponde por entero al usuario.

## 6. Servicios de Terceros Utilizados por Vancrone

Para su funcionamiento básico, Vancrone incorpora un conjunto reducido de SDKs de Google:

- Google Firebase Crashlytics — Diagnóstico de Fallos: Registros anónimos de errores para solventar problemas de estabilidad y depurar el software.
- Google AdMob — Publicidad (Versión Gratuita): Empleado para la visualización de banners y anuncios bonificados en la versión gratuita.
- Google ML Kit — Reconocimiento de Texto en el Dispositivo (OCR): El escáner de facturas opera 100% de manera local en el teléfono. Las fotos y textos extraídos nunca se envían a servidores de Google.
- Facturación de Google Play — Compras Digitales: La adquisición de licencias Pro y Business se procesa íntegramente mediante Google Play; los datos bancarios son gestionados exclusivamente por Google.

## 7. Ausencia de Infraestructura de Servidores

Vancrone no dispone de servidores propios. El Desarrollador no mantiene ningún backend, cuentas de usuario ni bases de datos remotas. Con excepción de las funciones de diagnóstico de Google descritas en la Sección 6, ningún dato sale de su dispositivo hacia servidores del Desarrollador.

## 8. Medidas de Seguridad

Además del cifrado local AES-256, Vancrone incorpora saneamiento contra inyecciones SQL, validación de integridad previa al OCR y verificación de firmas criptográficas de compras emitidas por Google Play.

## 9. Conservación de Datos y Control del Usuario

Dado que los datos radican en su terminal, el control es exclusivamente suyo:

- Opción "Restablecer todos los datos": Destruye de forma permanente e irreversible la base de datos cifrada y los archivos asociados.
- Desinstalación de la Aplicación: Ocasiona el borrado íntegro y definitivo de los directorios de datos de la aplicación en el dispositivo.
- El Desarrollador no conserva copias de los datos; la recuperación de información borrada es técnicamente imposible.

## 10. Privacidad de Menores

Vancrone no está dirigida a menores de 13 años y no recopila datos de menores de forma intencionada.

## 11. Opciones del Usuario

- Anuncios: Puede desactivar la personalización de anuncios en Ajustes de Android > Google > Anuncios, o eliminarlos adquiriendo la versión Pro/Business.
- Copias de seguridad: Puede exportar o restaurar una copia cifrada (.vcb) en cualquier momento mediante SAF desde el menú de Ajustes.
- Datos de diagnóstico: Puede restringir el envío de informes en los ajustes de privacidad de su dispositivo.
- Supresión de datos: Accesible en cualquier momento mediante Ajustes > "Restablecer todos los datos".

## 12. Transferencias Internacionales de Datos

Los datos técnicos y de publicidad recopilados por Google pueden ser tratados fuera de su país de residencia (incluidos los Estados Unidos) al amparo de Cláusulas Contractuales Tipo (CCT).

## 13. Derechos de Privacidad

En virtud de normativas como el RGPD o leyes locales, le asisten derechos de acceso, rectificación y supresión. Al encontrarse sus registros únicamente en su teléfono, puede ejercer dichos derechos directamente desde la aplicación.

## 14. Disposiciones Específicas por Región

- EEE, Reino Unido y Suiza: Bases legítimas: interés legítimo (diagnósticos), consentimiento (anuncios personalizados) y ejecución contractual (facturación). Tiene derecho a acudir a su autoridad de control.
- Estados Unidos: No se realiza venta de datos personales en los términos de la CCPA.
- Turquía: Sus derechos con arreglo al Art. 11 de la KVKK pueden consultarse por correo en vancrone.app@gmail.com.

Vancrone es administrada por un desarrollador individual; las consultas por correo electrónico se atienden de buena fe y en plazos razonables según la disponibilidad de desarrollo.